# OSI
- open systems interconnection model
    - defines how data communication occurs on computer networks
    - divided into layers
## OSI Model Layers (Please Do Not Throw Sausage Pizza Away)
1. Layer 1 - Physical Layer
2. Layer 2 - Data Link Layer (DLL)
3. Layer 3 - Network Layer
4. Layer 4 - Transport Layer
5. Layer 5 - Session Layer
6. Layer 6 - Presentation Layer
7. Layer 7 - Application Layer
- this model exists to simplify how data transfer works
- similar to an order of operations for transcribing an idea to life
- the **communications subnetwork** is guts of OSI model and is **layers 1, 2, 3**
- **layers 4 - 7** are called upper layers
- networking standards such as 100BASE-T(100mbps) are based on physical layer
    - the BASE means baseband
    - the T stands for twisted-pair cabling
    - baseband refers to the fact that all computers on the LAN share the same channel to transmit data (one road)
    - broadband is the opposite, utilizes multiple channels (several roads)

## Layer 1 - Physical Layer //bits
- physical and electrical medium for data transfer
- includes but not limited to cables, jacks, patch panels, punch blocks, hubs, and MAUs
- concepts related to physical layer include... topologies, analog versus digital/encoding, bit synchronization, baseband versus broadband, multiplexing, and serial (5-volt logic) data transfer
- unit of measurement for this layer is **bits** (1s and 0s) (unit of measurement gives us hint at which layer things are supposed to go)

## Layer 2 - Data Link Layer //frames
- establishes, maintains, and decides how transfer is accomplished over the physical layer
- devices that exist on the DLL are network interface cards and bridges
- this layers ensures error-free transmission over the physical layer under LAN transmissions
    - does so through physical addresses known as the **MAC** address **(media access control)** (physical where IP is logical)
    - MAC address is a unique identifier assigned to network adapters by the manufacturer
    - six octets in length and written in hexadecimal
- unit of measurement is **frames**
- a layer 2 switch is the most **common** type of switch used on a LAN
    - hardware based and uses the MAC address of each host computer's network adapter when deciding where to direct frames of data
    - every port on switch is mapped to MAC address of the computer physically connected to it
    - security is a concern with layer 2 switches
    - switches have memory that is set aside to store the MAC address to port translation table, known as the MAC table or *Content Addressable Memory (CAM) table*
        - this table can be compromised with a MAC Flood attack
- layer 2 switch can also allow for a virtual LAN to be implemented
    - VLAN implemented to segment network, reduce collisions, organize network, boost performance, and to increase security
    - IEEE 802.1Q, modifies ethernet frames by tagging them with the appropriate VLAN information (classroom vs staff information)
    - VLANs are used to restrict access to network resources, but this can be bypassed through VLAN hopping

## Layer 3 - Network Layer //packets
- dedicated to routing and switching information to different networks, LANs, or internetworks
- devices that exist on the network layer are routers and IP switches
- if you have an IP address, you are a **host**
- gets into logical addressing of hosts, such as IP
- unit of measurements is **packets**

- layer 3 switches:
    - layer 3 switch differs from layer 2 switch and determines paths for logical addressing and not physical addressing
    - layer 3 switch are similar to routers
    - switches forward packets,
    - managed switches
## Layer 4 - Transport Layer//segments, data, messages
- ensures error-free transmission between hosts through logical addressing
    - manages the transmission of messages through layers 1 to 3
- protocols that are categorized by this layer break up messages, send through subnet, etc.
- contains both connection-oriented and connectionless systems
- inbound and outbound ports are controlled by this layer, when you think **ports**, think the transport layer
- the unit of measurements is referred to **segments or messages** or **data**

- TCP and UDP:
    - TCP is **transmission control protocol**, which is connection-oriented protocol
    - UDP is **user datagram protocol**, which is connectionless
    - example of an app that uses TCP is a web browser, and app for UDP is streaming media
- Connection Oriented Communications:
    - (CO mode) requires that both devices or computers involved establish an end-to-end logical connection before data can be sent between the two
    - if an individual packet is not delivereed in a timely manner, it is re-sent, this is done bc the sending computer has the established connection and knows where to resend the packet
- Connectionless Communications:
    - no end-to-end connection is necessary before data is sent
    - every packet that is snet has destination address in its header
    - this is sufficient to move independent packets, such as when streaming media
    - if the packet is lost, it cannot be re-sent, because hte sending computer never established a logical connection and does not know which logical connection to use the send failed packet
- Ports:
    - layer 4 takes care of ports that a computer uses for data transmission
    - ports act as logical communications endpoints for computers
    - defined by **Internet Assigned Numbers Authority** or **IANA**, where 65,535 capable ports are defined
        - 0:1023 = well-known ports
        - 1024:49151 = registered ports (for proprietary applications) (open-source)
        - 49152:65535 = dynamic and private ports
    - know all the ports from the table in PP
    - 21 (FTP), 53 (DNS), 80 (HTTP), 443 (HTTPS)
## Layer 5 - Session Layer
- governs establishment, termination, and synchronization of sessions within OS over the network and between hosts (when you log on and log off for example)
- this is the layer that controls the name and address database for the OS or NOS. NETBIOS (Network Basic Input Output System) works on this layer (NetStat Command)

## Layer 6 - Presentation Layer
- translates the data format from sender to receiver in various OSes that may be used
- code conversion, data compression, and file encryption
- redirectors work on this layer, such as mapped network drives that enable a computer to access file shares on a remote computer

## Layer 7 - Application Layer
- layer for message creation and packet creation --begins
- end-user protocols such as FTP, SMTP, Telnet, and RAS work at this layer
- this layer is not the application itself, but the protocols that are initiated by this layer

## TCP Model
- the TCP/IP model is similar to OSI model
    - often used by software manufacturers who are not as concerned with how info is sent over physical media, or how data link is actually made
    - 4 layers
    1. Data Link Layer
    2. Network Layer
    3. Transport Layer
    4. Application Layer