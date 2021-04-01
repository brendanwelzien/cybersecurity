## DHCP
- short for `Dynamic Host Configuration Protocol`
- allows properly configured client computers to obtain IP addresses automatically from a DHCP server
    - the IP info may include...
        - ip addresses
        - subnet masks
        - gateway addresses
        - DNS server addresses
        - other advanced options
## DORA
- DHCP sessions use a 4 step process known as `DORA`:
1. **Discovery** = the client computer broadcasts out to the network in order to find a DHCP server
2. **Offering** = the DHCP server sends out a unicast "offering" of an IP address to the client computer
3. **Request** = the client broadcasts to all the servers that has accepted the offer
4. **Acknowledge** = the DHCP server sends a final unicast to the client that includes the IP information the client will use
    - DHCP utilizes ports 67 and 68
## DHCP Server
- installing a DHCP server requires...
    - installing the DHCP service
    - configuring an IP scope range
    - activating the scope
    - authorizing the server
    - configuring advanced IP options (optional)
## APIPA (automatic private ip addressing)
- feature of operating system which enables comps to self-configure ip addresses and subnet mask automatically when DHCP server is not reachable

- can get in the way of a client obtaining an IP address (when a client attempts to obtain an IP adddress from DHCP server, but it is too busy)
- you can disable APIPA

## Terminal Services
- also known as **Remote Desktop Services**, is a thin-client terminal server computing
- allows client computers to access and use apps loaded on server as well as to connect and take control of a server
- the service uses port 3389 and is also known as **Microsoft WBT Server** (window based terminal)

## Remote Access Service
- RAS is a grouping of different hardware and software platforms to allow remote access to another computer or network device
## IPSec
- internet protocol security is a protocol within the TCP/IP suite that encrypts and authenticates IP packets
- designed to secure any app traffic bc it resides on network layer/internet layer_
- integral part of ipv6

- three main protocols that ipsec uses:

1. Security association (SA): This generates the encryption and authentication keys that are used by IPsec.
2. Authentication header (AH): This provides connectionless integrity and the authentication of data. It also provides protection versus replay attacks.
3. Encapsulating security payload (ESP): This provides the same services as AH but also provides confidentiality when sending data.

## DNS
- The Domain Name System (DNS) is a worldwide service that resolves host names to IP addresses. 
- facilitates proper communication between computers. DNS servers communicate with each other in a hierarchy in an effort to teach each other their name resolutions. 
- DNS servers use inbound port 53 to accept name resolution requests. 

## WINS
- windows internet name service that resolves NETBIOS names to ip addresses