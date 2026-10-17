# Networking Fundamentals
## OSI Model
#### Physical Layer (1)
- Responsible for transmitting raw bit streams over a physical medium
- Deals with physical connection between devices
- Includes Ethernet cables, hubs, and repeaters
#### Data Link Layer (2)
* Provides node-to-node data transfer - a link between two physically connected nodes
* Ensures that the data frames are transmitted with proper synchronization, error detection, and correction
* Devices such as switches and bridges to operate this layer
* Use *MAC* addresses to identify network devices
#### Network Layer (3)
* Handles packet forwarding 
* Routing packets through different routers to reach the destination network
* Responsible for logical addressing and path determination, ensuring that data reaches the correct destination across multiple networks
Routers use IP addresses to identify devices and determine the most efficient path for data transmission
#### Transport Layer (4) 
* Provides end-tp-end communication services for applications
* Responsible for reliable (or unreliable) delivery of data, segmentation, reassembly of messages, flow control, and error checking
* Protocols like TCP (offers reliable connection-oriented transmission with error recovery) and UDP (provides faster, connectionless communication without guaranteed delivery
#### Session Layer (5)
* Manages sessions between applications
* Establishes, maintains, and terminated connections, allowing devices to hold ongoing communications (***Sessions***)
* Essential for session checkpoint and recovery, ensuring that data transfer can resume seamlessly after interruptions
* Protocols and APIs operate at this layer coordinate communication between systems and applications
#### Presentation Layer (6)
* Acts as a translated between the *application layer* and the network format
* Handles data representation, ensuring that information sent by the application layer of one system is readable by the application layer of another
* Includes data encryption and decryption, data compression, and converting data formats
* Encryption protocols and data compression techniques operate at this layer to secure and optimize data transmission
#### Applications Layer (7)
* Provides network services directly to end-user applications
* Enables resource sharing, remote file access, and other network services
* Common protocols include: *HTTP*(Web browsing) , *FTP* (File transfer), *SMTP*(Email transmission), and *DNS* (resolve domain names to IP addresses
* Serve as the interface between the network and the application software
## TCP/IP Model
###### A condensed version of the OSI model, tailored for practical implementation on the inernet and other networks
#### Link Layer
###### Corresponds to the *Physical and Data Link* Layers
* Responsible for handling physical aspects of network hardware and media
* Includes technologies such as ***Ethernet*** for wired connections and ***Wifi*** for wireless connections
* Cover everything from physical connections to data framing 
#### Internet Layer
###### Corresponds to the *Network Layer*
* Manages the logical addressing of devices and the routing packets across networks
Protocols like IP and ICMP operate at this layer, ensuring that data reaches its intended destination by determining logical paths for packet transmission
#### Transport Layer
###### Corresponds to the *Transportation Layer*
* Provides end-tp-end communication services that are essential for functioning the internet
* Ensures that data packets are delivered in a sequential and error-free manner
#### Application Layer
###### Correspond to the *Session, Presentation, and Applicartion* Layers
* Contains protocols that offer specific data communication services to applications
* Provides interfaces and protocols necessary for data exchange between systems
------------------------------------
## Components of a Network
### End Devices
###### Computers, Smartphones, Tablets, IoT / Smart Devices
* AKA ***host***
* Any device that ultimately ends up sending or receiving data within a network
### Intermediary Dveices
###### Switches, Routers, Modems, Access Points
* Has the unique role of facilitating the flow of data between **end devices**, either within a LAN, or between deferent networks
* Connect networks and control traffic to enhance performance and reliability
### Network Medis and Software Components (NIC)
 * Use [IP tables](https://linux.die.net/man/8/iptables) to create  and manage a firewall
###### Cables, Protocols, Management and Firewall Software
* A hardware component in a computer, or other device, that enables connection to a networkk
* Provides physical interface between the device and the network media, handling the sending and receiving of data over the network
* Each NIC has a unique MAC address
* Can be designed for wired or wireless connections
### Servers
###### Web Servers, File Servers, Mail Servers, Database Servers
* A powerful computer designed to provide services to other computers (*clients*) over a network
* The backbone behind websites, email, file, and applications

# Network Communication and Addressing
## Network Communication
#### MAC *(Media Access Control)* Addresses
* * A unique identifier assigned to the NIC of a device, allowing it to be recognized on a local network*
* Each MAC address is crucial for communication within a local network , ensuring that data reaches the correct physical device
* 48 bits long and is represented in hexadecimal format
* Appear as 6 pairs of hexadecimal digits separated by colons or hyphens
* The Windows [GETMAC](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/getmac) command) will return the MAC address of every NIC on the host
#### IP *(Internet Protocol)* Addresses
* A numerical label assigned to each device connected to a network that utilizes the IP for communication
There are two versions of IP addresses: IPv4 (32-bit) and IPv6(128-bit)
## Ports
* *A number assigned to specific processes or services on a network to help computers sort and direct network traffic correctly
* Facilitate the simultaneous operation of multiple network services
* Use the [netstat](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/netstat) tool to view active connections and listening ports
* ***Well-known port*** (0 - 1023) are reserved for common and universally recognized services and protocols
* ***Registered Ports*** (1024 - 49151) are not strictly regulated but are still registered and assigned to specific services by the Internet Assigned Numbered Authority (IANA)
  * Commonly used for external services. Helps in managing network traffic and preventing port conflicts a
