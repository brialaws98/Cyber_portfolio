# Dig (Easy)
###### Tasked to help the newly launched company,Fortaigan, audit its DNS records. To complete these tasks, I will be using a terminal to find information.
### Tools used
* [What is DNS?](https://www.cloudflare.com/learning/dns/what-is-dns/)
* [DNS records](https://www.cloudflare.com/learning/dns/dns-records/)
### Steps taken 
* I want to find the IP address for ``fortaigan.net``
  * ``dig @resolver A fortaigan.net`` ~ Used to ***find the IP address*** of the device with the *resolver* hostname
* I want to find the mail server now
  * ```dig @resolver MX fortaigan.net`` ~ Used to ***find the mail server*** of the device with the *resolver* hostname
  * To find the mail server that takes first priority, I need to find the server listed with the LOWEST number
* I want information on the nameserver
  * Discovered the primary nameserver and will use ``dig`` to figure out the IP address for this one as well
  * ``dig @resolver ns1.fortaigan.net``` was used to find the IP address for this task
* Finding the responsible person for this domain may be a bit trickier because many domains do not include them and may instead include a generic contact email
  * ``dig @resolver RP fortaigan.net`` ~ The ``RP record`` returns information about the responsible person
  * ``dig @resolver admin.fortaigan.net TXT`` ~ The email was used to find the full name of the person responsible
* I Want to find the flag
  * ``dig @resolver TXT fortaigan.net``~ The ``TXT record`` includes additional quotations and backslashes around the flag. These are part of how it is represented and are not a part of the flag
* ***SIP*** *(Session Initiation Protocol)* handles the signaling part of voice, video, and other messaging sessions that many modern businesses may need
  * Has ability to route calls using domain names instead of phone numbers <br>
    - SIP devices may need help locating the correct servers
* I want to find information about the service using a standard SIP SRV hostname ``_sip._tcp.``
  * ``dig @resolver SRV _sip._tcp.fortaigan.net`` ~ Returns the number of values (the port the SIP service listens on, the weight used for load balancing, and the priority) as well as the hostname of the server that provides the SIP service
* I discovered that the email that is ``sipserver.fortaigan.net``
  * ``dig @resolver fortaigan.net`` ~ Used the email that I discovered to find the IP address given to the SIP service

# Nmap (Easy)
###### Test your understanding of port scanning by scanning ``ports.cityinthe.cloud``.
### Tools used
* [Lists of TCP and UDP ports](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers)
* [Port specification and scan order](https://nmap.org/book/man-port-specification.html)
### Steps taken
* I want to find the 3 lowest TCP port on the system
  * ``nmap -Pn -p 1-500 ports.cityinthe.cloud`` <br>
    * ```-Pn`` ~ Treats all hosts as online --skip host discovery
    * ``-p <port ranges>`` ~ Only scan specific ports
* Scanning UDP ports can be challenging because UDP does not requires a response
  * Nmap will move on the scanning subsequent ports after the request times out
  * Scanning can take some time
* I just want to find the 10 lowest UDP ports
  * ``nmap -sU -p 1-10 ports.cityinthe.cloud`` ~ The open port is unfiltered
    *  ``-sU`` ~ UDP scan
    * ***Open|   |*** <br>
      - *Network behavior:* The target host responds with a UDP payload (DNS response or SNMP reply)
      - *What it means:* The port is unfiltered and an application actively replied
    * ***Open|Filtered*** <br>
      - *Network behavior:* Nmap receives no response at all (no packet returned, no ICMP error)
      - *What it means:* Nmap cannot tell the difference between an open port ignoring empty probes and a firewall dropping packets(``FILTERED``)
* I want to find more specific information about the service
  * ``nmap -sV -p 16080 ports.cityinthe.cloud``
    * ``-sV`` ~ Probe open ports to determine service version info

# Git (Easy)

# Net Track (Medium)

# Metadata (Hard)
