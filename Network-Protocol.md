# Understanding Network Protocol

## IPv4
- as a network administrator, you will use the Transmission Control Protocol/Internet Protocol communications suite most often
- IP version 4 is the most frequently used communications protocol. IP resides on the network layer of the OSI model
- IP addresses consist of 4 numbers, each between 0 to 255
- for an IP address to *function*, there must be a properly configured IP address and compatiable subnet mask
    - to connect to the internet, you will also need a gateway address and DNS server address

## Classful Network Architecture
- the IPv4 classification system is known as the "classful network" architecture and is broken down into **5 sections, three which are used by hosts on networks - Classes A, B, C**
- the term node is sync with "host"
- anything that has an IP address is a host and has a node
- loopback testing:
    - the range for class A is 0-127
    - the 127 network number is not used by hosts as a logical IP address, instead this network is used for loopback IP addresses, which allows for testing
- usable addresses: always going to be **2 less than mathematical amount**
    - the first and last addresses cannot be used
    - the 0 in binary for the host bits defines the entire network
    - the 1 in binary defines the known as the broadcast address
- classes D and E are not used by regular hosts
    - D is used for what is known as multicasting- transmitting data to multiple computers or routers
    - E is reserved for future use, but has given way to IPv6 instead
- ip conflict:
    - avoid ip conflict by configuring unique ip addresses between two computers

## Addresses
- public address is exposed to the internet
- private ip address is hidden through an ip proxy or firewall device
- private addresses:
    - class A : 10.0.0.0 - 10.255.255.255
    - class B : 172.16.0.0 - 172.31.255.255
    - class C : 192.168.0.0 - 192.168.255.255
- APIPA: Automatic Private IP Addressing (a default address)
    - it uses a single class B network number: 169.254.0.0
- static IP address are addresses that are manually assigned to host
- dynamic IP addresses are more common, where they automatically obtain an IP address
## Default Gateway and DNS Server
- to have a fully functional computer, we need...
    - default gateway: the first IP address of the device that a client computer will look for when attempting to gain access outside the local network
    - DNS Server: the server that provides name resolution of host names to IP addresses
## Network Address Translation
- NAT, is the process of modifying an IP while it is operating across a router, computer, or similar device
    - this is usually so one larger address space (private) can be re-mapped to another address space, or perhaps re-mapped to a single public IP address
- classless inter-domain routing (CIDR)
    - allows network to be divided into different sized subnets to make one IP network that would have been considered a class... Done through **Variable Length Subnet Masking**
    - example = 192.168.0.0/16
## Subnetting
- subnetting is the subdivision of your logical IP network
- by default, all computers are on one subnet or network with no divisions involved
- by modifying the default subnet mask, you can subnet your network into multiple smaller networks
    - class a: 255.0.0.0 : 11111111.000000000.00000000.00000000
    - class b: 255.255.0.0 : 11111111.11111111.00000000.00000000
    - class c: 255.255.255.0 : 11111111.11111111.11111111.00000000
    - a subnet id of 14 would have a binary equivalent of 1110, the host IP in decimal would be 224-239
## IPv6 Addressing
- broken down into 3 parts:
    - global routing prefix: this is the first three groups of numbers, and it defines the network of the address
    - IPv6 subnet: this defines the individual subnet of the network that the address is located on
    - interface ID: this is the individual host IP portion: it can be assigned to one interface or more than one interface, depending on the type of IPv6 address
## Dual IP Stack
- exists when there are two internet protocol software implementations in an operating system, one for ipv4 and ipv6
- can these independently or can use hybrid implementation

- IPv4-mapped addresses have the first 80 bits set to 0, the next 16 to 1, and the last 32 bits populated
- ipv6 packets can be encapsulated inside ipv4 datagrams

## Summary
- Internet Protocol version 4, or IPv4, is the most frequently used communications protocol. IP resides on the Network layer of the OSI model, and IP addresses consist of four numbers, each between 0 and 255. The protocol suite is built into most operating systems and is used by most internet connections in the United States and many other countries/regions. 
- The IPv4 classification system is known as the classful network architecture and is broken down into five sections, three of which are commonly used by hosts on networks; these are Classes A, B, and C. 
- To complete an IP configuration, you need a default gateway address and a DNS server address. This helps the client computers access the internet.
- Network Address Translation (NAT) is the process of modifying an IP address while it is in transit across a router, computer, or similar device. 
- This is usually so one larger address space (private) can be remapped to another address space, or remapped to a single, public IP address. 
- One of the reasons for having a subnet mask is to have the ability to create subnetworks logically by IP address.
- It is a subdivision of your logical IP network and host IDs. Subnetting is the act of dividing a network into smaller, logical subnetworks. 
- Classless interdomain routing (CIDR) is a way of allocating IP addresses and routing Internet Protocol packets. 
- It was intended to replace the prior classful IP addressing architecture in an attempt to slow the exhaustion of IPv4 addresses.
- Classless interdomain routing is based on variable-length subnet masking (VLSM), which allows a network to be divided into different-sized subnets and make an IP network that would have previously been considered a class (such as Class A) appear to look like Class B or Class C. 
- IPv6 is the new generation of IP addressing for the internet, but it can also be used in small office networks and home networks.
- It was designed to meet the limitations of IPv4 address space and security.
- The transition from IPv4 to IPv6 is expected to take several more years. In the meantime, expect to see a mix of IPv4, IPv4/IPv6 (dual stack), and IPv6-only networks. 
- To help with the transition from IPv4 to IPv6, several methods were developed, including Teredo and Intra-Site Automatic Tunnel Addressing Protocol (ISATAP).  


- ipv6 is a 128-bit system where ipv4 is a 32-bit system