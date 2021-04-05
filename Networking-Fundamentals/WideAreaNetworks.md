# Understanding Wide Area Networks

## Routing
- routing is the process of moving data across networks between hosts or between routers
- information is transmitted according to IP networks and individual IP addresses of hosts in question
- router is in charge of maintaining tables of info about other routers on the network
    - a `static` route is one that has been manually configured
    - a `dynamic` route is one that has been implemented with special routing protocols
### Dynamic Routing
- dynamically configure routing tables
    - Routing Information Protocol (RIP)
    - Open Shortest Path First (OSPF)
    - Interior Gateway Routing Protocol (IGRP)
    - Border Gateway Protocol (BGP)

#### Routing Information Protocol
- uses distance-vector routing algorithms to decipher which route to send data packets
- calculates direction or interface that packets are forwarded to, as well as distance from destination
- RIPv1 and RIPv2 are common among today's networks

#### Open Shortest Path First (OSPF)
- a link-state protocol that monitors the network for routers that have a change in their link state, meaning they were turned off, turned on, or restarted
- most commonly used interior gateway protocol in large networks
- interior gateway protocols are used to determine connections between autonomous systems
- Interior Gateway Routing Protocol (IGRP): A proprietary protocol used in large networks to overcome the limitations of RIP. 
- Border Gateway Protocol (BGP): A core routing protocol that bases routing decisions on the network path and rules.

- QoS (Quality of Service)
    - traditional network carried only data packets
    - converged network also supports voice, video, and other time-sensitive packets
    - industry-wide set of standards

    - Shaping by application: When you shape by application, you categorize specific types of network traffic and assign that category a bandwidth limit.

    - Shaping network traffic per user: When you shape by network traffic per user, you delegate certain bandwidth to a user.

    - Priority shaping: When you shape by priority, you define the relative importance or priority of different types of traffic.
## WAN Technology
- wide area networks connect multiple local area networks together
- if an org wishes to have a wide area connection to another office, it needs to decide on a networking service
## Packet Switching
- Most WANs utilize some type of packet switching technology
- packet switching services include X.25 and Frame Relay
    - before packet switching, there were direct dial-up connections and other archaic forms of communication
## X.25
- X.25 communications protocol was one of the first implementations of packet switching, and it is still in use today
- packet switching was originally created to break down large messages into smaller, more manageable segments for transmission over a WAN
- data is gathered by the router (PAD), but router disassembles the entire lot into jumbled packets
- the PAD sends packets to a CSU/DSU as serial info. The CSU/DSU is the equivalent of the modem for the entire LAN.

## Packet Switching Exchange
- PSE are located in the central offices just inside the cloud, they are mega switching computers that handle huge numbers of packets --> decides which circuit each packet will take
- PSE then orders up a leased line from the local exchange carrier (LEC)
    - today, it is a digital line, usually at speed of 64K
    - synchronous
## Virtual Circuits
- PSE has thousands of circuits from which to choose (circuit set)
- the chances of entire message of packets taking one circuit are slim, because so many different users and companies are utilizing the bandwidth
- because multiple circuits are being used, the entire circuit set is known as the virtual circuit
## Hops
- possible several PSE stops along the way
- these are also PADs, and they disassemble and reassemble the packets
    - these stops are also known as hops
    - at the receiving so-called office, the PAD (router) reassembles packets and the overhead (header/trailer) is discarded
### X.25 Advantages
- If any data fails, X.25 automatically recovers and sends it again. 
- X.25 allows shared access among multiple users on the LAN. 
- X.25 has full error and flow control.
- There is also protection from intermediate link failure. 
    - X.25 is not completely fault tolerant, but it is 70% effective.
- Pricing is per shared packet sent, not per minute.
- X.25 is a synchronous, digital transmission. There is less overhead per file.

## Frame Relay
- advancement of X.25 packet switching
- newer form of packet switching designed for faster connections
- used to create a virtual circuit, but one that is more advanced. Frame Relay creates the "virtual network" that resides in the cloud
- many customers use the same groups of wires or circuits (shared circuits)
### Permanent Virtual Circuits
- with the frame relay, multiple sessions can run simultaneously on the same link
- these connections to the cloud are known as permanent logical links or permanent virtual circuits (PVCs)
- the PVC links the sites together in the cloud, and this is accomplished by the PSE (packet switching exchange)

## Leased Lines
- you must purchase Frame Relay service from internet services which are called leased lines
- must also commit a certain amount of info over time (committed information rate)(CIR)
- since this transmission is full duplex, there can be two CIRs for each PVC

## T-Carriers
- a T-carrier or telecommunications carrier system is a cabling and interface system designed to carry data at high speeds
- the basic data transfer rate of the T-carrier system is 64kbps, which is known as DS0, which is the digital signaling scheme
- DS1 would be the digital signaling scheme for the T1-carrier
- The two most common T-carrier systems are as follows:
    - T1: It is considered 1.544 Mbps, but only 1.536 Mbps of that is for data. 
        - The 1.536 Mbps is broken into 24 equal 64 Kbps channels and can be used with a multiplexor.
    - T3: Stands for trunk Carrier 3. 
        - Equivalent of 28 T1s. It is considered 44.736 Mbps, using 672 64 Kbps B channels. 

## ISDN 
- integrated services digital network is a digital technology developed to combat limitations of PSTN
- users that have ISDN can send data, fax, or talk on phone simultaneously from one line
- ISDN can be broken down into two major categories:
    - Basic rate ISDN (BRI): 
        - This is 128 Kbps with two equal B channels at 64 Kbps each for data, and one 16 Kbps D channel for timing. 
        - Generally, devices that connect to BRI lines can handle eight simultaneous connections to the internet.
    - Primary rate ISDN (PRI): 
        - This is 1.536 Mbps, and it runs on a T1 circuit. 
        - PRI has 23 equal 64 Kbps B channels for data, along with one 64 Kbps D channel for timing.
## ATM
- Asynchronous transfer mode (ATM) is a cell-based switching technology as opposed to a packet switching technology
- the cells involved in ATM are fixed length, normally 53 octets or 53 8-bit bytes

## SONET
- OCx is the standard for data throughput on SONET connections. 
- SONET is an abbreviation of Synchronous Optical Network. 
- It transfers multiple digital bit streams over optical fibers.

type|speed
----|-----
OC-1|51.84 Mbps
OC-3|155.52 Mbps
OC-12	|	622.08 Mbps
OC-24	|	1.244 Gbps
OC-48	|	2.488 Gbps
OC-192	|	9.953 Gbps

## FDDI
- fiber distributed data interface is a standard for transmitting data on optical fiber cables at a rate of around 100Mbps
- it uses ring topology

## DSL
- Digital subscriber line (DSL) is a family of technologies that provides data transmissions over local telephone networks. 
    - xDSL is the standard for the various digital subscriber lines. 
    - ADSL (asymmetrical digital subscriber lines) can run on your home telephone line so that you can talk on the phone and access the internet at the same time. 
    - SDSL (symmetrical digital subscriber line) is installed (usually to companies) as a separate line and is more expensive. The upload and download speed are the same or symmetrical.
## Broadband Cable
- used for cable internet and cable tv
- operates at a higher speed than DSL and it can usually get up to an average of 5 to 7 Mbps, although serial connection has the theoretical ability to go up to 18Mbps
- consumer information websites commonly show people connecting with cable at 10Mbps

## POTS/PSTN
- stands for plain old telephone system/public switched telephone network
- this is what we use for  **regular** phone lines since 1940s
- is now digital at the switching office and some central office, but there are analog lines running to people's homes

## Summary
- Static routing is when a router has been manually configured. For example, when a routing entry is manually entered in to the routing table with the route add command, it is known as static routing.
- Dynamic routing is implemented by dynamically configuring routing tables. This is done with dynamic routing protocols, such as RIP and OSPF.
- Quality of Service (QoS) is an industry-wide set of standards and mechanisms that ensure high-quality performance for critical and time-sensitive applications on shared networks. 
- Wide area networks connect multiple local area networks together. If an organization wants to have a wide area connection to another office, administrators need to decide on a networking service and the speed that they want to connect at. Budgeting plays a big role in these types of decisions.
- Although Frame Relay and T-carriers are very common WAN connectivity technologies, there are other types of connections that a company might opt for, such as ISDN, ATM, SONET, cable, or DSL.