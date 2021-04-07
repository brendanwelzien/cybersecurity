# Understanding Network Security

**Firewalls**
- foundation of network security technologies
- system designed to protect computer / network from network-based attacks
- does so by *filtering data packets* that are traversing the network

**OSI MODEL**
- never fully utilized as a model for protocol, it is the standard for discussing how networking works

1. physical - bit, physical charateristics of network

2. data link - frame, connects data layer so it can be transmitted, handles error detection, correction, and hardware addressing, broken into 2 layers (Media Access Control (MAC) and Logical Link Control (LLC))

3. network - packets, routing
4. transport - data, messages, mechanism for carrying data acros network... segmentation (breaks down data),service addressing (assures data passed to right service and port), and error checking (assures data is sent or received correctly)
- tcp/ip connections made through process called *3-way handshake*
    1. cient sends a sychronized (SYN) packet to the server
    2. server acknowledges requeset and responds with a synchronize-acknowledge (SYN-ACK) packet
    3. client receives SYN-ACK and responds with acknowledgement (ACK) and a TCP socket is created
- buffering: allows for flow control by temporarily storing info until destination device is available
    - example: waiting in line to get on a ride at a theme park
- windowing: involves sending and receiving devices agreeing to standard amount of data to be sent at a time

5. session, synchronization between apps
6. presentation, converts app data into a format permittable for transmission across the network
7. application, takes and passes data to lower layers for transport, responses passed up through layers and displayed back to user

**Packet Filtering Firewall**
- considered the `first generation` firewall
- a *packet filtering firewall* inspects the data packets as they attempt to traverse the firewall, and based on firewall rules, the packets are either **allowed** or **denied**
- *routers* have ability to do some packet filtering, such as *permitting all outbound traffic while denying all inbound traffic*, or *blocking specific protocols from passing through router like telnet or ftp*

**Configuring Packet Filtering Firewall**
- generally you use a mix of these TCP/IP attributes:
    - source ip addresses
    - destination ip addresses
    - ip protocol (telnet, ftp, http, https, etc.)
    - source tcp and udp ports (example, http protocol runs on tcp port 80)
    - destination tcp and udp ports
    - inbound firewall network interface
    - outbound firewall network interface

**Circuit-Level Firewalls**
- considered `second generation` firewall technology
- work in similar fashion as packet-filtering, but operate at *transport* and *session* layers of OSI model
- instead of analyzing each *individual packet*, a circuit-level firewall monitors tcp/ip sessions, by monitoring tcp handshaking between packets to validate the session
- traffic is filtered based on specified session rules and may be restricted to authorized computers only


**Application-Level Firewall**
- known as proxy servers, work by performing deep inspection of app data as it traverses firewall
- rules are set based by analyzing client requests and app responses, then enforcing correct app behavior
- can block malicious activity, log user activity, and provide content filtering / protect against spam and viruses
- allows caching which is temporary storage of information for easy retrieval

**Stateful Firewall**
- statefull multi-level firewalls are designed to provide the best features of *both* *packet filtering* and *application-level firewalls*
- stateful inspection determines whether or not a packet is part of an existing session and that info can be used to either permit or deny a packet

## Host vs. Network Firewalls
- two basic types of software firewall:

1. Host Firewall: software firewall installed on a host, used to protect host from network-based attacks
    - known as *personal firewalls*

2. Network Firewall: software firewall is an app installed on a server used to protect network segments from other network segments

- when choosing the kind of firewall consider...
    - host hardware
    - host operating system
    - application conflicts
    - availability/stability

## Using Isolation to Protect a Network
- VLAN membership by Port
- VLAN membership by MAC Address
- VLAN membership by IP Subnet
- VLAN membership by Protocol

**Routing**
- routing takes one step up OSI model from VLAN - takes place at layer 3
- routing is the process of *forwarding a packet based on packet's destination address*
    - each step in the route a packet takes across the network a decision has to be made about where the packet is to be forwarded
    - to make these decisions, the *IP layer* consults a *routing table* stored in memory of the routing device

- two kinds of routers:
    - software:
        - cheap, easy to use, slow, limited scalability, limited protocol support
    - hardware:
        - high performance, very reliable, wide variety of protocols, high cost, complex

**Routing Protocols**
- based either on *distance vector* or *link state algorithm*
- path selection involves applying a routing metric to multiple routes, in order to select the *best* route
- metrics: bandwidth, network delay, hop count, path cost, load, reliability, & communication costs
- hop count = *# of routers traversed by a packet between its source & destination*

    **Routing Information Protocol (RIP)**
    - protocol that determines optimal route for packet to reach destination
    - broadcasts update message once in 30 seconds
    - issues: counts to *infinity*, sometimes when a route goes down routers begin to advertise bad route info to each other causing data to go back and forth until max hops count is reached
    - ways to resolve *count to infinity*:
        - split horizon: prevents a router from being updated with info from another router that it has advertised already
        - split horizon w/ poison reverse: allows routes to be broadcasted back to interface they were received from but are announced with a hop count of 16
        - triggered updates: instead of waiting a set time to broadcast a route, as soon as a change in the route is noted, a broadcast is immediately sent
    **OSPF - Open Shortest Path First**
    - OSPF is a link state protocol
    - metrics: bandwidth and delay
    - routing is carried out in autonomous system
    - no hop count

## Other Security Technologies
- **IDS** (intrusion detection systems) & **IPS** (intrusion prevention systems)
- IDS is a solution designed to detect unauthorized user activities, attacks, and network compromises
- IPS is similar, but in addition to detecting and alerting, an IPS can also take action to prevent breach from occurring

**Honeypots**
- a *honeypot* is a trap for hackers
    - distracts hackers from real targets, detect new vulnerabilities and exploits, and learn about attacker identity
- a *honey net* is just a collection of honeypots used to present an attacker an even more realistic attack environment
- a *padded cell* is a system that waits for an IDS to detech an attacker and then transfers the attacker to a special host where they cannot do any damage to the production environment

**DMZ**
- DMZ in computer networking, is a firewall configuration used to secure hosts on a network segment
- in most DMZs, the hosts on DMZ are connected behind a firewall which is connected to a public network like the internet
- another *common configuration* is to have firewall connected to an *Extranet*, with connections to customers and businesses. DMZs are designed to **provide access to systems without jeopardizing the internal network*

**NAT** (Network Address Translation)
- technique used to modify the network address information of a host while traffic is traversing a router or firewall
- this technique is used to hide the network information of a private network while allowing traffic to be transferred across a public network like the internet
- resulting solution for preserving a # of IP addresses used on the internet
- *Static NAT* --> maps an unregistered IP address on private network to a registered IP address on public network, using a *one-to-one* basis in conjunction with DMZ/extranet networks
- *Dynamic NAT* --> maps an unregistered IP address on private network to registered IP address that is selected by the routing

## VPN
- VPN (Virtual Private Network) is a technology that uses encrypted tunnels to create secure connections across public networks like the Internet. 
- VPNs are commonly used by remote employees for access to the internal network, to create secure network to network connections for branch offices or business partner connections, or even to create secure host to host connections for additional security and isolation on an internal network. 
- VPNs utilize encryption and authentication to provide confidentiality, integrity, and privacy protection for data. 

## IPSec
- Internet Protocol Security (IPsec) is a standards-based protocol suite designed specifically for securing Internet Protocol (IP) communications. 
- It is also a component of IPv6, the next generation of the IP protocol. IPsec authenticates and encrypts each IP packet in an IP data stream.  
- IPsec has protocols that can be used to establish mutual authentication and cryptographic keys negotiation during a session. IPsec operates at the Network Layer of the OSI model.

## SSL
- One of the key VPN protocols used today is SSL / TLS, which is the main alternative to IPsec for implementing a VPN solution.  
- While this protocol is widely used to secure websites, it has since been formalized in the IETF standard known as Transport Layer Security (TLS). 
- The SSL/TLS protocol provides a method for secure client/server communications across a network and prevents eavesdropping and tampering with data in transit. SSL/TLS also provides endpoint authentication and communications confidentiality through the use of encryption.

## SSH
- secure shell protocol, for secure remote login and other secure network services over the network
- SSH used for a # of apps across multiple platforms including UNIX, Windows, Mac, and Linux

- servers and domains can be isolated from the rest of your network through *Microsoft Active Directory and IPSec*

## Tunneling
- Tunneling is defined as the encapsulation of one network protocol within another. 
- Tunneling can be used to route an unsupported protocol across a network, or to securely route traffic across an insecure network. 
- VPN’s uses a form of tunneling when data is encapsulated in the IPsec protocol.
- Examples include PPTP and L2TP with IPsec.

## DNSSEC
- DNS Security Extensions (DNSSEC) adds security provisions to DNS so that computers can verify that they have been directed to proper servers. 
- DNSSEC provides authentication and integrity checking on DNS lookups ensuring that outgoing Internet traffic is always sent to the correct server. 
- This removes the issues of forged DNS data, because there is no way to forge the appropriate authentication. 
- This not only addresses the issue of website redirection, but also addresses some challenges associated with spam and the use of faked mail domains.

## Spoofing
- defined as a hoax, protocol spoofing is the misuse of a network protocol to create a hoax on a host or network device
    - ARP spoofing
    - DNS spoofing
    - IP Address spoofing

## Network Sniffing
- Network sniffing is a type of network analysis that is a very useful tool for network administrators responsible for maintaining networks and identifying network issues. 
- It involves connecting a device to the network with the appropriate software to allow access to the details of the packets traversing the network. 

## Common Attack Methods
- Denial-of-Service/Distributed Denial of Service (DoS/DDoS) Attacks
- IP Spoofing to Bypass Network Security
- Man in the Middle Attacks
- Back Door Attack
- DNS Poisoning
- Replay Attack
- Weak Encryption Keys
- Social Engineering
- Password Cracking
- Dictionary Attack
- Brute Force Attack
- Software Vulnerability Attack
- Buffer Overflow Attack
- Remote Code Execution Attack
- SQL Injection Attack
- Cross Site Scripting Attack

## Popular DDOS Attacks
- UDP flood
- ICMP (ping) flood.
- SYN flood.
- Ping of death
- HTTP flood
- Email denial-of-service attack
- Zero-day attacks.

## Wireless LAN (WLAN)
- allows users to connect to a network while allowing them to remain mobile
- basic component of wireless network is the SSID (service set identifier), which is defined in the IEEE 802.11 standard as the name for WLAN

## Wired Equivalency Privacy (WEP)
- The very first security capability available to WLAN users was WEP (Wired Equivalency Privacy). 
- WEP rapidly fell out of favor when a flaw with the encryption mechanism was found.
- The flaw in WEP makes it relatively easy for an attacker to crack the encryption and access the wireless network, so it is generally only used if no other solution is available (WEP is better than nothing) or the WLAN is being used with older devices, or devices like PDAs or handheld games that require the use of WEP.

## WPA/WPA2
- WPA (Wi-Fi Protected Access) was designed as the interim successor to WEP. 
- WPA included a new security protocol, Temporal Key Integrity Protocol (TKIP)
- WPA2 (Wi-Fi Protected Access version 2) is the standards-based version of WPA, except WPA2 implements all of the IEEE 802.11i standards.

# WLAN / MAC Addresses
- You can use MAC addresses to control what systems are able to connect to a WLAN through the use of MAC filters.  
- By turning MAC filtering on, you can limit network access to only permitted systems by entering the MAC address information into the MAC filters. 
- The table of permitted MAC addresses is maintained by the wireless access points. 

## SUMMARY
- A firewall is a system that is designed to protect a computer or a computer network from network-based attacks. 
- Network Access Protection (NAP) allows administrators a more powerful way to control access to network resources.  
- Virtual LANs (VLANs) were developed as an alternate solution to deploying multiple routers.
- Intrusion detection systems (IDS) is a solution designed to detect unauthorized user activities, attacks, and network compromises. 
- An intrusion prevention system (IPS) is very similar to an IDS, except that in addition to detecting and alerting, an IPS can also take action to prevent to breach from occurring.
- Honeypots, honey nets and padded cells are complementary technologies to IDS/IPS deployments.  A honeypot is a trap for hackers.
- A DMZ is a firewall configuration used to secure hosts on a network segment. 
- In most DMZs, the hosts on the DMZ are connected behind a firewall which is connected to a public network like the Internet.
- Network Address Translation (NAT) is a technique used to modify the network address information of a host while traffic is traversing a router or firewall.