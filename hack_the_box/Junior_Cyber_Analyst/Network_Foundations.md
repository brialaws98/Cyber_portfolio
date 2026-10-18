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
