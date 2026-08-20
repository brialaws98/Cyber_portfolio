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

# HTTP (Easy)

# Telnet (Easy)

# Packet Dissection (Medium)

# Decrypt (Medium)

# Pandora (Hard)

# CAN Bus (Hard)

# WiFi PCAP 1 (Easy)

# Wifi PCAP 2 (Medium)

# Wifi PCAP 3 (Hard)
