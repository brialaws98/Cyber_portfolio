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
## Chapter 3 - Target Acquired
