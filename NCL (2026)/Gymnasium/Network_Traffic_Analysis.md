# DNS (Easy)
###### DNS is what enables us to access much of the internet without remembering IP addresses,Analyze  (DOmain Name Service) network packet capture to understand more about DNS
### Tools used
* [What is DNS](https://www.cloudflare.com/learning/dns/what-is-dns/) ~ Used to get a better understanding of what DNS is
* [AWS-What is DNS](https://aws.amazon.com/route53/what-is-dns/) ~ Another article to understand how it works
### Steps taken to solve problem
* Open Wireshark and Analyze the the packet
* I looked at the 4th packet:
  * Under *Domain Name System (queries)* => *Queries* I found out that:
    * The type of DNS query requested is ```AXFR```
    * The domain that was requested is ```etas.com```
* I wanted to know information on the response that was given by packet #5
  * Under *Domain Name System (response)* => *Answers* I found out that:
    * There are ```4``` items in the response
    * The TTL(Time To Live) was 3600(1hr) for all of the DNS records
    * The IP address for the "welcome" subdomain is ```1.1.1.1```

# FTP Traffic (Easy)
###### We found some interesting traffic, analyze the packet capture to identify what was transferred.
### Tools used
* [Computer Networking](https://trove.cyberskyline.com/computer-fundamentals-for-cybersecurity/networking)
* [Learn more about File Transfer Protocol (FTP)](https://en.wikipedia.org/wiki/File_Transfer_Protocol)
### Steps taken and solution
* I wanted to find the first ```Username:Password``` that was attempted
  * On the first packet, navigate "Follow => TCP Stream" option to look at the information
    * Found the first username and password that was used
    * Discovered the FTP server that is running
    * Discovered the successful login attempt
* Applied a filter in the search bar ```ftp.response.code == 230```, a code for successful logon
  * Discovered the first command that was executed
  * They deleted a file (```DELE```)
  * And then uploaded a new file (```STOR```)
* Applied ```ftp-data``` to the search bar to look for
  * In packet 17, in the "info" section, it shows a "LIST" command in the parentheses
    * Following the TCP Stream, I see the contents of the directory from when the command was run
   * In packet 25, there is a "STOR" command in the parentheses
     * ```STOR``` ~ uploads the file and stores it on the FTP server
  * Packet 65 shows another listing of the current directory after the file was uploaded
    * Discovered the file size (in byte) of the uploaded file
    * Discovered the file that was downloaded by the anonymous user

# HTTP (Easy)

# Telnet (Easy)

# Packet Dissection (Medium)

# Decrypt (Medium)

# Pandora (Hard)

# CAN Bus (Hard)

# WiFi PCAP 1 (Easy)

# Wifi PCAP 2 (Medium)

# Wifi PCAP 3 (Hard)
