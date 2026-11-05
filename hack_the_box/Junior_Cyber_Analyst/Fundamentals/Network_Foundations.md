# Skills Assessment
## Chapter 1 - Keep me in the loop
* ```ifconfig -a```
  * ``ifconfig`` ~ Used to configure network interfaces and display their current status
  * ``-a`` flag will display all interfaces 
* There are three unique IPv4 addresses and some IPv6 addresses as well
  * The ``lo`` interface seems differnt
* We are looking for a [loopback](https://www.geeksforgeeks.org/computer-networks/what-is-a-loopback-address/) address ``127.0.0.1``, which is always associated to the IPv4 address
  * This server is often used for testing, as a way to make sure an application is working as intended before going live on the network
  * Used to keep certain servers hidden from outside users
* ```netstat -tulnp4```
  * ``netstat`` utility displays network connections, routing, tables, and interface statistices
    * List all open or listening TCP and UDP ports for IPv4 in the format "``IP:PORT``"
    * May also show the name of the program responsible for each open port if permission allow
  * When the ``-n`` option is removed (``netstat tulip4``) the output will displayed as "``hostname:servive``" instead
* *Port forwarding* ~ A technique that allows traffic sent to one TCP/UDP port to be redirected to another

## Chapter 2 - Having Tuns of Fun
* At the end of Chapter one, we successfully investigated two out of three available network interfaces
  * *Loopback*(lo): Allow to send the network traffic to itself
  * *Public IP*(ens3): Enables to communicate with us over the internet
* That leaves the reamaining interface *tun0*
* After entering ```ip route get <target IP>```
  * Will display the route taken for any traffic sent to reach the target
  * Shows that all traffic of the target is routed through ``tun0``, a VPN tunnel that connects the VM to the private network
* Use ```ping -c 4 <target IP>``` to test the reachability of a host on a network
  * Does not use TCP or UDP ports, making it a ***Layer 4*** protocol in terms of the OSI model
  * Confirmed that the attack host and communicate with
* Using ```nmap <target IP>``` will return open TCP ports present on the target

## Chapter 3 - Target Acquired
###### ```nmap -p<target ports> -sC -sV <target IP>```
 * Adding the ``-sC`` and ``-sV`` options will allow Nmap to determine the version of whatever program is listening on a given port, as well as additional information
* Nmap tells us that the FTP (21) services has *Anonymous FTP* enabled
  * Means that anyone is able to connect to the FTP service
* The HTTP(80) service does not return as much information
* Initial Nmap scan operates at ***Layer 4*** of the OSI model
* For scans such as the version scan (``-sV``) or default scan (``-sC``), Nmap uses protocol=specific ***layer 7*** packets
###### ```nc <target IP> <port>```
 * We are telling [netcat](https://en.wikipedia.org/wiki/Netcat), a utility for making raw TCP/UDP connections, to connect to port 21 on the target machine
   * Once connected, are greeted with a banner from FTP service. indicating a successful connection
* Next step is to login as an *anonymous user* by using [Passive Mode](https://www.geeksforgeeks.org/difference-between-active-and-passive-ftp/)
  * Used the following to complete this task
```
USER anonymous[Ctrl+V][Enter][Enter]
PASS anything[Ctrl+V][Enter][Enter]
PASV[Ctrl+V][Enter]{Enter]
```
  * FTP requires a *return character and a new-line character (\r\n)* for its commands
* To determine the port number, I need to do some calculations because of the limitations in the FTP protocol
  * The full port cannot be displayed at once, so it is instead split to 2 small numbers p1 and p2; the last two numbers in the output
  * Then the real port is calculated as ``p1*256 + p2`` (See [this documentation](http://www.faqs.org/rfcs/rfc959.html) for more information
??????return to this part????
