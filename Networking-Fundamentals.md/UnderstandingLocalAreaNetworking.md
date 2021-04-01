- instructor:
    - vrandle@nhorlando.com

# Networking Fundamentals
- understanding lcoal area networking
- defining networks with the OSI model
- understanding wireless networks
- understanding internet protocol
- implementing TCP/IP in the command line
- working with networking services
- understanding wide area networks
- defining network infrastructures and security

# Security Fundamentals
- understanding security layers
- authentication, authorization, and accounting
- understanding security policies
- understanding network security
- protecting the server and client

# The Exam
1. Complete 5 practice exams via **CyberVista** with 90% and send results to `@jenniferr@nhorlando.com` for the course 40032

# Lesson 1 // Understanding Local Area Networking / central connecting devices

## Local Area Network
- a local area network (LAN) is a group of these computers that are confined to a small geographic area, usually within a building
- LAN requires computers with network adapters, central connecting devices, and a medium to bring it together through cabled/wireless connections
    - networks are used to exchange data
1. create network documentation for LAN, the documentation phase occurs before a network is built
    - a **hub** is the most basic of central connecting devices
    - connects each of networked computers. known as hosts, to one another by way of copper-based cables (cannot get to internet)
    - any host that sends data must first send data to hub, and then broadcasted to rest of network 
### 4-Port Router
- router acts as central connecting device, but a communications link to the internet where one can send/receive data from computers on internet
    - *gateway devices*, a door to your network, allows devices to talk to each other and other networks
### Switch
- **segmentation** of your network, the more computers added to your network requires a **switch** to organize network traffic
- **unicasts** (allows a computer to talk directly another party vs. broadcasting where everyone receives the communication)
### Network adapter and RJ-45 Patch Cable
- a network adapter, known as network interface card or NIC, is device that enables you to send and receive data to / from computer
- an adapter can connect to the network by cable or air (wireless)
- a RJ-45 (**ethernet port**) port is the port where the adapter connects (ex. **ethernet cable**)

- serial data transfer, is the transfer of one bit at at a time in a single-bit stream through twisted-pair cabling through LAN (binary)
- a byte is = 01010101

- ethernet
    - set of rules that govern the transmission of data between network adapter and connecting devices
    - 802.3u or fast ethernet runs at 100mbps
    - 802.3ab or gigabit ethernet
### Types of Transfers
- broadcast has data sent to every other host on network
- unicast has data sent to one host only

### Data Transfer Rate
- known as bit rate, defines bits per sec that is transmitted over a network

### IP Address
- allows each computer to send and receive information back and forth in a manner
- identifies your computer number and network it lives on
    - broken down into two parts, the network portion and the host portion
    - the 255s represent the network portion of the IP where the 0 represents the host portion
    - default gateway represents address of router
* IPConfig command shows IP configuration information
* ping command is used to test network connectivity between two hosts
    * ping loopback
    * ping localhost
    * ping 127.0.0.1

- a wireless lan requires a **wireless access point** (WAP) as the central connecting device for network
- a virtual lan on a switch can organize a group of hosts together and can have separate networks (classroom 1, classroom 2, library, staff)
### Perimeter Network
- DMZ, is a small network that is setup separately from a company's private LAN and the internet
- usually on the edge of the LAN, but DMZ has become a much more popular term
- space in network where you want limited access to occur
- back to back configuration vs. 3-leg perimeter configuration
### Network Topology
- defines the physical connections of hosts in a computer network
    - **bus**
    - **ring**
    - **star**
    - **mesh**
    - **tree**

- **bus**
    - each device is connected to a single cable by an interface connector
    - central cable is known as the **backbone or bus**
    - bus ends up being single point of failure
- **star**
    - most common topology
    - each computer is individually wired to a central connecting device
- **mesh**
    - every computer connects to every other computer, no central connecting device is needed
    - fault tolerant!! (data can still be interacted with other devices if one goes bad or becomes corrupted)
- **ring**
    - in a LAN environment, each computer is connected to the network using a closed loop, data passed in one direction, one machine at a time
    - used by token ring and FDDI

- a token ring:
    - network that sends data logically in a ring fashion meaning that a token goes to each computer, one at a time, but is physically connected in a star fashion
    - all computers in token ring network are connected to a central connecting device known as Multistation access (MAU or MSAU)
- Ethernet:
    - stadnardized by **Institute of Electrical and Electronics Engineers** (IEEE) as **802.3**
    - computers on ethernet networks communicate by sending ethernet frames
    - a **frame** is a group of bytes packaged by a network adapter for transmission across network
    - the **IEEE 802.3** defines carrier sense multiple access with collision detection or CSMDA/CD
        - computers on a default ethernet LAN all share the same channel, CSMDA/CD governs the way computers co-exist with limited collisions 802.3 (wired)
        - if an organization utilizes wireless ethernet, carrier sense multiple access with collision avoidance (CSMA/CA) is employed 802.11 (wireless)
    
### 802.3 Ethernet Standards
- 802.3 // 10mbps
- 802.3a // 10mbps
- 302.3i // 10mbps
- 802.3j // 10mbps
- 802.3u // 100 mbps
- 802.3ab // 1Gbps
- 802.3z // 1Gbps
- 802.3ae // 10gbps
- 802.an // 10gbps
- 802.3ba / 40gbps and 100 gbps

### Distributive Computing
- today's computing, used for both client-server and peer-to-peer networks
- every device or workstation has its own processing power
    - thin-client computers do not have a hard drive and store operating system in RAM (random access memory), to be loaded every time the device is turned on
### Peer-To-Peer Networking
- each computer is treated as equal
- peer computers serve data, the difference is they can only serve it to small number of computers at the same time
- refers to file sharing networks

### Summary
- A network is two or more computers that exchange data. A local area network (LAN) is a group of these computers that are confined to a small geographic area, usually one building.
- The network adapter, also known as a network interface card (NIC), is the device that enables the sending and receiving of data to and from your computer. Today, multiple devices can connect to each other and communicate using a switch.
- Internet Protocol (IP) is the part of TCP/IP that, among other things, governs IP addresses. The IP address is the cornerstone of networking. It defines the computer or host you are working on.
- A wireless local area network (WLAN) has many advantages, the most standout of which is the ability to roam. A person with a laptop, handheld computer or PDA, or other like device can work from anywhere.
- Network topologies define the physical connections of hosts in a computer network. There are several types of physical topologies, including bus, ring, star, mesh, and tree.
- Today’s computing is known as distributive computing and is used for both client/server and peer-to-peer networks. This means that every device or workstation has its own processing power. 
- The client/server model is an architecture that distributes applications between servers, such as Windows Server 2016, and client computers, such as Windows 8/8.1 or Windows 10.
- Peer-to-peer networking, first and foremost, means that each computer is treated as an equal. This means each computer has the equal ability to serve data and to access data, just like any other computer on the network. Before servers became popular in PC-based computer networks, each PC had the ability to store data. 