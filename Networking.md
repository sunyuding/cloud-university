S​how off your depth of knowledge and understanding of network theory, like different protocols (TCP/IP, UDP, ICMP, etc), MAC addresses, IP packets, DNS, OSI layers, and load balancing. 
# Protocols
## TCP/IP
- The three-way handshake
            - Setting up a connection
            - Delivery acknowledgements
        - Retransmission
        - In-order delivery
        - Congestion control
        - Error detection
            - No improvement, but checksum is mandatory
        - Bigger heander
        - Data doesn't always get sent out immediately
        - Bigger overhead
        - Text communication
        - File transfers
        - Remote access (e.g. SSH)
## UDP
- Advantages
            - Small packet sizes
            UDP header: 8 bytes
            TCP header: 20 bytes
            - No connection to create and maintain
            - More control over when data is sent
        - No error recovery
        - No compensation for losing package
        - Packets can arrive out of order
        - Multimedia streaming
        - Some firewall block UDP
## ICMP
## HTTP
  - Each HTTP request includes 5 key elements/core components:
    - HTTP methods: GET, PUT, POST, DELETE, OPTIONS,
    - URI(Uniform Resource Identifier)
    - HTTP version
    - Request Heander/metadata
    - Request Body
  - Each HTTP response includes 5 key elements/core components:
    - Status/Response Code: 200, 404, 503
    - HTTP Version: HTTP v1.1
    - Response Header
    - Response Body

# MAC addresses

# IP packets

# DNS

# ISO OSI Model 
International Standards Organization Open Systems Interconnect. Please Do Not Take Salami Pizza Away.

| TCP/IP 4 Layers        | OSI MOdel 7 Layers     | 
| ---------------------- |------------------------| 
| Application Layer      | 7 - Application Layer  | 
|                        | 6 - Presentation Layer |   
|                        | 5 - Session Layer      |  
| Transport Layer        | 4 - Transport Layer    |
| Internet Layer         | 3 - Network Layer      |
| Network Access Layer   | 2 - Data Link Layer    |
|                        | 1 - Physical Layer     |

## Application 
- This consists of network aware applications like Email, Web Browsers, File sharing services, Print servers, Network drives, Twitter, Facebook
- Protocol
    - HTTP 80
    - HTTPS 443
    - SMTP
    - SSH
    - NTP
    - DNS 53
    - Telnet 23
    - FTP 20 and 21
- PDU - Data
- The **Data** is broken up into **Segments** which use Ports to identify services
- Clients are dynamically assigned ports from 8000 to 65535

## Presentation
- Job is to configure the data: encryption, compression, translation

## Session
- It's job is to control the communication: login rights, permissions, rights

## Transport
- It's job is to guarantee end to end delivery of data
- Purpose of the transport layer
    - Letting multiple applications use one network connection simulaneously
- Protocol
    - UDP(User Datagram Protocol)  
    - TCP(Transmission Control Protocol)

## Network
- Internet Layer for the 4 Layers Model
- Protocol
    - Internet Protocol (IP)
    - Internet Control Message Protocol (ICMP)
        - A lightweight protocol used to carry error messages and information about a network
        - Function used by Ping
    - Address Resolution Protocol (ARP)
- The Internet layer PDU is called a **packet**
- The IP packets use this addressing scheme: IP Addresses
- Ex. 192.168.100.254

## Network Access Layer
- Mostly uses **Ethernet Frames**
- Physical Address ex.
- 00.12.F4.AB.0C.82
- 00-12-F4-AB-0C-82
- 0012.F4AB.0C82
- 48 bit hexadecimal number
- Also called the "**MAC address**"

### Data Link
- Ethernet or WiFi
- PDU - Frames

### Physical
- coaxial Ethernet cable
- PDU - Bits

# Addressing Summary:
- Application Layer
    - Data
- Transport Layer
    - Segments
    - Ports (http: 80, DNS: 53, Telnet: 23)
- Internet Layer
    - Packets
    - IP addresses (192.168.100.254)
- Network Access Layer
    - Frames
    - Physical Addresses (00.12.F4.AB.0C.82)

# Device Summary:
- Application Layer
    - Application Layer Gateway (ALG) - Data
- Transport Layer
    -  Firewalls - Ports
- Internet/Network Layer
    - Routers and Layer 3 Switches - IP addresses
- Data Link Layer
    - Bridges and Switches - Physical Addresses
- Physical Layer
    - Repeaters (transceivers) and Hubs - Bits

# Load Balancing

# References
- [ ] Check out [C​omputer Networking: A Top-Down Approach](https://www.bau.edu.jo/UserPortal/UserProfile/PostsAttach/10617_1870_1.pdf).
- [x] [Khan Academy](https://www.khanacademy.org/computing/computer-science/internet-intro)
- [x] [UDP and TCP: Comparison of Transport Protocols](https://www.youtube.com/watch?v=Vdc8TCESIg8)
- [x] [TCP/IP and the OSI Model Explained!](https://www.youtube.com/watch?v=e5DEVa9eSN0)
- [ ] [Packet Transmission across the Internet. Networking & TCP/IP tutorial.](https://www.youtube.com/watch?v=nomyRJehhnM)
- [ ] [HTTP](https://www.youtube.com/watch?v=WGJrLqtX7As)
- [ ] [SSL and HTTPS](https://www.youtube.com/watch?v=S2iBR2ZlZf0)
- [ ] [SSL/TLS](https://www.youtube.com/watch?v=Rp3iZUvXWlM)
- [ ] [HTTP 2.0](https://www.youtube.com/watch?v=E9FxNzv1Tr8)
- [ ] [Video Series (21 videos)](https://www.youtube.com/playlist?list=PLEbnTDJUr_IegfoqO4iPnPYQui46QqT0j)
- [ ] [Subnetting Demystified - Part 5 CIDR Notation](https://www.youtube.com/watch?v=t5xYI0jzOf4)
- [ ] Sockets:
    - [ ] [Java - Sockets - Introduction (video)](https://www.youtube.com/watch?v=6G_W54zuadg&t=6s)
    - [ ] [Socket Programming (video)](https://www.youtube.com/watch?v=G75vN2mnJeQ)
- [ ] (Book) [Understanding Linux Network Internals](http://shop.oreilly.com/product/9780596002558.do)
- [ ] [OSI Reference Model Layer Mnemonics](http://www.tcpipguide.com/free/t_OSIReferenceModelLayerMnemonics.htm)
- [ ] [Top 60 Networking Interview Questions And Answers](https://www.softwaretestinghelp.com/networking-interview-questions-2/)

- [x] [What happens when ...](https://github.com/sunyuding/what-happens-when)
    - The "g" key is pressed
        - auto-complete dropbox
    - Parse URL
        - Protocol
            - http
            - https
        - Resource   
    - DNS lookup
        - browser cache
        - the ISP's caching DNS server
    - Opening of a socket
        - TCP socket stream
    - HTTP protocol
    - HTTP Server Request Handle
        - HTTP Request Method
            - GET
            - HEAD
            - POST
            - PUT
            - DELETE
            - CONNECT
            - OPTIONS
            - TRACE
        - Domain
        - Requested path/page
    - HTTPS
    - Browser
    - HTML parsing
    - CSS interpretation
    - Page rendering
