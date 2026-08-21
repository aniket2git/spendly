
---

# PART G - Computer Networks, Security and Mobile Computing

> *The second-largest block in the paper. Layers, protocols, IP addressing and cryptography together carry 8 to 12 marks.*



## G1 Networking Fundamentals



### G1.1 What a network is


A **computer network** is two or more computers connected together so they can **share resources and exchange messages**.

Why build one? To share files, share hardware (one printer for the whole office), communicate (email, chat), share software, and to allow central backup and administration.


> **NOTE: Direct PYQ**
>
> "In a global system of world-wide computer networks, interconnection is essential for which purpose of computations?" Answer key: **Messages for communication**.
>
> The Internet's foundational purpose is the exchange of **messages** between machines. Every other activity - file sharing, transactions, data analysis - is built *on top of* message passing. When a question asks for the *essential* purpose, choose communication.



> **NOTE: Direct PYQ**
>
> "Which of the following are the most essential components a computer system uses for communication over internet?" Answer: **NIC and TCP/IP**.
>
> Reasoning: you need **hardware** to physically connect - the **Network Interface Card** - and you need a **protocol suite** so both ends agree on the rules - **TCP/IP**. A monitor, keyboard, mouse, camera or microphone are peripherals for the *human*, not for network communication.



### G1.2 Types of network by size



| Type | Full form | Coverage | Example |
|---|---|---|---|
| PAN | Personal Area Network | A few metres, around one person | Bluetooth headset, smartwatch |
| LAN | Local Area Network | One building or campus | Office, school computer lab. High speed, low error rate, privately owned |
| MAN | Metropolitan Area Network | One city | Cable TV network, city-wide Wi-Fi |
| WAN | Wide Area Network | Country or worldwide | The INTERNET. Uses leased lines and satellites |
| CAN | Campus Area Network | Several nearby buildings | University campus |
| VPN | Virtual Private Network | Logical, over a public network | Secure tunnel for remote workers |



### G1.3 Topologies


The **topology** is the physical or logical arrangement of the machines.


| Topology | Layout | Advantages | Disadvantages |
|---|---|---|---|
| Bus | All nodes share one backbone cable | Cheap, easy to install, needs least cable | One cable break kills the whole network; collisions; hard to troubleshoot |
| Star | All nodes connect to a CENTRAL hub or switch | Easy to add/remove nodes; one node failing does not affect others; easy fault isolation | The CENTRAL DEVICE is a single point of failure; more cable needed |
| Ring | Each node connects to exactly two others forming a closed loop | Equal access, no collisions with token passing | One node or link failure can break the ring (unless dual ring) |
| Mesh | Every node connects to every other node | Most RELIABLE and fault tolerant; multiple paths | Very expensive; needs n(n-1)/2 links for n nodes |
| Tree | Hierarchy of star networks joined to a backbone | Scalable, easy to manage in segments | Depends on the root; heavy cabling |
| Hybrid | A mix of the above | Flexible | Complex and costly |



> **TIP: The mesh formula**
>
> A **full mesh** with n nodes needs **n(n-1)/2** links (undirected) and each node needs **n-1** ports. For 10 nodes: 10 x 9 / 2 = 45 links.



### G1.4 Transmission media



| Medium | Type | Notes |
|---|---|---|
| Twisted pair (UTP / STP) | Guided | Cheapest, easiest to install. Cat5e/Cat6 Ethernet cable. Susceptible to interference; limited to about 100 m |
| Coaxial cable | Guided | Better shielding than twisted pair; used for cable TV and older Ethernet |
| OPTICAL FIBRE | Guided | Carries light instead of electricity. HIGHEST bandwidth, longest distance, IMMUNE to electromagnetic interference, very secure (hard to tap). Expensive and fragile |
| Radio waves | Unguided | Omnidirectional, penetrates walls. Wi-Fi, AM/FM |
| Microwave | Unguided | Line-of-sight, high frequency. Terrestrial towers and satellites |
| Infrared | Unguided | Short range, cannot pass through walls. TV remotes |



#### How optical fibre works - and the PYQ on it

An optical fibre has a **core** surrounded by a **cladding**. Light entering the core hits the boundary and is reflected back in, again and again, and so travels along the fibre.

For this to happen the light must undergo **Total Internal Reflection (TIR)**, and TIR requires that light travels from a **denser** medium into a **rarer** medium at an angle greater than the critical angle. "Denser" optically means a **higher refractive index**.


> **NOTE: PYQ worked out**
>
> "The refractive index of the core of an optical fibre is greater than that of cladding because:" Answer: **the light gets totally internally reflected into the core.**
>
> The chain of logic: refractive index of core > refractive index of cladding, therefore total internal reflection can occur at the core-cladding boundary, therefore the light stays trapped inside the core and travels the length of the fibre with almost no loss. If the cladding had the higher index, light would simply **refract out into the cladding** and be lost - which is exactly what the wrong option describes.



### G1.5 Networking devices



| Device | OSI layer | Function |
|---|---|---|
| Repeater | Physical (1) | Regenerates and amplifies a weakened signal to extend distance. No filtering |
| Hub | Physical (1) | A multiport repeater. BROADCASTS incoming data to ALL ports. One collision domain, so it is inefficient. "Dumb" device |
| Bridge | Data Link (2) | Connects two LAN segments and filters traffic using MAC addresses. Two ports typically |
| SWITCH | Data Link (2) | A multiport bridge. Learns MAC addresses and forwards a frame only to the correct port. Each port is its own collision domain. Full duplex |
| ROUTER | Network (3) | Connects DIFFERENT networks and forwards packets using IP addresses and a routing table. Breaks up broadcast domains |
| Gateway | All layers (up to 7) | Connects two networks using DIFFERENT protocols; performs protocol translation |
| Brouter | 2 and 3 | Bridge plus router |
| NIC | 1 and 2 | Network Interface Card - the hardware giving a computer its MAC address and physical connection |
| Modem | Physical (1) | MOdulator-DEModulator: converts digital to analog and back for telephone/cable lines |
| Access Point (AP) | 2 | Lets wireless devices join a wired network |
| Firewall | 3 to 7 | Filters traffic based on security rules |



> **TIP: Hub vs Switch vs Router in one line each**
>
> **Hub** shouts to everyone. **Switch** speaks only to the right person in the same room. **Router** carries the message to a different room (network) altogether.



### G1.6 Transmission modes and switching



| Mode | Description |
|---|---|
| Simplex | One direction only. Keyboard to computer, TV broadcast |
| Half duplex | Both directions but only ONE at a time. Walkie-talkie |
| Full duplex | Both directions SIMULTANEOUSLY. Telephone |



| Switching | How it works | Notes |
|---|---|---|
| Circuit switching | A dedicated physical path is SET UP before any data flows, held for the whole session, then torn down | Telephone network. Guaranteed bandwidth, but wasteful when idle. SETUP IS REQUIRED |
| Message switching | The whole message is stored and forwarded hop by hop | Obsolete |
| Packet switching - Datagram | Each packet is routed INDEPENDENTLY and may take a different path; packets may arrive out of order. NO connection setup | The Internet (IP) |
| Packet switching - Virtual circuit | A logical path is established first, then all packets follow it in order | Frame Relay, ATM, MPLS. SETUP IS REQUIRED |



> **NOTE: PYQ worked out**
>
> "Which of the following statements is true?" The correct option was **"Circuit setup is required in a virtual-circuit network."**
>
> Reasoning: a **virtual circuit** establishes a logical connection (a setup phase assigning a virtual circuit identifier) before data transfer, so setup IS required. A **datagram** network sends each packet independently with **no setup at all**. Therefore the statements "setup is not required in both", "setup is required in both" and "setup is required in a datagram network" are all false.



## G2 The OSI and TCP/IP Reference Models



### G2.1 Why we need layers


Sending data across a network involves dozens of separate problems: which wire, which voltage, how to find the destination, what to do if a packet is lost, how to encrypt it, how to display it. Solving all of that in one program would be unmanageable.

So the work is divided into **layers**. Each layer does one job, uses the service of the layer below, and provides a service to the layer above.


### G2.2 The OSI model - 7 layers


Memorise from the top down: **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing (Application, Presentation, Session, Transport, Network, Data Link, Physical).

Or bottom up: **P**lease **D**o **N**ot **T**hrow **S**ausage **P**izza **A**way.


| Layer | Number | Data unit | Main responsibilities | Devices / Protocols |
|---|---|---|---|---|
| Application | 7 | Data / Message | Interface to the user's application; network services | HTTP, FTP, SMTP, DNS, TELNET, SNMP, DHCP |
| Presentation | 6 | Data | TRANSLATION (ASCII/EBCDIC), ENCRYPTION and decryption, COMPRESSION. Also called the syntax layer | SSL/TLS, JPEG, MPEG, ASCII |
| Session | 5 | Data | Establishing, managing and terminating SESSIONS; dialog control; SYNCHRONISATION and checkpointing | NetBIOS, RPC, PPTP |
| Transport | 4 | SEGMENT (TCP) / Datagram (UDP) | END-TO-END delivery, segmentation and reassembly, PORT addressing, FLOW CONTROL, ERROR CONTROL, connection management | TCP, UDP, SCTP |
| Network | 3 | PACKET | LOGICAL (IP) addressing, ROUTING, path determination, fragmentation, CONGESTION CONTROL, internetworking | IP, ICMP, IGMP, ARP, RARP, OSPF, RIP, BGP. ROUTER |
| Data Link | 2 | FRAME | Physical (MAC) addressing, framing, error detection (CRC), flow control on a single link, media access control | Ethernet, PPP, HDLC, Token Ring. SWITCH, BRIDGE, NIC |
| Physical | 1 | BIT | Transmission of a RAW BIT STREAM over the medium; voltages, cables, pins, data rate, topology, transmission mode | Cables, HUB, REPEATER, connectors |


- **Data Link sublayers** - **LLC (Logical Link Control)** handles flow and error control; **MAC (Media Access Control)** handles access to the shared medium.


> **NOTE: Very important PYQ - read the note about the answer key**
>
> "Which layer is responsible for sending data as a bit stream?" The official answer key gave **Data link layer**.
>
> Standard textbook theory says the **PHYSICAL layer** is the one that transmits a raw **bit stream** over the medium - that is its textbook definition. The Data Link layer works with **frames**.
>
> How to handle this in the exam: if both "Physical layer" and "Data link layer" appear and the question says "**raw** bit stream" or "**transmission over the medium**", choose **Physical**. This particular paper chose Data Link, probably reasoning that the data link layer is what *hands* the bit stream down for transmission. Be aware of the discrepancy and pick Physical unless the wording clearly matches the data-link role.



### G2.3 The TCP/IP model - 4 layers



| TCP/IP layer | Equivalent OSI layers | Data unit | Protocols |
|---|---|---|---|
| Application | Application + Presentation + Session (5,6,7) | Data | HTTP, FTP, SMTP, DNS, TELNET, SNMP |
| Transport (Host-to-Host) | Transport (4) | Segment | TCP, UDP |
| INTERNET | Network (3) | PACKET | IP, ICMP, ARP, RARP, IGMP |
| Network Access (Link) | Data Link + Physical (1,2) | Frame / Bit | Ethernet, Wi-Fi, PPP |



> **NOTE: Direct PYQ**
>
> "The internet layer in TCP/IP model is associated with ______ data." Answer: **packets**.
>
> Lock in the data-unit chain: **Transport = segments, Internet/Network = packets, Data Link = frames, Physical = bits.** This exact mapping is asked in some form almost every year.



### G2.4 Which function belongs to which layer


This is the trap examiners rely on most, because several functions appear at more than one layer.


| Function | Layer(s) |
|---|---|
| Physical / MAC addressing | Data Link |
| Logical / IP addressing | Network |
| Port addressing | Transport |
| Routing | Network |
| Framing | Data Link |
| Fragmentation and reassembly of packets | Network |
| Segmentation and reassembly | Transport |
| Congestion control | Network (also handled by TCP at Transport) |
| FLOW CONTROL | Data Link (per link) AND Transport (end to end) |
| ERROR CONTROL | Data Link (per link) AND Transport (end to end) |
| End-to-end / process-to-process delivery | Transport |
| Encryption and compression | Presentation |
| Dialog control and synchronisation | Session |



> **NOTE: PYQ worked out**
>
> "Which of the following is NOT a network layer function?" Options: **Error control and flow control**, Intra-routing, Routing, Congestion control. Answer: **Error control and flow control**.
>
> Reasoning: routing, intra-domain routing and congestion control are all core Network-layer duties. **Error control and flow control** are the classic responsibilities of the **Data Link layer** (hop by hop) and the **Transport layer** (end to end) - not the Network layer. IP itself is a "best-effort" protocol: it does no flow control and only a header checksum.



> **NOTE: Direct PYQ**
>
> "What feature of the transport layer prevents data loss?" Options: Encryption, Packet switching, Addressing, **Flow control**. Answer: **Flow control**.
>
> Definition to remember: **flow control** stops a fast sender from overwhelming a slow receiver's buffer - if the buffer overflows, data is lost. TCP implements it with a **sliding window** and the receiver's advertised window size. Encryption is Presentation-layer, packet switching is Network-layer, and addressing does not prevent loss.



## G3 Data Link Layer - Error and Flow Control



### G3.1 Error detection



| Method | How it works | Strength |
|---|---|---|
| Parity check (VRC) | Add one bit so the total number of 1s is even (even parity) or odd | Detects all single-bit errors, but misses any even number of errors |
| Two-dimensional parity (LRC) | Parity on rows and columns | Better; can detect and even correct some errors |
| CHECKSUM | Sum all the data words using 1's complement arithmetic and send the complement of the sum. Receiver adds everything; the result should be all 1s | Used by TCP, UDP and IP headers. Simple but weaker |
| CRC (Cyclic Redundancy Check) | Treat the data as a polynomial, divide by a generator polynomial, append the remainder | MOST POWERFUL detection method. Used in Ethernet, Wi-Fi. Detects all burst errors shorter than the CRC length |
| Hamming code | Adds redundant parity bits at power-of-two positions | Can DETECT AND CORRECT a single-bit error (Forward Error Correction) |


- **Hamming distance** - The number of bit positions in which two codewords differ. To detect d errors you need a minimum distance of d+1; to correct d errors you need 2d+1.
- **Single-bit error** - Only one bit flipped.
- **Burst error** - Two or more consecutive bits corrupted. More common in real transmission.


### G3.2 Flow control protocols and sliding window



| Protocol | Window size | Behaviour |
|---|---|---|
| Stop-and-Wait | 1 | Send one frame, wait for its acknowledgement, then send the next. Very simple, very inefficient on long links |
| Go-Back-N ARQ | Sender window N, receiver window 1 | The receiver accepts frames only in order and DISCARDS any out-of-order frame. On a loss, the sender retransmits the lost frame AND every frame after it. Uses CUMULATIVE acknowledgements |
| Selective Repeat ARQ | Sender window N, receiver window N | The receiver BUFFERS out-of-order frames and acknowledges them individually. Only the actually lost frame is retransmitted. More efficient, but needs receiver buffering and sorting |


- **ARQ** - Automatic Repeat Request - error control using acknowledgements and retransmission.
- **Piggybacking** - Carrying an acknowledgement inside an outgoing data frame to save bandwidth.
- **Sequence number bits** - Go-Back-N with window N needs sequence numbers up to N+1, so ceil(log2(N+1)) bits. Selective Repeat needs 2N distinct numbers.


> **NOTE: PYQ worked out**
>
> "How does the receiver handle out-of-order frames in Selective Repeat?" Answer: **Buffers them until all missing frames arrive.**
>
> This is the single defining difference between the two sliding-window protocols. In **Go-Back-N** the receiver *discards* out-of-order frames. In **Selective Repeat** the receiver *keeps* (buffers) them, delivers them to the upper layer only once the gap is filled, and acknowledges each one separately.
>
> The wrong options describe the other protocol: "requests retransmission of all frames" and "sends a cumulative acknowledgment" are Go-Back-N behaviour; "discards them immediately" is Stop-and-Wait / Go-Back-N behaviour.



### G3.3 Media access control



| Protocol | Idea |
|---|---|
| ALOHA (pure) | Transmit whenever you have data; if there is a collision, wait a random time and retry. Max efficiency 18.4% |
| Slotted ALOHA | Transmit only at the start of a time slot. Max efficiency 36.8% |
| CSMA | Carrier Sense Multiple Access - "listen before you talk" |
| CSMA/CD | Collision Detection. Used in wired ETHERNET. If a collision is detected, stop, send a jam signal, and back off using binary exponential backoff |
| CSMA/CA | Collision AVOIDANCE. Used in WIRELESS (Wi-Fi, 802.11), because a station cannot reliably detect collisions while transmitting. Uses RTS/CTS handshaking and random backoff before sending |
| Token passing | A token circulates; only the holder may transmit. Collision free. Token Ring, FDDI |
| Polling | A primary station asks each secondary in turn |



## G4 Network Layer - IP Addressing and Routing



### G4.1 IPv4 addresses


An **IPv4 address** is a **32-bit** number written as four decimal octets separated by dots, e.g. 192.168.10.5. Each octet ranges from 0 to 255.

Every IP address has two parts: the **network address** (which network) and the **host address** (which machine on that network).


> **NOTE: Direct PYQ**
>
> "Which of the following 4-byte IP addresses are used for internet protocol layer?" Answer: **Network address and host address.**
>
> An IPv4 address is 4 bytes = 32 bits, and it is split into exactly these two logical parts. A **port** address belongs to the Transport layer, and a **MAC** address belongs to the Data Link layer - so any option pairing IP with port or MAC is wrong.



### G4.2 Address classes



| Class | First octet range | Default mask | Network / Host bits | Number of networks | Hosts per network | Use |
|---|---|---|---|---|---|---|
| A | 1 - 126 | 255.0.0.0 (/8) | 8 / 24 | 126 | 16,777,214 | Very large organisations |
| B | 128 - 191 | 255.255.0.0 (/16) | 16 / 16 | 16,384 | 65,534 | Medium organisations |
| C | 192 - 223 | 255.255.255.0 (/24) | 24 / 8 | 2,097,152 | 254 | Small networks |
| D | 224 - 239 | - | - | - | - | MULTICASTING |
| E | 240 - 255 | - | - | - | - | Reserved / experimental |



#### Special addresses

- **127.0.0.0 - 127.255.255.255** - **Loopback**. 127.0.0.1 is "localhost" - this machine itself.
- **All host bits 0** - The **network address** - identifies the network itself, not assignable to a host.
- **All host bits 1** - The **broadcast address** - reaches every host on that network, not assignable.
- **Private ranges** - 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16. Not routable on the Internet; used behind NAT.
- **0.0.0.0** - "This host / any address".
- **169.254.x.x** - APIPA - a self-assigned address when DHCP fails.


### G4.3 Subnetting - the calculations


**Subnetting** borrows bits from the host portion to create smaller networks.


*The four formulas you need*
```
Let  n = number of HOST bits (the zeros in the subnet mask)

   Total addresses in the subnet     =  2^n
   Usable HOST addresses            =  2^n - 2
        (subtract 1 for the network address and 1 for the broadcast address)
   Number of subnets from borrowing b bits  =  2^b
   Block size / increment           =  256 - (the interesting octet of the mask)
```



> **NOTE: PYQ worked out - the subnet mask question**
>
> "A network on the internet has a subnet mask of 255.255.240.0. What is the maximum number of hosts it can handle?" Answer: **4094**.
>
> Step 1 - write the mask in binary.
> 255 = 11111111, 255 = 11111111, 240 = 11110000, 0 = 00000000
> So the mask is: 11111111.11111111.11110000.00000000
>
> Step 2 - count the bits.
> Number of 1s (network bits) = 8 + 8 + 4 = **20**. This is a /20 network.
> Number of 0s (host bits) = 32 - 20 = **12**.
>
> Step 3 - apply the formula.
> Total addresses = 2^12 = 4096
> Usable hosts = 2^12 - 2 = 4096 - 2 = **4094**
>
> Why subtract 2? One address has all host bits 0 (the network address) and one has all host bits 1 (the broadcast address). Neither can be given to a machine.
>
> Note the distractor **4096** - that is the total *addresses*, not usable *hosts*. Always read whether the question asks for addresses or hosts.



> **TIP: The mask-to-bits shortcut table**
>



| Mask octet | Binary | 1s contributed | Block size |
|---|---|---|---|
| 255 | 11111111 | 8 | 1 |
| 254 | 11111110 | 7 | 2 |
| 252 | 11111100 | 6 | 4 |
| 248 | 11111000 | 5 | 8 |
| 240 | 11110000 | 4 | 16 |
| 224 | 11100000 | 3 | 32 |
| 192 | 11000000 | 2 | 64 |
| 128 | 10000000 | 1 | 128 |
| 0 | 00000000 | 0 | 256 |



### G4.4 IPv6


- **Size** - **128 bits**, written as eight groups of four hexadecimal digits separated by colons.
- **Why** - IPv4's 4.3 billion addresses ran out.
- **Header** - Simplified, fixed 40 bytes. **No checksum**, no fragmentation by routers.
- **Features** - Built-in IPSec security, auto-configuration, better multicast, flow labels for QoS.
- **No broadcast** - IPv6 uses **multicast and anycast** instead of broadcast.
- **Notation** - Leading zeros in a group may be dropped; one run of all-zero groups may be replaced by `::` (only once).


### G4.5 ARP and related protocols



| Protocol | Full form | Converts |
|---|---|---|
| ARP | Address Resolution Protocol | IP address to MAC address |
| RARP | Reverse ARP | MAC address to IP address (obsolete, replaced by DHCP) |
| ICMP | Internet Control Message Protocol | Error reporting and diagnostics. Used by PING and TRACEROUTE |
| IGMP | Internet Group Management Protocol | Manages multicast group membership |
| DHCP | Dynamic Host Configuration Protocol | Automatically assigns IP address, subnet mask, gateway and DNS to a host |
| NAT | Network Address Translation | Maps many private addresses to one public address |



> **NOTE: PYQ worked out**
>
> "What is the ARP reply's scope in terms of message type?" Answer: **Unicast**.
>
> The mechanism explains it. When host A needs B's MAC address, A does not know who has that IP, so it must ask **everybody** - the ARP **REQUEST is a BROADCAST**. But host B, on hearing the request, now knows exactly who asked (A's MAC and IP were in the request), so it replies directly to A only - the ARP **REPLY is a UNICAST**.
>
> Memorise the pair: **ARP request = broadcast, ARP reply = unicast.**



### G4.6 Routing


- **Routing** - Choosing a path for a packet from source network to destination network.
- **Routing table** - Holds destination network, subnet mask, next hop and metric.
- **Static routing** - Manually configured. Simple and secure, but does not adapt to failures.
- **Dynamic routing** - Routers exchange information automatically and adapt.
- **Default gateway** - Where to send packets whose destination is not in the table.
- **Hop count** - The number of routers a packet crosses.
- **TTL (Time To Live)** - A counter decremented by each router; at 0 the packet is discarded. Prevents infinite loops.


| Algorithm | Type | Metric | Notes |
|---|---|---|---|
| RIP | Distance vector | HOP COUNT, maximum 15 | Simple; slow convergence; suffers count-to-infinity, cured by split horizon and poison reverse |
| OSPF | Link state | COST based on bandwidth | Each router builds a full map and runs DIJKSTRA's algorithm. Fast convergence. Interior gateway protocol |
| BGP | Path vector | Policy based | The routing protocol OF THE INTERNET, used BETWEEN autonomous systems (exterior) |
| EIGRP | Hybrid | Bandwidth and delay | Cisco proprietary |


- **Intra-domain (interior) routing** - Inside one autonomous system: RIP, OSPF.
- **Inter-domain (exterior) routing** - Between autonomous systems: BGP.
- **Unicast** - One sender to one receiver.
- **Broadcast** - One sender to all hosts on the network.
- **Multicast** - One sender to a specific group of receivers.
- **Anycast** - One sender to the nearest of several possible receivers.


## G5 Transport Layer - TCP and UDP



### G5.1 TCP vs UDP - the master comparison



| Point | TCP | UDP |
|---|---|---|
| Full form | Transmission Control Protocol | User Datagram Protocol |
| Connection | CONNECTION-ORIENTED - a connection is set up first | CONNECTIONLESS - just send |
| Reliability | RELIABLE - guaranteed delivery with acknowledgements and retransmission | UNRELIABLE - best effort, no acknowledgements |
| Ordering | Data is delivered IN THE ORDER it was transmitted | No ordering guarantee |
| Flow control | Yes (sliding window) | No |
| Congestion control | Yes | No |
| Error checking | Checksum plus recovery | Checksum only, no recovery |
| Header size | 20 to 60 bytes | 8 bytes - fixed and small |
| Speed | Slower | FASTER |
| Data unit | Segment | Datagram |
| Data from application | Received as a single continuous STREAM of bytes | Treated as separate discrete messages |
| Use cases | Web (HTTP), email (SMTP), file transfer (FTP), remote login | Video/audio streaming, online gaming, DNS, DHCP, TFTP, SNMP, VoIP |



> **NOTE: Two direct PYQs on TCP**
>
> "Which of the following statements is FALSE about TCP?" Answer: **"It is a connection-less protocol."** TCP is definitively **connection-oriented**. The other statements are all true: it uses a three-way handshake, it receives data from the application as a single stream, and it is connection-oriented.
>
> "What does the TCP service model guarantee about the order of data delivery?" Answer: **Data is delivered in the order it is transmitted.** TCP uses sequence numbers to reorder segments that arrive out of order, so the application always sees a correctly ordered byte stream. Note the distractor "Data may arrive out of order and is handled by the application layer" - that describes **UDP**, where the application must sort things out itself.



### G5.2 Ports


A **port number** is a 16-bit number (0 to 65535) identifying a specific process or service on a host.


| Range | Name |
|---|---|
| 0 - 1023 | Well-known ports (reserved for standard services) |
| 1024 - 49151 | Registered ports |
| 49152 - 65535 | Dynamic / private / ephemeral ports |



| Port | Service | Protocol |
|---|---|---|
| 20, 21 | FTP (20 data, 21 control) | TCP |
| 22 | SSH | TCP |
| 23 | TELNET | TCP |
| 25 | SMTP | TCP |
| 53 | DNS | UDP (and TCP for large transfers) |
| 67, 68 | DHCP | UDP |
| 69 | TFTP | UDP |
| 80 | HTTP | TCP |
| 110 | POP3 | TCP |
| 143 | IMAP | TCP |
| 161 | SNMP | UDP |
| 443 | HTTPS | TCP |
| 3306 | MySQL | TCP |


- **Socket** - The combination of **IP address + port number**. It uniquely identifies one endpoint of a connection.


### G5.3 TCP connection management



*The three-way handshake (opening a connection)*
```
   CLIENT                                  SERVER
     |------------- SYN (seq = x) ------------>|
     |<------- SYN + ACK (seq = y, ack = x+1) -|
     |------------- ACK (ack = y+1) ---------->|
                 Connection established
```



*Connection termination - the four-way handshake*
```
     |------------------ FIN ----------------->|
     |<----------------- ACK ------------------|
     |<----------------- FIN ------------------|
     |------------------ ACK ----------------->|
```



#### The RST flag

- **RST (Reset)** - Abruptly **terminates the connection immediately**, without the graceful four-way FIN exchange. Sent when a segment arrives for a port with no listening process, or when a connection is in an invalid state.


> **NOTE: PYQ worked out**
>
> "What happens if a RST (reset) packet is received during the connection management process?" Answer: **The connection is immediately terminated.**
>
> Contrast RST with FIN: **FIN** says "I have finished sending, let us close politely" and starts an orderly shutdown. **RST** says "this connection is invalid, drop it now" - no acknowledgement is expected and any queued data is discarded. So the connection does not remain active, the receiver does not send another SYN, and the sender stops retransmitting.



#### TCP header flags

- **URG** - Urgent pointer is valid.
- **ACK** - Acknowledgement number is valid.
- **PSH** - Push the data to the application immediately.
- **RST** - Reset the connection.
- **SYN** - Synchronise sequence numbers (connection setup).
- **FIN** - No more data from sender (connection close).


### G5.4 TCP congestion control


**Congestion** is when too much data is injected into the network, so routers' queues overflow and packets are dropped.


| Phase | Behaviour |
|---|---|
| Slow Start | The congestion window (cwnd) begins at 1 MSS and DOUBLES every round trip time (it increases by 1 MSS per acknowledgement received, which doubles the window each RTT). This is EXPONENTIAL growth, despite the name |
| Congestion Avoidance (AIMD) | Once cwnd reaches the slow-start threshold, growth becomes LINEAR - increasing by roughly 1 MSS per RTT (additive increase) |
| Congestion Detection | On packet loss (timeout or 3 duplicate ACKs), the threshold is halved and the window is cut (multiplicative decrease) |
| Fast Retransmit / Fast Recovery | Three duplicate ACKs trigger immediate retransmission without waiting for a timeout |



> **NOTE: PYQ worked out - a very common trap**
>
> "Which of the following statements is true about slow start phase of the TCP congestion control?" Answer: **Congestion window approximately doubles every round trip time.**
>
> Why the tempting options are wrong:
> "increases by 1 MSS every round trip time" - that describes the **congestion avoidance** phase, not slow start.
> "increases by 2 MSS on every successful acknowledgement" - it increases by **1** MSS per acknowledgement.
> "doubles on every successful acknowledgement" - it doubles per **RTT**, not per acknowledgement.
>
> The subtle mechanism: the window increases by 1 MSS for **each ACK received**. Since a window of N segments produces N ACKs in one RTT, the window grows from N to 2N over that RTT. Hence "increases by 1 MSS per ACK" and "doubles every RTT" describe the same behaviour - and the exam wants the "doubles every RTT" phrasing.


- **MSS** - Maximum Segment Size.
- **RTT** - Round Trip Time.
- **Silly window syndrome** - Tiny segments being sent inefficiently; cured by Nagle's algorithm (sender side) and Clark's solution (receiver side).


## G6 Application Layer Protocols



### G6.1 The protocols you must know



| Protocol | Full form | Purpose | Port |
|---|---|---|---|
| HTTP | HyperText Transfer Protocol | Transfers web pages. STATELESS request-response protocol | 80 |
| HTTPS | HTTP Secure | HTTP over SSL/TLS - encrypted | 443 |
| FTP | File Transfer Protocol | Transfers files; uses TWO connections (control and data) | 21, 20 |
| TFTP | Trivial FTP | Simple file transfer over UDP, no authentication | 69 |
| SMTP | Simple Mail Transfer Protocol | SENDING / PUSHING email | 25 |
| POP3 | Post Office Protocol v3 | RETRIEVING email; normally downloads and deletes from the server | 110 |
| IMAP | Internet Message Access Protocol | Retrieving email while keeping it on the server; supports folders and multiple devices | 143 |
| DNS | Domain Name System | Translates a DOMAIN NAME into an IP address | 53 |
| DHCP | Dynamic Host Configuration Protocol | Automatically assigns IP configuration | 67, 68 |
| TELNET | Terminal Network | Remote login, UNENCRYPTED - insecure | 23 |
| SSH | Secure Shell | Encrypted remote login - the secure replacement for Telnet | 22 |
| SNMP | Simple Network Management Protocol | Monitoring and managing network devices | 161 |


- **DNS hierarchy** - Root, then Top Level Domains (.com, .org, .in), then second-level domains, then subdomains. Resolution can be **recursive** or **iterative**.
- **URL** - **Uniform Resource Locator** - protocol://host:port/path?query#fragment
- **Cookie** - A small text file stored by the browser to give the stateless HTTP protocol a memory of the user.
- **Proxy server** - An intermediary that forwards requests; provides caching, filtering and anonymity.


## G7 Network Security and Cryptography



### G7.1 The goals of security



| Goal | Meaning |
|---|---|
| Confidentiality | Only authorised people can read the data. Achieved by ENCRYPTION |
| Integrity | The data has not been altered in transit. Achieved by HASHING / message digests |
| Availability | The service is accessible when needed. Threatened by Denial of Service attacks |
| AUTHENTICATION | VERIFYING THE IDENTITY of a user or system - proving you are who you claim to be |
| Authorisation | Deciding what an authenticated user is allowed to do |
| Non-repudiation | The sender cannot later deny having sent the message. Achieved by DIGITAL SIGNATURES |



> **NOTE: Direct PYQ**
>
> "The process of verifying a user's identity is called:" Options: integrity, **authentication**, validation, confidentiality. Answer: **authentication**.
>
> Keep this trio separate: **Authentication** = "who are you?" (proving identity, e.g. password, OTP, fingerprint). **Authorisation** = "what may you do?" (permissions). **Validation** = checking that *data* is in the right format. Authentication is about the *person*, validation is about the *data*.



### G7.2 Encryption terminology


- **Plain text** - The ORIGINAL readable message. This is **the information transformed during encryption** - it is the INPUT.
- **Cipher text** - The scrambled, unreadable output of encryption.
- **Encryption** - Converting plain text into cipher text using a key.
- **Decryption** - Converting cipher text back into plain text.
- **Key** - The secret value that controls the transformation.
- **Cryptanalysis** - The science of breaking ciphers without the key.


> **NOTE: PYQ worked out**
>
> "The information transformed during encryption is ______." Options: encrypted message, coded message, cipher text, **plain text**. Answer: **plain text**.
>
> Read the sentence carefully - it asks what gets **transformed** (i.e. what goes IN), not what comes out. Plain text is transformed *into* cipher text. "Cipher text" is the tempting wrong answer because it is the *result*, not the thing being transformed.



### G7.3 Symmetric vs asymmetric cryptography



| Point | Symmetric key (Private key) | Asymmetric key (Public key) |
|---|---|---|
| Number of keys | ONE shared secret key for both encryption and decryption | TWO mathematically linked keys - a public key and a private key |
| Speed | FAST - suitable for large volumes of data | SLOW - about 1000 times slower |
| Key distribution | THE MAIN PROBLEM: how do you securely share the secret key? | Solved - the public key can be published openly |
| Number of keys for n users | n(n-1)/2 | 2n |
| Algorithms | DES, 3DES, AES, RC4, RC5, Blowfish, IDEA | RSA, Diffie-Hellman, ECC, DSA, ElGamal |



> **NOTE: Direct PYQ**
>
> "Which of the following is NOT a symmetric-key cryptographic algorithm?" Options: AES, RC4, **RSA**, DES. Answer: **RSA**.
>
> RSA (named after Rivest, Shamir and Adleman) is the classic **asymmetric / public-key** algorithm. AES, DES and RC4 are all symmetric.
>
> Memory hook for the asymmetric family: **R**SA, **D**iffie-Hellman, **E**CC, **D**SA, **E**lGamal. Everything else you are likely to see (AES, DES, 3DES, RC4, RC5, Blowfish, IDEA) is symmetric.



#### How public key encryption actually works

This direction confuses most students, so learn it as two separate use cases.


| Goal | Encrypt with | Decrypt with | Why |
|---|---|---|---|
| CONFIDENTIALITY (secrecy) | The RECIPIENT'S PUBLIC key | The RECIPIENT'S PRIVATE key | Anyone can lock a message for you, but only you hold the key that opens it |
| AUTHENTICATION (digital signature) | The SENDER'S PRIVATE key | The SENDER'S PUBLIC key | Only you could have created it, so everyone can verify it came from you |



> **NOTE: Direct PYQ**
>
> "In public key cryptography, which key is used for decrypting a message encrypted with the public key?" Answer: **The recipient's private key.**
>
> The logic: the message was locked with the recipient's **public** key, and a public/private pair is mathematically matched - only the corresponding **private** key can undo it. Another public key cannot, a symmetric key is irrelevant here, and the *sender's* private key belongs to a completely different key pair.



### G7.4 Session keys - the hybrid approach


Symmetric encryption is fast but has a key-distribution problem. Asymmetric encryption solves key distribution but is slow. Real systems (like HTTPS) combine both:

1. Use **asymmetric** cryptography once, to safely agree on a temporary shared key.
2. Use that temporary **symmetric** key for the actual data transfer.

- **Session key** - A **single-use symmetric key generated for one communication session** between end systems, and discarded afterwards. This limits damage if a key is ever compromised.


> **NOTE: Direct PYQ**
>
> "Communication between end systems is encrypted using a key that is commonly referred to as a:" Answer: **session key**.
>
> Why not the others: a "private key" and "public key" belong to a long-lived asymmetric pair, not to one session; "single key" is not standard terminology. The word **session** signals that the key is temporary and specific to this conversation.



### G7.5 Hashing and digital signatures


- **Hash function** - A one-way function producing a fixed-length **message digest** from any input. It is **irreversible** - you cannot get the message back from the digest.
- **Properties** - Deterministic, fast, one-way (pre-image resistant), collision resistant, and any tiny input change produces a completely different digest (avalanche effect).
- **Common algorithms** - MD5 (128-bit, now broken), SHA-1 (160-bit, deprecated), **SHA-256 / SHA-512** (current standard).
- **Used for** - Password storage, file integrity checks, digital signatures, blockchain.
- **Digital signature** - The message digest encrypted with the **sender's private key**. It provides authentication, integrity and non-repudiation - but **not** confidentiality by itself.
- **MAC / HMAC** - Message Authentication Code - a hash computed with a shared secret key.


### G7.6 Digital certificates and PKI


- **Digital certificate** - An electronic document that binds a **public key to an identity**, signed by a trusted third party. Standard format: **X.509**.
- **Certificate Authority (CA)** - The trusted third party that issues and signs certificates - VeriSign, DigiCert, Let's Encrypt.
- **PKI** - **Public Key Infrastructure** - the whole framework of CAs, certificates, registration authorities and revocation lists that makes public keys trustworthy.
- **Certificate contents** - Subject name, public key, issuer (CA) name, validity period, serial number, and the CA's digital signature.


> **NOTE: PYQ worked out (this question appeared in Hindi)**
>
> "Which of the following describes the use of digital certificates in authentication?" Answer: **They verify the identity of entities using Public Key Infrastructure (PKI).**
>
> Why the others are wrong: certificates do **not** store user passwords; they do **not** compress large files (that is unrelated to security); and they do **not** themselves encrypt the data transmission - they authenticate the *identity* so that the keys used for encryption can be trusted. Encryption of the traffic is done afterwards with session keys.



### G7.7 Attacks and defences



| Attack | Description |
|---|---|
| Passive attack | Eavesdropping - traffic analysis, release of message contents. Hard to detect, easy to prevent with encryption |
| Active attack | Modification - masquerade, replay, message modification, denial of service. Hard to prevent, easier to detect |
| Man-in-the-Middle | An attacker sits between two parties, relaying and possibly altering messages |
| Denial of Service (DoS) / DDoS | Flooding a service so legitimate users cannot reach it |
| Phishing | Fake emails or websites tricking users into revealing credentials |
| SQL injection | Inserting malicious SQL through an input field. Prevented by parameterised queries |
| Cross-Site Scripting (XSS) | Injecting malicious JavaScript into a web page viewed by others |
| Brute force | Trying every possible key or password |
| Replay attack | Capturing and re-sending a valid message. Prevented by timestamps and nonces |



| Malware | Behaviour |
|---|---|
| Virus | Attaches itself to a host file and needs a user action to spread |
| Worm | SELF-REPLICATING; spreads across networks without user action |
| Trojan horse | Disguises itself as useful software while doing something harmful |
| Ransomware | Encrypts the victim's files and demands payment |
| Spyware / Keylogger | Secretly records activity or keystrokes |
| Rootkit | Hides deep in the OS to conceal an intruder's presence |
| Adware | Displays unwanted advertisements |
| Botnet | A network of compromised machines controlled remotely |


- **Firewall** - Filters traffic between networks. **Packet filtering** examines headers; **stateful inspection** tracks connections; **application/proxy** firewalls inspect content.
- **IDS / IPS** - Intrusion Detection System (alerts) / Intrusion Prevention System (blocks).
- **VPN** - Creates an encrypted tunnel over a public network. Uses IPSec or SSL/TLS.
- **SSL / TLS** - Secure Sockets Layer / Transport Layer Security - operates between Transport and Application layers to secure HTTP into HTTPS.
- **Risk management methodologies** - **Acceptance** of threats, **Avoidance** of threats, **Transfer** of risks (insurance), **Mitigation/reduction**. Note that "risk **generation**" is not a methodology - it appeared as a distractor in one paper.


> **NOTE: Direct PYQ**
>
> "Which of the following is NOT a risk management methodology?" Options: Acceptance of threats, **Risk generation**, Avoidance of threats, Transfer of risks. Answer: **Risk generation**. The four genuine strategies are avoid, accept, transfer and mitigate. Nobody *generates* risk as a management strategy.



## G8 Wireless and Mobile Computing



### G8.1 GSM architecture



| Term | Full form | Role |
|---|---|---|
| MS | Mobile Station | The handset plus SIM |
| BTS | BASE TRANSCEIVER STATION | The actual radio equipment at the tower - transmits and receives radio signals to and from mobile stations |
| BSC | Base Station Controller | Controls several BTSs; manages radio channels and handovers |
| MSC | Mobile Switching Centre | The telephone exchange of the mobile network; routes calls |
| HLR | HOME LOCATION REGISTER | The PERMANENT central database of all subscribers of that network - identity, subscribed services, and the current location area |
| VLR | VISITOR LOCATION REGISTER | A TEMPORARY database of the subscribers currently in this MSC's area. The VLR is responsible for informing the HLR about location changes |
| AuC | Authentication Centre | Holds the secret keys used to authenticate SIMs |
| EIR | Equipment Identity Register | Database of IMEI numbers; blocks stolen handsets |



> **NOTE: Direct PYQ**
>
> "BTS stands for ______." Answer: **Base Transceiver Station**.
>
> Watch the spelling of the distractors: "Base Transfer Station", "Basic Transfer System" and "Basic Transceiver Station" are all wrong. It is **Base** (not Basic) **Transceiver** (not Transfer) **Station**. The word *transceiver* = transmitter + receiver, which is exactly what the tower equipment does.



> **NOTE: PYQ worked out - HLR and VLR**
>
> "Which of the following statements is true about Home Location Register (HLR) and Visitor Location Register (VLR)?" Answer: **VLR is responsible for the MS (Mobile Station) to inform the HLR about location changes.**
>
> The mechanism: as you move, you register with a new **VLR**. That VLR then updates the **HLR** so the home network always knows which VLR is currently serving you. When someone calls you, the network queries your HLR, which points to the current VLR, which knows your precise location area.
>
> So the direction of reporting is **VLR to HLR**, never HLR to VLR. Any option reversing this, or saying the VLR is "not responsible", is wrong.



### G8.2 Handover (handoff)


**Handover** is transferring an ongoing call or data session from one cell/channel to another as the user moves, without dropping the connection.


| Type | Meaning |
|---|---|
| Intra-cell handover | Change of channel within the same cell |
| Inter-cell / Intra-BSC handover | Between two cells controlled by the same BSC |
| Inter-BSC handover | Between cells under different BSCs |
| Inter-MSC handover | Between cells under different MSCs |
| Hard handover | The old link is broken BEFORE the new one is made - a brief interruption. Used in GSM |
| Soft handover | The new link is established BEFORE the old one is released - no interruption. Used in CDMA |
| INTER-SYSTEM handover | Handover between two DIFFERENT network types - for example from a SATELLITE network to a TERRESTRIAL CELLULAR network |
| Gateway handover | In satellite systems, a change of the gateway (earth station) serving the connection |
| Intra-satellite handover | Between two spot beams of the SAME satellite |
| Inter-satellite handover | Between two different satellites |



> **NOTE: Direct PYQ**
>
> "______ is the handover from a satellite network to a terrestrial cellular network." Answer: **Inter system handover**.
>
> The key word is **system** - two different *systems* (satellite and terrestrial) are involved. Gateway, intra-satellite and inter-satellite handovers all take place *within* the satellite system.



### G8.3 Mobile IP


Mobile IP lets a device keep its IP address while moving between networks.


| Term | Meaning |
|---|---|
| MN - Mobile Node | The device that moves between networks |
| HA - HOME AGENT | A router on the mobile node's HOME network. It keeps track of where the MN currently is and tunnels packets to it |
| FA - FOREIGN AGENT | A router on the network the MN is CURRENTLY VISITING. It is the END OF THE TUNNEL - it receives the tunnelled packets and delivers them to the MN |
| COA - Care Of Address | The MN's current address in the visited network. It can be a foreign-agent COA or a co-located COA obtained via DHCP |
| CN - Correspondent Node | The other party communicating with the MN |
| Home address | The MN's permanent address on its home network |
| Tunnelling / Encapsulation | The HA wraps the original packet inside a new one addressed to the COA |
| Triangular routing | Packets go CN to HA to MN, but the reply goes MN directly to CN - an inefficient triangle |



> **NOTE: PYQ worked out**
>
> "______ is the address of the current tunnel endpoint for MN that can be chosen via DHCP." Answer: **FA (Foreign Agent)**.
>
> Reasoning: the tunnel runs from the **Home Agent** (the start) to the current point of attachment (the end). The **Foreign Agent** sits in the visited network and terminates that tunnel, so it is the **tunnel endpoint**. Its address can be learned dynamically, including via DHCP.
>
> Careful with **COA** as a distractor - the COA is the *address value*, whereas the question asks for the **entity** acting as the tunnel endpoint. HA is the tunnel *start*, and CN is the far-end correspondent, not part of the tunnel at all.



### G8.4 Wireless standards and technologies



| Standard / Term | Description |
|---|---|
| IEEE 802.3 | Ethernet (wired) |
| IEEE 802.11 | Wireless LAN - Wi-Fi. Variants: 802.11a/b/g/n/ac/ax |
| IEEE 802.15 | Bluetooth / WPAN |
| IEEE 802.16 | WiMAX - wireless MAN |
| MIMO | MULTIPLE INPUT MULTIPLE OUTPUT - uses several antennas at both transmitter and receiver to send parallel data streams. Improves SIGNAL RANGE, RELIABILITY and throughput via spatial multiplexing and diversity |
| WEP | Wired Equivalent Privacy - the original, now BROKEN, Wi-Fi security |
| WPA / WPA2 / WPA3 | Successively stronger Wi-Fi security standards |
| SSID | The network name broadcast by an access point |
| TDMA | Time Division Multiple Access - users share a channel in time slots |
| FDMA | Frequency Division Multiple Access - users get different frequency bands |
| CDMA | Code Division Multiple Access - all users share the whole band, separated by unique codes |
| OFDM | Orthogonal Frequency Division Multiplexing - splits the channel into many closely spaced subcarriers. Used in 4G/5G and modern Wi-Fi |



> **NOTE: Direct PYQ**
>
> "Which technology is commonly used in Wi-Fi to enhance signal range and reliability?" Answer: **MIMO (Multiple Input Multiple Output)**.
>
> Why the others fail: **WEP** is a (broken) *security* protocol, not a range technology. **TDMA** and **CDMA** are *channel access* methods used in cellular networks, not the Wi-Fi range enhancer. MIMO uses multiple antennas to exploit multipath reflections instead of suffering from them - which is precisely what improves both range and reliability.



#### Mobile generations


| Generation | Key feature |
|---|---|
| 1G | Analog voice only |
| 2G | Digital voice, SMS. GSM, CDMA |
| 2.5G | GPRS, EDGE - basic data |
| 3G | Mobile internet, video calls. UMTS, WCDMA |
| 4G | LTE. High-speed broadband, all-IP network |
| 5G | Very high speed, very low latency, massive IoT connectivity |

