# Nmap Networking Reconnaissance & Security Auditing Exercises
###### [Nmap recon documentation](Nmap_recon.docx.pdf)
###### A collection of practical Nmap exercises demonstrating network exploration, active stack fingerprinting, port scanning, and service version detection
### Overview
This project contains lab exercises exploring the capabilities of **Nmap (Network Mapper)**, a free and open-source utility for network discovery and security Auditing. The exercises cover various active scanning techniques executed against local development or personal network environments
### Lab Exercises Breakdown
#### Exercise 1: Active State Fingerprinting
* ***Objective:*** Determine the operating system running on a target system using active stack fingerprinting
* ***Command Syntax:*** ```nmap -O -v <target_IP_address>```
  * ```-O```: Enables active fingerprinting to detect the remote operating system
  * ```-v```: Runs the scan in verbose mode
#### Exercise 2: Comprehensive Combined Scan
* ***Objective:*** Perform combined Scan incorporating TCP, UDP, application version detection, and OS fingerprinting
* ***Command Syntax:*** ```nmap -A -sS -sU -u ,target_IP_address>/24```
  * ```-A```: Enables OS detection, version detection, script scanning, and traceroute
  * ```-sS```: Executes a TCP SYN(stealth) port scan
  * ```-sU```: Executes a UDP port scan
#### Exercise 3: Network Ping Sweep
* ***Objective:*** Discover active hosts across a local subnet range
* ***Command Syntax:*** ```nmap -sP -v <class_IP_range>/24```
  * ```-sP```: Performs a ping Sweep to identify online hosts without running full port scans
* Picked up IP addresses for multiple devices
#### Exercise 4: Service Vendor and Version Detection
* ***Objective:*** Identify specific application vendors and version numbers running on target TCP ports
* ***Command Syntax:*** ```nmap -sV -vv <target_IP_address>```
* ```-sV```: Probes open ports to determine service/version info
* ```-vv```: Sets double verbose output for deeper log insights
#### Exercise 5: Stealth TCP SYN Port Scanning
* ***Objective:*** Conduct a stealthier port scan by specifying source ports and targeting precise service ports using a half-open connection method
* ***Command Syntax:*** ```nmap -sS -vv -g:80 -p <specified_ports> <target_IP_address>```
  * ```-g 80```:  Sets the source port to port 80 to bypass basic filtering policies
  * ```-p```: Specifies targeted ports
  * *Note on mechanics:* Sends a SYN packet upon receiving a SYN/ACK, responds with a RST packer instead of completing the 3-way handshake to maintain discretion

