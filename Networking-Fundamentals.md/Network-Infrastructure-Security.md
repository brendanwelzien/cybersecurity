# Defining Network Infrastructure And Network Security

**The Internet**
- worldwide system of connected computer networks
- not controlled by one body except in two technical aspects
    1. Ip classification system is defined by the **IANA** (Internet Assigned Numbers Authority)
    2. DNS is defined by the **IETF** (Internet Engineering Task Force) companies

**World Wide Web**
- system of interlinked hypertext documents that can be accessed with a web browser
- in stage Web 2.0

**Intranet**
- private computer network or single website that an organization implements in order to share data with employees globally
- user authentication is necessary before a person can access the information in an intranet
    - keeps general public out as long as intranet is secured properly

**Extranet**
- similar to intranet, but extends to users outside a company and to other organizations that are separate
- user authentication is still necessary

## VPN
- (virtual private network) is a connection between two or more computers or devices that are not on the same private network
- in order to ensure that only the proper users and data sessions cross to a VPN device, data encapsulation and encryption are used
    - a "tunnel" is created, through the LANs and WANs might intervene
- popular protocols include *PPTP* and *L2TP with IPSec*

### Point-To-Point Tunneling Protocol
- more commonly used, but is less secure
- includes security mechanisms, and no additional protocols need to be loaded up
    - a VPN device or server that allows incoming PPTP connections must have *inbound port 1723* open
    - PPTP works within the point-to-point protocol, which is also used for dial-up connections

### L2TP with IPSec
- Layer 2 Tunneling Protocol is quickly becoming popular as IPSec serves as its security protocol
    - L2TP is considered more secure because IPSec is required in most L2TP implementations
    - A VPN device or server that allows incoming L2TP connections must have *inbound port 1701 open*

### VPN Encryption
- Point-to-Point Tunneling Protocol (PPTP)
    - Based on PPP. Uses weak encryption

- Layer 2 Tunneling Protocol (L2TP)
    - Used with IPsec to provide security

- Secure Sockets Protocol (SSTP)
    - Uses HTTPS over TCP port 443

- Internet Key Exchange v.2 (IKEv2)
    - Uses Ipsec and supports VPN Reconnect. Doesn’t require a certificate

### VPN Authentication
- Password Authentication Protocol(PAP)
    - Uses plain text password. Unsecure

- Challenge Handshake Authentication Protocol (CHAP)
    - Uses challenge and response. Still used

- Microsoft CHAP v.2 (MS-CHAPv2)
    - Provides 2 way authentication. Stronger than CHAP

- Extensible Authentication Protocol (EAP-MS-CHAPv2)
    - Allows addition of biometrics and other forms of authentication

## Connection Manager Adminstration Kit
- the **Connection Manager Administration Kit (CMAK)** is used to create and customize the profiles for CM and dsitribute them to users.
    - once profile is completed that means all the settings for the user to connect, including the IP address of the VPN server is functioning
## Security Devices and Zones
- firewalls are the main defense for company's networks, whether they are LANs, WANs, intranets, or extranets
- perimeter security zones such as DMZs help keep certain information open to specific users or to the public while keeping the rest of an organization's data secret

## Firewalls
- used to protect a network from malicious attak and unwanted intrusion
- most commonly used type of security device in an organization's perimeter

## Packet Filtering
- inspects each packet that passes through the firewall and accepts/rejects it based on a set of rules
    - stateless packet inspection and stateful packet inspection (SPI)
    - stateless packet filter (pure packet filtering), does not retain memory of packets that have passed through the firewall
## NAT Filtering
- NAT endpoint filtering, filters traffic according to ports (TCP or UDP)
- done in *3* ways
    1. using basic endpoint connections
    2. by matching incoming traffic to corresponding outbound IP address connection
    3. by matching incoming traffic to corresponding IP address and port
## Application-Level Gateway
- (ALG) supports address and port translation and checks whether the type of application traffic is allowed
- adds a layer of security, but is resource intensive

## Circuit-Level Gateway
- Circuit-level gateway works at the session layer of the OSI model when a TCP or UDP connection is established. 
- Once the connection has been made, packets can flow between the hosts without further checking. 
- Circuit-level gateways hide information about the private network, but they do not filter individual packets.

## Port Scans
- a port scan allows a user to see if a port is responsive
- NMAP is a freeware program you can download to run a port scan on a target of your choice. (please don’t run port scans on systems you don’t own as there may be consequences) 
- Many firewalls block ping requests. To use NMAP without ping packets use the –Po option

## Proxy Server
- A proxy server acts as an intermediary between a LAN and the internet. 
- By definition, proxy means “go-between,” acting as a mediator between a private and a public network. 
- The proxy server evaluates requests from clients, and if they meet certain criteria, forwards them to the appropriate server. 

## Caching Proxy
- Caching proxy attempts to serve client requests without actually contacting the remote server. 
- Although there are FTP and SMTP proxies among others, the most common caching proxy is the HTTP proxy, also known as a web proxy, which caches web pages from servers on the internet for a set amount of time. 
- This is done to save bandwidth on the company’s internet connection and to increase the speed at which client requests are carried out. 

## IP Proxy
- secures a network by keeping machines behind it anonymous
- does so through use of NAT

## Internet Content Filter
- applied as software at the application layer and filters out various types of internet activities

## Network Intrusion Detection and Prevention
- A network intrusion detection system (NIDS) is a type of IDS that attempts to detect malicious network activities (such as port scans and DoS attacks) by constantly monitoring network traffic. 
- The NIDS will then report any issues that it finds to a network administrator as long as it is configured properly.
- A network intrusion prevention system (NIPS) is designed to inspect traffic, and, based on its configuration or security policy, it can remove, detain, or redirect malicious traffic in addition to simply detecting it.

## DMZ
- A perimeter network or demilitarized zone (DMZ) is a small network that is set up separately from a company’s private local area network and the internet. 
- It is called a perimeter network because it is usually on the edge of a LAN, but DMZ has become a much more popular term. 
- A DMZ allows users outside a company LAN to access specific services located on the DMZ. 
- However, when the DMZ set up properly, those users are blocked from gaining access to the company LAN.
- The DMZ might house a switch with servers connected to it that offer web, email, and other services.
- Two common DMZ configurations are as follows:
    - Back-to-back configuration: This configuration has a DMZ situated between two firewall devices, which could be black box appliances or Microsoft Internet Security and Acceleration (ISA) Servers. 
    - 3-leg perimeter configuration: In this scenario, the DMZ is usually attached to a separate connection of the company firewall. Therefore, the firewall has three connections—one to the company LAN, one to the DMZ, and one to the internet.

## Summary
- Point-to-Point Tunneling Protocol (PPTP), Layer 2 Tunneling Protocol over IPsec (L2TP/IPsec), Secure Socket Tunneling Protocol (SSTP), and VPN Reconnect (or IKEv2) are the four types of VPN tunneling protocols that are available in Windows 10. 
- During a VPN connection, the user should be authenticated to prove who is logging on. Therefore, you need to choose the most secure form of authentication that can be deployed to your remote users
- Security devices such as firewalls are the main defense for a company’s networks, whether they are LANs, WANs, intranets, or extranets. 
- Perimeter security zones such as demilitarized zones help to keep certain information open to specific users or to the public, while keeping the rest of an organization’s data secure.
- A proxy server acts as an intermediary between the LAN and the internet. By definition, proxy means “go-between,” acting as a mediator between a private and a public network. 
- A perimeter network or demilitarized zone (DMZ) is a small network that is set up separately from a company’s private local area network and the internet. It is called a perimeter network because it is usually on the edge of the LAN. 