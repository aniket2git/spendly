
---

# PART 7 - Computer Networks, Security and Mobile Computing

> *Weightage: 9 to 12 marks in DSSSB, 8 to 14 expected. Layer functions, IP addressing and cryptography are the reliable scorers.*



## 7.1 Fundamentals, Topologies and Devices



> **WEIGHTAGE: 2-3 marks | Device-to-layer mapping is a repeat favourite | Priority CRITICAL**



### 7.1.1 Questions



**Q. [PYQ] Which of the following are the most essential components a computer system uses for communication over internet?**

- (a) Applications and mouse
- (b) Monitor and keyboard
- (c) **NIC and TCP/IP  <-- CORRECT**
- (d) Camera and microphone

> **Why:** You need **hardware** to connect physically (Network Interface Card) and a **protocol suite** so both ends agree on the rules (TCP/IP). Monitors, keyboards and cameras are peripherals for the human, not for networking.



**Q. [EXPECTED] [TRAP] Which topology needs the least cable but fails completely if the backbone breaks?**

- (a) Star
- (b) Ring
- (c) **Bus  <-- CORRECT**
- (d) Mesh

> **Why:** **Bus**: cheapest, least cable, but one cable fault kills the whole network and collisions are frequent. **Star**: easy fault isolation, but the central hub/switch is a single point of failure. **Mesh**: most reliable, needs **n(n-1)/2** links.



**Q. [EXPECTED] [NUMERICAL] How many cables are needed for a full mesh network with 8 nodes?**

- (a) 64
- (b) 56
- (c) **28  <-- CORRECT**
- (d) 16

> **Why:** n(n-1)/2 = 8 x 7 / 2 = **28** links, and each node needs n-1 = 7 ports. The quadratic growth is why full mesh is rare in practice.



**Q. [EXPECTED] [TRAP] A hub differs from a switch in that a hub:**

- (a) works at the network layer
- (b) **broadcasts incoming data to all ports, creating one collision domain  <-- CORRECT**
- (c) filters traffic by IP address
- (d) connects different networks

> **Why:** A **hub** is a multiport repeater (Physical layer, layer 1) that blindly floods every port. A **switch** (Data Link, layer 2) learns MAC addresses and forwards a frame only to the correct port, giving each port its own collision domain.



**Q. [EXPECTED] Which device connects two different networks and forwards packets using IP addresses?**

- (a) Hub
- (b) Switch
- (c) Bridge
- (d) **Router  <-- CORRECT**

> **Why:** A **router** works at the **Network layer (3)** using a routing table, and it separates broadcast domains. A **gateway** goes further, translating between different protocols across all layers.



**Q. [EXPECTED] At which OSI layer does a switch operate?**

- (a) Layer 1
- (b) **Layer 2  <-- CORRECT**
- (c) Layer 3
- (d) Layer 4

> **Why:** Switch and bridge = **Data Link (2)**, using MAC addresses. Hub and repeater = **Physical (1)**. Router = **Network (3)**. NIC spans 1 and 2.



**Q. [PYQ] The refractive index of the core of an optical fibre is greater than that of cladding because:**

- (a) the light gets reflected at the entrance end of the optical fibre
- (b) **the light gets totally internally reflected into the core  <-- CORRECT**
- (c) the light gets restricted at the entrance end
- (d) the light gets refracted into cladding

> **Why:** **Total internal reflection** requires light to travel from a denser medium (higher refractive index) into a rarer one at greater than the critical angle. If the cladding had the higher index, light would simply refract out and be lost.



**Q. [EXPECTED] Which transmission medium is immune to electromagnetic interference?**

- (a) Twisted pair
- (b) Coaxial cable
- (c) **Optical fibre  <-- CORRECT**
- (d) Radio waves

> **Why:** Fibre carries **light**, not electric current, so EMI cannot affect it. It also offers the highest bandwidth, longest range and best security (very hard to tap) - at higher cost and greater fragility.



**Q. [PYQ] [TRAP] Which of the following statements is true?**

- (a) Circuit setup is not required in both a datagram network and virtual-circuit network.
- (b) Circuit setup is required in both.
- (c) **Circuit setup is required in a virtual-circuit network.  <-- CORRECT**
- (d) Circuit setup is required in a datagram network.

> **Why:** A **virtual circuit** establishes a logical path (assigning a VC identifier) before data flows. A **datagram** network routes each packet independently with **no setup at all**, which is how IP works.



**Q. [EXPECTED] Half duplex transmission means:**

- (a) data flows in one direction only
- (b) **data flows in both directions but only one at a time  <-- CORRECT**
- (c) data flows both ways simultaneously
- (d) no data flows

> **Why:** **Simplex** = one direction only (TV broadcast). **Half duplex** = both directions alternately (walkie-talkie). **Full duplex** = both simultaneously (telephone).



## 7.2 OSI and TCP/IP Models



> **WEIGHTAGE: 3-4 marks | Data units and layer functions appear every year | Priority CRITICAL**



### 7.2.1 Questions



**Q. [PYQ] The internet layer in the TCP/IP model is associated with ______ data.**

- (a) segments
- (b) frames
- (c) bytes
- (d) **packets  <-- CORRECT**

> **Why:** Lock the chain in memory: **Transport = segments, Internet/Network = packets, Data Link = frames, Physical = bits.** Some form of this is asked almost every year.



**Q. [PYQ] Which of the following are networking transport layer protocols?**

- (a) FTP and DNS
- (b) Telnet and ICMP
- (c) **TCP, UDP and SCTP  <-- CORRECT**
- (d) ARP and RARP

> **Why:** FTP, DNS and Telnet are **Application** layer; ICMP, ARP and RARP are **Network** layer. Only TCP, UDP and SCTP are Transport.



**Q. [PYQ] [TRAP] Which of the following is NOT a network layer function?**

- (a) **Error control and flow control  <-- CORRECT**
- (b) Intra-routing
- (c) Routing
- (d) Congestion control

> **Why:** Routing, intra-domain routing and congestion control are all Network-layer duties. **Error and flow control** belong to the **Data Link** layer (hop by hop) and the **Transport** layer (end to end). IP itself is best-effort with only a header checksum.



**Q. [PYQ] What feature of the transport layer prevents data loss?**

- (a) Encryption
- (b) Packet switching
- (c) Addressing
- (d) **Flow control  <-- CORRECT**

> **Why:** **Flow control** stops a fast sender from overrunning a slow receiver's buffer - buffer overflow is exactly how data would be lost. TCP implements it with a **sliding window** and the receiver's advertised window size.



**Q. [PYQ] [TRAP] Which layer is responsible for sending data as a bit stream?**

- (a) Presentation layer
- (b) Network layer
- (c) Physical layer
- (d) **Data link layer  <-- CORRECT**

> **Why:** **KEY NOTE.** This paper's key said Data Link. Standard theory assigns the **raw bit stream over the medium** to the **PHYSICAL** layer; the Data Link layer deals in **frames**. If the question says "raw bit stream" or "over the transmission medium", answer **Physical**.



**Q. [EXPECTED] Encryption and compression are performed at which OSI layer?**

- (a) Application
- (b) **Presentation  <-- CORRECT**
- (c) Session
- (d) Transport

> **Why:** The **Presentation** layer (6) handles translation (ASCII/EBCDIC), **encryption/decryption** and **compression** - it is also called the syntax layer. The **Session** layer (5) does dialog control, synchronisation and checkpointing.



**Q. [EXPECTED] Port addressing is a function of which layer?**

- (a) Network
- (b) Data Link
- (c) **Transport  <-- CORRECT**
- (d) Application

> **Why:** **Transport** uses **port** numbers to reach a specific process. Network uses **IP** (logical) addresses; Data Link uses **MAC** (physical) addresses.



**Q. [EXPECTED] How many layers does the TCP/IP model have?**

- (a) 7
- (b) 5
- (c) **4  <-- CORRECT**
- (d) 3

> **Why:** TCP/IP has **4**: Application (= OSI 5,6,7), Transport, Internet, Network Access (= OSI 1,2). OSI has 7. Mnemonic for OSI top-down: **A**ll **P**eople **S**eem **T**o **N**eed **D**ata **P**rocessing.



## 7.3 Data Link Layer, Error and Flow Control



> **WEIGHTAGE: 1-3 marks | Sliding window behaviour is the recurring question | Priority HIGH**



### 7.3.1 Questions



**Q. [PYQ] How does the receiver handle out-of-order frames in Selective Repeat?**

- (a) Requests retransmission of all frames
- (b) Sends a cumulative acknowledgment
- (c) **Buffers them until all missing frames arrive  <-- CORRECT**
- (d) Discards them immediately

> **Why:** This is **the** defining difference: **Go-Back-N discards** out-of-order frames and uses cumulative ACKs; **Selective Repeat buffers** them and acknowledges each individually, retransmitting only what was actually lost.



**Q. [EXPECTED] In Go-Back-N with a window size of 4, if frame 2 is lost, which frames are retransmitted?**

- (a) Only frame 2
- (b) **Frame 2 and all subsequent frames in the window  <-- CORRECT**
- (c) No frames
- (d) All frames from 0

> **Why:** The name says it - the sender "goes back N" and resends the lost frame **plus everything after it**, because the receiver discarded them all. This wastes bandwidth but keeps the receiver simple.



**Q. [EXPECTED] [TRAP] Which error detection method is most powerful and used in Ethernet?**

- (a) Simple parity check
- (b) Checksum
- (c) **CRC  <-- CORRECT**
- (d) Hamming code

> **Why:** **CRC** (Cyclic Redundancy Check) treats data as a polynomial and detects all burst errors shorter than the CRC length. **Checksum** is weaker and used in TCP/UDP/IP headers. **Hamming code** actually *corrects* single-bit errors (forward error correction), which is a different goal.



**Q. [EXPECTED] A simple even parity check fails to detect:**

- (a) single-bit errors
- (b) **errors affecting an even number of bits  <-- CORRECT**
- (c) any errors
- (d) burst errors only

> **Why:** If two bits flip, parity is restored and the error passes unnoticed. This is why CRC replaced parity for serious links.



**Q. [EXPECTED] [TRAP] Which access method is used in wireless LANs rather than wired Ethernet?**

- (a) CSMA/CD
- (b) **CSMA/CA  <-- CORRECT**
- (c) Token passing
- (d) Polling

> **Why:** **CSMA/CD (Collision Detection)** is wired Ethernet. Wireless stations cannot reliably detect collisions while transmitting, so Wi-Fi uses **CSMA/CA (Collision Avoidance)** with RTS/CTS handshaking and random backoff.



**Q. [EXPECTED] [NUMERICAL] The maximum channel efficiency of pure ALOHA is:**

- (a) 36.8%
- (b) **18.4%  <-- CORRECT**
- (c) 50%
- (d) 100%

> **Why:** Pure ALOHA = **18.4%**; slotted ALOHA doubles it to **36.8%** by forcing transmissions to begin at slot boundaries, which halves the vulnerable period.



## 7.4 Network Layer, IP Addressing and Routing



> **WEIGHTAGE: 2-4 marks | A subnetting numerical is very likely | Priority CRITICAL**



### 7.4.1 Questions



**Q. [PYQ] Which of the following 4-byte IP addresses are used for internet protocol layer?**

- (a) Network address and port address
- (b) Network address and MAC address
- (c) **Network address and host address  <-- CORRECT**
- (d) Host address and port address

> **Why:** An IPv4 address is 32 bits = 4 bytes, split logically into **network** and **host** parts. Port belongs to Transport; MAC to Data Link.



**Q. [PYQ] [NUMERICAL] A network has a subnet mask of 255.255.240.0. What is the maximum number of hosts it can handle?**

- (a) 1024
- (b) 3072
- (c) 2048
- (d) **4094  <-- CORRECT**

> **Why:** Write the mask in binary: 240 = 11110000, so network bits = 8+8+4 = **20** (a /20) and host bits = 32-20 = **12**. Usable hosts = **2^12 - 2 = 4094**. Subtract 2 for the network address (all host bits 0) and the broadcast address (all host bits 1). Note the distractor 4096 is the *total* addresses.



**Q. [EXPECTED] [NUMERICAL] How many usable host addresses are available in a /26 network?**

- (a) 64
- (b) **62  <-- CORRECT**
- (c) 32
- (d) 30

> **Why:** Host bits = 32 - 26 = 6, so 2^6 - 2 = **62**. Handy ladder: /24 gives 254, /25 gives 126, /26 gives 62, /27 gives 30, /28 gives 14, /30 gives 2.



**Q. [EXPECTED] Which IP address class is reserved for multicasting?**

- (a) Class A
- (b) Class B
- (c) Class C
- (d) **Class D  <-- CORRECT**

> **Why:** **Class D (224-239)** is multicast; **Class E (240-255)** is reserved/experimental. Class A is 1-126, B is 128-191, C is 192-223, and **127.x.x.x is loopback**.



**Q. [EXPECTED] [TRAP] What is the size of an IPv6 address?**

- (a) 32 bits
- (b) 64 bits
- (c) **128 bits  <-- CORRECT**
- (d) 256 bits

> **Why:** IPv6 is **128 bits**, written as eight groups of four hex digits. It has a fixed 40-byte header, **no checksum**, no router fragmentation, and **no broadcast** - it uses multicast and anycast instead.



**Q. [PYQ] What is the ARP reply's scope in terms of message type?**

- (a) Anycast
- (b) **Unicast  <-- CORRECT**
- (c) Multicast
- (d) Broadcast

> **Why:** **ARP request = BROADCAST** (the sender does not know who owns the IP, so it must ask everyone). **ARP reply = UNICAST** (the responder learned the asker's MAC from the request, so it answers directly). Memorise the pair.



**Q. [EXPECTED] ARP resolves:**

- (a) IP address to domain name
- (b) **IP address to MAC address  <-- CORRECT**
- (c) MAC address to IP address
- (d) domain name to IP address

> **Why:** **ARP**: IP to MAC. **RARP**: MAC to IP (obsolete, replaced by DHCP). **DNS**: domain name to IP. **ICMP**: error reporting and diagnostics (ping, traceroute).



**Q. [EXPECTED] [TRAP] Which routing protocol uses Dijkstra's algorithm and converges quickly?**

- (a) RIP
- (b) **OSPF  <-- CORRECT**
- (c) BGP
- (d) EIGRP

> **Why:** **OSPF** is a **link-state** protocol: every router builds a full topology map and runs Dijkstra. **RIP** is distance-vector using **hop count with a maximum of 15**, and converges slowly. **BGP** is the Internet's **exterior** path-vector protocol used between autonomous systems.



**Q. [EXPECTED] The TTL field in an IP packet prevents:**

- (a) congestion
- (b) **packets circulating forever in routing loops  <-- CORRECT**
- (c) fragmentation
- (d) duplicate delivery

> **Why:** Each router decrements TTL; at zero the packet is discarded and an ICMP time-exceeded message may be returned - which is exactly the mechanism **traceroute** exploits.



## 7.5 Transport Layer - TCP and UDP



> **WEIGHTAGE: 2-4 marks | TCP vs UDP is asked in some form nearly every year | Priority CRITICAL**



### 7.5.1 Questions



**Q. [PYQ] [TRAP] Which of the following statements is FALSE about TCP?**

- (a) It uses a three-way handshake to establish a connection.
- (b) It receives data from application as a single stream.
- (c) It is a connection-oriented protocol.
- (d) **It is a connection-less protocol.  <-- CORRECT**

> **Why:** TCP is definitively **connection-oriented**; **UDP** is the connectionless one. The option list contains both claims, which is your signal for which is being tested.



**Q. [PYQ] What does the TCP service model guarantee about the order of data delivery?**

- (a) **Data is delivered in the order it is transmitted.  <-- CORRECT**
- (b) Data is not guaranteed to arrive in any specific order.
- (c) Data may arrive out of order and is handled by the application layer.
- (d) Data is delivered as fast as possible.

> **Why:** TCP uses **sequence numbers** to reorder segments before delivery. The "handled by the application layer" option describes **UDP**, where the application must sort things out itself.



**Q. [EXPECTED] [TRAP] Which protocol would you choose for live video streaming, and why?**

- (a) TCP, because it is reliable
- (b) **UDP, because low latency matters more than retransmitting lost frames  <-- CORRECT**
- (c) TCP, because it is faster
- (d) SCTP, because it is connectionless

> **Why:** Retransmitting a video frame that is already too late to display is useless and adds delay. **UDP** is used for streaming, VoIP, gaming, **DNS**, DHCP, TFTP and SNMP. Its header is a fixed **8 bytes** versus TCP's 20-60.



**Q. [PYQ] What happens if a RST (reset) packet is received during the connection management process?**

- (a) The receiver sends another SYN packet.
- (b) **The connection is immediately terminated.  <-- CORRECT**
- (c) The sender continues retransmissions.
- (d) The connection remains active.

> **Why:** **RST aborts immediately** and discards queued data - no acknowledgement expected. Contrast **FIN**, which begins a graceful four-way shutdown. RST is sent when a segment arrives for a port with no listener.



**Q. [EXPECTED] The TCP three-way handshake consists of:**

- (a) SYN, ACK, FIN
- (b) **SYN, SYN+ACK, ACK  <-- CORRECT**
- (c) SYN, ACK, RST
- (d) FIN, ACK, FIN

> **Why:** Connection setup is three steps; **termination takes four** (FIN, ACK, FIN, ACK).



**Q. [PYQ] [TRAP] Which statement is true about the slow start phase of TCP congestion control?**

- (a) Congestion window increases by 1 MSS every round trip time.
- (b) **Congestion window approximately doubles every round trip time.  <-- CORRECT**
- (c) Congestion window increases by 2 MSS on every successful acknowledgement.
- (d) Congestion window approximately doubles on every successful acknowledgement.

> **Why:** The window grows by **1 MSS per ACK received**; since a window of N segments produces N ACKs per RTT, the window goes from N to 2N each RTT - i.e. it **doubles per RTT**. "Increases by 1 MSS per RTT" describes the later **congestion avoidance** phase (additive increase).



**Q. [EXPECTED] [NUMERICAL] Which port number does HTTPS use?**

- (a) 80
- (b) **443  <-- CORRECT**
- (c) 22
- (d) 25

> **Why:** Learn the core set: **20/21 FTP, 22 SSH, 23 Telnet, 25 SMTP, 53 DNS, 67/68 DHCP, 69 TFTP, 80 HTTP, 110 POP3, 143 IMAP, 161 SNMP, 443 HTTPS, 3306 MySQL.**



**Q. [EXPECTED] A socket is uniquely identified by:**

- (a) port number alone
- (b) IP address alone
- (c) **IP address + port number (+ protocol)  <-- CORRECT**
- (d) MAC address

> **Why:** This combination is what lets one machine hold thousands of simultaneous connections.



## 7.6 Application Layer Protocols



> **WEIGHTAGE: 1-3 marks | Protocol-to-purpose matching is easy marks | Priority HIGH**



### 7.6.1 Questions



**Q. [EXPECTED] [TRAP] Which protocol is used to SEND email, and which to RETRIEVE it?**

- (a) POP3 to send, SMTP to retrieve
- (b) **SMTP to send, POP3/IMAP to retrieve  <-- CORRECT**
- (c) IMAP to send, SMTP to retrieve
- (d) HTTP for both

> **Why:** **SMTP pushes mail out** (port 25). **POP3** (110) downloads and typically deletes from the server; **IMAP** (143) keeps mail on the server and supports folders and multi-device sync.



**Q. [EXPECTED] Which protocol automatically assigns IP address, subnet mask, gateway and DNS to a host?**

- (a) DNS
- (b) ARP
- (c) **DHCP  <-- CORRECT**
- (d) ICMP

> **Why:** **DHCP** uses UDP ports 67 and 68. If it fails, Windows self-assigns an **APIPA** address in 169.254.x.x.



**Q. [EXPECTED] [TRAP] Which of the following is an insecure protocol that transmits credentials in plain text?**

- (a) SSH
- (b) HTTPS
- (c) **Telnet  <-- CORRECT**
- (d) SFTP

> **Why:** **Telnet** (port 23) sends everything unencrypted; **SSH** (22) is its encrypted replacement. Similarly FTP is insecure and SFTP/FTPS are the secure alternatives.



**Q. [EXPECTED] HTTP is described as a stateless protocol because:**

- (a) it cannot transfer files
- (b) **each request is independent and the server retains no memory of previous requests  <-- CORRECT**
- (c) it uses UDP
- (d) it has no error codes

> **Why:** Statelessness is why **cookies** and server-side **sessions** exist - they supply the memory HTTP lacks. Status codes: 200 OK, 301 moved, **404 not found**, 500 server error.



## 7.7 Network Security and Cryptography



> **WEIGHTAGE: 2-4 marks | Symmetric vs asymmetric is near-certain | Priority CRITICAL**



### 7.7.1 Questions



**Q. [PYQ] The process of verifying a user's identity is called:**

- (a) integrity
- (b) **authentication  <-- CORRECT**
- (c) validation
- (d) confidentiality

> **Why:** **Authentication** = "who are you?" (password, OTP, biometric). **Authorisation** = "what may you do?". **Validation** = checking *data* format. **Integrity** = data has not been altered.



**Q. [PYQ] The information transformed during encryption is __________.**

- (a) encrypted message
- (b) coded message
- (c) cipher text
- (d) **plain text  <-- CORRECT**

> **Why:** The question asks what goes **IN**. **Plain text** is transformed *into* cipher text. "Cipher text" is the tempting wrong answer because it is the *result*.



**Q. [PYQ] [TRAP] Which of the following is NOT a symmetric-key cryptographic algorithm?**

- (a) AES
- (b) RC4
- (c) **RSA  <-- CORRECT**
- (d) DES

> **Why:** **RSA** (Rivest-Shamir-Adleman) is the classic **asymmetric/public-key** algorithm. Asymmetric family: **RSA, Diffie-Hellman, ECC, DSA, ElGamal**. Everything else you commonly meet (AES, DES, 3DES, RC4, RC5, Blowfish, IDEA) is symmetric.



**Q. [PYQ] In public key cryptography, which key is used for decrypting a message encrypted with the public key?**

- (a) Another public key
- (b) A symmetric key
- (c) The sender's private key
- (d) **The recipient's private key  <-- CORRECT**

> **Why:** Public and private keys are mathematically matched pairs - only the **corresponding private key** can undo what its public key locked. The *sender's* private key belongs to a different pair entirely.



**Q. [EXPECTED] [TRAP] To create a digital signature, the sender encrypts the message digest with:**

- (a) the recipient's public key
- (b) the recipient's private key
- (c) **the sender's private key  <-- CORRECT**
- (d) a session key

> **Why:** Two separate use cases: for **confidentiality** encrypt with the **recipient's PUBLIC** key; for a **digital signature** encrypt with the **sender's PRIVATE** key so anyone can verify it using the sender's public key. Signatures give authentication, integrity and non-repudiation - but **not** confidentiality.



**Q. [PYQ] Communication between end systems is encrypted using a key that is commonly referred to as a:**

- (a) single key
- (b) **session key  <-- CORRECT**
- (c) private key
- (d) public key

> **Why:** A **session key** is a temporary symmetric key generated for one session and then discarded. HTTPS does exactly this: asymmetric cryptography to agree a key, then fast symmetric encryption for the data.



**Q. [EXPECTED] Why do real systems combine asymmetric and symmetric cryptography?**

- (a) To use more keys
- (b) **Asymmetric solves key distribution; symmetric is far faster for bulk data  <-- CORRECT**
- (c) Symmetric is more secure
- (d) Asymmetric cannot encrypt

> **Why:** Asymmetric encryption is roughly a thousand times slower. Using it only to exchange the session key gives both secure key distribution and high throughput.



**Q. [PYQ] Which of the following describes the use of digital certificates in authentication?**

- (a) They store users' passwords.
- (b) They compress large files for secure transfer.
- (c) **They verify the identity of entities using Public Key Infrastructure (PKI).  <-- CORRECT**
- (d) They encrypt data transmission.

> **Why:** A certificate (format **X.509**) binds a **public key to an identity** and is signed by a trusted **Certificate Authority**. It authenticates identity; the traffic itself is encrypted afterwards with session keys.



**Q. [EXPECTED] A hash function is characterised by being:**

- (a) reversible
- (b) **one-way and producing a fixed-length digest  <-- CORRECT**
- (c) variable in output length
- (d) encryption with a key

> **Why:** Hashes are **irreversible**. Used for password storage, integrity checks and digital signatures. **MD5** (128-bit) and **SHA-1** (160-bit) are broken; **SHA-256/512** is current.



**Q. [EXPECTED] [TRAP] Which malware self-replicates and spreads across networks without any user action?**

- (a) Virus
- (b) **Worm  <-- CORRECT**
- (c) Trojan horse
- (d) Adware

> **Why:** A **virus** needs a host file and a user action; a **worm** spreads autonomously. A **Trojan** masquerades as useful software; **ransomware** encrypts files for payment; a **rootkit** hides an intruder's presence.



**Q. [EXPECTED] SQL injection is best prevented by:**

- (a) using a firewall
- (b) **using parameterised queries / prepared statements  <-- CORRECT**
- (c) encrypting the database
- (d) renaming tables

> **Why:** Parameterised queries separate code from data so user input can never be interpreted as SQL. Related web attack: **XSS**, prevented by output encoding.



**Q. [PYQ] Which of the following is NOT a risk management methodology?**

- (a) Acceptance of threats
- (b) **Risk generation  <-- CORRECT**
- (c) Avoidance of threats
- (d) Transfer of risks

> **Why:** The four genuine strategies are **avoid, accept, transfer (e.g. insurance) and mitigate**. Nobody *generates* risk as a strategy.



**Q. [EXPECTED] [TRAP] A passive attack is characterised by:**

- (a) modifying messages
- (b) **eavesdropping without altering data  <-- CORRECT**
- (c) denial of service
- (d) masquerading

> **Why:** **Passive** = eavesdropping and traffic analysis; hard to detect but easy to prevent with encryption. **Active** = modification, masquerade, replay, DoS; hard to prevent but easier to detect.



## 7.8 Wireless and Mobile Computing



> **WEIGHTAGE: 1-3 marks in DSSSB | GSM registers and handover types recur | Priority MEDIUM**



### 7.8.1 Questions



**Q. [PYQ] BTS stands for ________.**

- (a) Base Transfer Station
- (b) **Base Transceiver Station  <-- CORRECT**
- (c) Basic Transfer System
- (d) Basic Transceiver Station

> **Why:** **Base** (not Basic) **Transceiver** (transmitter + receiver, which is what tower equipment does) **Station**. Watch the deliberate near-miss spellings.



**Q. [PYQ] [TRAP] Which statement is true about Home Location Register (HLR) and Visitor Location Register (VLR)?**

- (a) VLR is not responsible for the MS to inform the MLR about location changes.
- (b) VLR is not responsible for the MS to inform the HLR about location changes.
- (c) **VLR is responsible for the MS to inform the HLR about location changes.  <-- CORRECT**
- (d) HLR is responsible for the MS to inform the VLR about location changes.

> **Why:** Reporting always flows **VLR to HLR**. As you move you register with a new VLR, which updates your permanent **HLR** so the home network always knows which VLR is serving you. Incoming calls query the HLR first.



**Q. [PYQ] ________ is the handover from a satellite network to a terrestrial cellular network.**

- (a) Gateway handover
- (b) Inter satellite handover
- (c) **Inter system handover  <-- CORRECT**
- (d) Intra satellite handover

> **Why:** The key word is **system** - two different systems (satellite and terrestrial) are involved. Gateway, intra-satellite and inter-satellite handovers all occur *within* the satellite system.



**Q. [EXPECTED] [TRAP] In a soft handover, the new connection is established:**

- (a) after the old one is released
- (b) **before the old one is released, so there is no interruption  <-- CORRECT**
- (c) only if the old one fails
- (d) by the mobile station alone

> **Why:** **Soft handover** (CDMA) makes before break - no interruption. **Hard handover** (GSM) breaks before make - a brief gap.



**Q. [PYQ] ______ is the address of the current tunnel endpoint for MN that can be chosen via DHCP.**

- (a) **FA  <-- CORRECT**
- (b) COA
- (c) HA
- (d) CN

> **Why:** The tunnel runs from the **Home Agent** (start) to the current point of attachment. The **Foreign Agent** sits in the visited network and terminates it, so it is the **tunnel endpoint**. **COA** is the address *value*, not the entity; **CN** is the far-end correspondent.



**Q. [PYQ] Which technology is commonly used in Wi-Fi to enhance signal range and reliability?**

- (a) **MIMO (Multiple Input Multiple Output)  <-- CORRECT**
- (b) WEP (Wired Equivalent Privacy)
- (c) TDMA
- (d) CDMA

> **Why:** **MIMO** uses multiple antennas at both ends to exploit multipath reflections instead of suffering from them, improving range, reliability and throughput. **WEP** is (broken) security; TDMA and CDMA are cellular channel-access methods.



**Q. [EXPECTED] Which IEEE standard defines Wireless LAN (Wi-Fi)?**

- (a) 802.3
- (b) **802.11  <-- CORRECT**
- (c) 802.15
- (d) 802.16

> **Why:** **802.3 = Ethernet, 802.11 = Wi-Fi, 802.15 = Bluetooth/WPAN, 802.16 = WiMAX.**



**Q. [EXPECTED] [TRAP] Which Wi-Fi security standard is considered broken and should not be used?**

- (a) WPA2
- (b) WPA3
- (c) **WEP  <-- CORRECT**
- (d) 802.1X

> **Why:** **WEP** (Wired Equivalent Privacy) has fatal cryptographic flaws and can be cracked in minutes. Progression of strength: WEP, WPA, WPA2, WPA3.

