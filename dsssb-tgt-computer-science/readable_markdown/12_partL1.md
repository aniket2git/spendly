
---

# PART L - Fully Solved Previous Year Question Papers

> *Every question from the three papers you shared, with the correct option marked and the reasoning in one line. Attempt each paper closed-book first, then read the explanations.*



## L0 How to Use This Part



### L0.1 The method that actually raises your score


Do not read these papers like a story. Work them like this:

1. Cover the answers with a sheet of paper. Attempt all questions of one Discipline section in **20 minutes**.
2. Mark yourself with the DSSSB scheme: **+1** for correct, **-0.25** for wrong, **0** for skipped.
3. Now read every explanation - **including the ones you got right**. Getting a question right by luck is not knowledge.
4. For every question you got wrong, write the **topic name** in a notebook. After all three papers, that notebook is your personal syllabus for revision.
5. Re-attempt the same papers after two weeks. Anything you get wrong twice needs the relevant chapter re-read completely.


> **TIP: A note on the answer keys**
>
> A handful of official answer keys in these papers are **technically debatable** - and I have flagged each one where it occurs, with both the key's answer and the standard textbook answer. This matters: if the same question reappears, you want to know the theory AND what the examiner expected. These flagged cases are marked **KEY NOTE**.



## L1 Paper 1 - Discipline 1



**Q. In order to move objects in computer graphics that generate animation effects, which of the following is necessary?**

- (a) **Various transformation operations  <-- CORRECT**
- (b) Line rasterisation sequencing
- (c) Phong model of lighting
- (d) Eigen value computations

> **Why:** Animation is repeated translation, rotation and scaling between frames. Rasterisation draws lines; the Phong model shades surfaces. See Part I, Chapter I3.4.



**Q. ________ is the standard that defines how web servers and application programs communicate.**

- (a) JDBC
- (b) ODBC
- (c) CGI
- (d) **HTTP  <-- CORRECT**

> **Why:** **KEY NOTE.** The key says HTTP. Textbook theory says **CGI** is the standard defining how a web server talks to an external application program; HTTP defines browser-to-server communication. If both appear again, judge by the pairing named in the question. See Part H, Chapter H1.2.



**Q. The ______ design is a high-abstraction version of a system, followed by ______ design that breaks the concept into a less-abstracted view of sub-systems, and later the ______ design showcases the implementation at module level.**

- (a) detailed, system, architectural
- (b) detailed, architectural, system
- (c) architectural, detailed, system
- (d) **system, architectural, detailed  <-- CORRECT**

> **Why:** Always most abstract to most concrete: System to Architectural to Detailed. See Part I, Chapter I1.3.



**Q. Within software engineering, which prescriptive model is INCOMPATIBLE with circumstances in which the requirements alter throughout development?**

- (a) **Linear models  <-- CORRECT**
- (b) Evolutionary models
- (c) Agile models
- (d) Incremental models

> **Why:** "Linear" means Waterfall - each phase is frozen once finished, so changes cannot be fed back. The other three are built to absorb change. See Part I, Chapter I2.3.



**Q. Represent (743) in octal in grey code.**

- (a) **100010010  <-- CORRECT**
- (b) 101011101
- (c) 110100000
- (d) 100010000

> **Why:** Octal 743 to binary is 111100011; then Gray = first bit copied, each later bit = XOR of adjacent binary bits. Full working in Part A, Chapter A5.5.



**Q. Which of the following is a translator that translates source code into object target code?**

- (a) Language processor
- (b) Interpreter
- (c) **Compiler  <-- CORRECT**
- (d) Assembler

> **Why:** A compiler translates the whole program into object code. An interpreter executes line by line without producing a stored object file; an assembler translates assembly, not high-level source. See Part A, Chapter A2.4.



**Q. A fixed sum that is paid by customers for a service, typically on a monthly, quarterly or annual basis, is called ______ in electronic commerce.**

- (a) licensing
- (b) affiliate
- (c) marketing
- (d) **subscription  <-- CORRECT**

> **Why:** "Fixed sum" plus "monthly/quarterly/annual" defines a recurring subscription. See Part H, Chapter H7.3.



**Q. Which architecture is the most energy efficient?**

- (a) CISC
- (b) IANA
- (c) ISA
- (d) **RISC  <-- CORRECT**

> **Why:** RISC uses simple fixed-length instructions and a hardwired control unit, so fewer transistors switch per instruction - which is why every phone uses ARM. IANA is a networking body. See Part B, Chapter B3.



**Q. Which phenomenon causes a phase shift in the retardation plates?**

- (a) Phasor plates
- (b) Retardation plates
- (c) Polaroid filters
- (d) **Double refraction  <-- CORRECT**

> **Why:** Birefringence gives the two polarisation components different speeds, producing the phase difference. "Retardation plates" is the device, not the phenomenon. See Part J, Chapter J5.2.



**Q. What is the best case and worst-case complexity of selection sort?**

- (a) O(n log n)
- (b) O(n)
- (c) **O(n^2)  <-- CORRECT**
- (d) O(log n)

> **Why:** Selection sort always scans the whole unsorted portion, so the comparison count n(n-1)/2 is unaffected by the input order. See Part E, Chapter E4.2.



**Q. ________ is the handover from a satellite network to a terrestrial cellular network.**

- (a) Gateway handover
- (b) Inter satellite handover
- (c) **Inter system handover  <-- CORRECT**
- (d) Intra satellite handover

> **Why:** Two different *systems* are involved (satellite and terrestrial). The others all occur within the satellite system. See Part G, Chapter G8.2.



**Q. The series SUM 1 / (n^2) raised to the power 1/5 is:**

- (a) None of the given options
- (b) divergent
- (c) oscillatory convergent
- (d) **convergent  <-- CORRECT**

> **Why:** **KEY NOTE.** The term simplifies to 1/n^(2/5), a p-series with p = 0.4. Since p is less than or equal to 1, the strict rule gives **divergent**; the official key marked convergent. Learn the rule properly: p greater than 1 converges. See Part J, Chapter J4.1.



**Q. Which method creates interpolants that are softer?**

- (a) Polynomial and spline interpolation
- (b) **Piecewise constant interpolation  <-- CORRECT**
- (c) Polynomial interpolation
- (d) Linear interpolation and spline interpolation

> **Why:** Piecewise constant interpolation is a plain step function with no curvature - the crudest interpolant. See Part J, Chapter J2.2.



**Q. Which of the following are networking transport layer protocols?**

- (a) FTP and DNS
- (b) Telnet and ICMP
- (c) **TCP, UDP and SCTP  <-- CORRECT**
- (d) ARP and RARP

> **Why:** FTP, DNS and Telnet are Application layer; ICMP, ARP and RARP are Network layer. See Part G, Chapter G2.2.



**Q. Which transition generates laser output in the CO2 molecule?**

- (a) **Vibrational states  <-- CORRECT**
- (b) Pulsed output
- (c) Molecular states
- (d) Energy states

> **Why:** CO2 is a molecule, so it has vibrational levels; lasing occurs between them at 10.6 micrometres. See Part J, Chapter J5.1.



**Q. ______ activities are at the very core of project completion work tasks, whereas ______ activities are not mandatory.**

- (a) Requirements, arbitrary
- (b) Framework, umbrella
- (c) **Functional, non-functional  <-- CORRECT**
- (d) Non-functional, functional

> **Why:** Functional requirements define the work the software must do; non-functional ones are quality attributes. See Part I, Chapter I1.2.



**Q. Which of the following is frequently used to ensure that data is correctly entered into a computer?**

- (a) **Keyboards  <-- CORRECT**
- (b) Speakers
- (c) Input controls
- (d) Digitisers

> **Why:** The keyboard is the standard device for entering and verifying data. Speakers are output; digitisers convert drawings. See Part A, Chapter A3.2.



**Q. The most common type of business organisation is:**

- (a) partnership
- (b) **sole proprietorship  <-- CORRECT**
- (c) NGO
- (d) corporation

> **Why:** Easiest and cheapest to start, no registration formalities - the vast majority of small businesses. See Part J, Chapter J6.5.



**Q. An operating system completely releases the memory allocated to a process after the process transitions from which of the following states?**

- (a) Sleeping to ready
- (b) Ready to running
- (c) **Running to terminated  <-- CORRECT**
- (d) Running to sleeping

> **Why:** Memory is reclaimed only when the process ends; in every other transition it is still alive and needs its data. See Part C, Chapter C2.2.



**Q. Which of the following is used to define the structure of a relation as well as delete relations and relate schemas?**

- (a) Integrity constraint
- (b) View
- (c) DML (Data Manipulation Language)
- (d) **DDL (Data Definition Language)  <-- CORRECT**

> **Why:** Every verb in the question is structural, and structure is DDL's job. See Part F, Chapter F4.1.



## L2 Paper 1 - Discipline 2



**Q. Which of the following comes under applied mathematics?**

- (a) Information processing
- (b) **Operations research  <-- CORRECT**
- (c) Management accounting
- (d) Organisation

> **Why:** Operations Research applies mathematical optimisation and probability to decision problems. See Part J, Chapter J6.9.



**Q. ________ reads XML documents and provides access to their content and structure.**

- (a) XML schema
- (b) XML pre-processor
- (c) **XML processor  <-- CORRECT**
- (d) XML codes

> **Why:** An XML schema *describes* validity; the processor (parser) actually reads the document. See Part H, Chapter H5.2.



**Q. An individual's shared experience results in __________.**

- (a) systematic knowledge
- (b) shared knowledge
- (c) **tacit knowledge  <-- CORRECT**
- (d) tacit, systematic and shared knowledge

> **Why:** Knowledge gained through personal experience, hard to articulate, is tacit by definition. See Part I, Chapter I4.5.



**Q. What are the data structures categorised as a linear list?**

- (a) Binary tree
- (b) Graphs
- (c) Circular queue
- (d) **Array  <-- CORRECT**

> **Why:** A linear list means a strict sequence. Trees and graphs are non-linear; a circular queue loops back on itself. See Part E, Chapter E2.1.



**Q. Which qualitative statistic is difficult to quantify precisely?**

- (a) Model
- (b) Infrastructure
- (c) **Value  <-- CORRECT**
- (d) Decision making

> **Why:** "Value" is inherently subjective and perception-dependent. Infrastructure can be counted. See Part I, Chapter I4.7.



**Q. BTS stands for ________.**

- (a) Base Transfer Station
- (b) **Base Transceiver Station  <-- CORRECT**
- (c) Basic Transfer System
- (d) Basic Transceiver Station

> **Why:** **Base** (not Basic) **Transceiver** (transmitter + receiver) **Station**. See Part G, Chapter G8.1.



**Q. Which of the following statements is FALSE?**

- (a) **Final methods can be overridden.  <-- CORRECT**
- (b) "static public void main(String...abcd){}" is a valid statement.
- (c) Abstract classes cannot be instantiated.
- (d) Interface allows default method definitions.

> **Why:** A `final` method is precisely one that cannot be overridden. The other three are all true (varargs main is legal; abstract classes cannot be instantiated; Java 8+ interfaces allow default methods). See Part D, Chapter D3.4.



**Q. What is the lifetime of an atom's ground state in Stimulated Absorption?**

- (a) 2 minutes
- (b) 11 hours
- (c) 5 seconds
- (d) **Infinity  <-- CORRECT**

> **Why:** The ground state is the lowest energy level - there is nowhere lower to fall, so the atom stays indefinitely. See Part J, Chapter J5.1.



**Q. The default file system type in Linux is:**

- (a) Ext3
- (b) Ext1
- (c) **Ext4  <-- CORRECT**
- (d) Ext2

> **Why:** Ext4 is the modern Linux default (journaling, extents, large volumes). See Part C, Chapter C5.4.



**Q. How many INVALID input combinations occur at the input of a BCD adder?**

- (a) 58
- (b) 56
- (c) **156  <-- CORRECT**
- (d) 256

> **Why:** Two 4-bit inputs give 2^8 = 256 combinations; valid BCD pairs = 10 x 10 = 100; so invalid = 256 - 100 = 156. See Part A, Chapter A5.4.



**Q. The internet layer in the TCP/IP model is associated with ______ data.**

- (a) segments
- (b) frames
- (c) bytes
- (d) **packets  <-- CORRECT**

> **Why:** Transport = segments, Internet = packets, Data Link = frames, Physical = bits. See Part G, Chapter G2.3.



**Q. What will the output of the following code snippet be? document.write("Hello") then document.write("\nIndia")**

- (a) Hello
- (b) HelloIndia
- (c) India
- (d) **Hello India  <-- CORRECT**

> **Why:** HTML collapses whitespace, so `\n` renders as a single space, not a line break. Use `<br>` for a real break. See Part H, Chapter H4.2.



**Q. Which of the following is an example of an output device?**

- (a) Mouse
- (b) Light pen
- (c) Keyboard
- (d) **Visual Display Unit  <-- CORRECT**

> **Why:** A light pen is an input device despite working on the screen. See Part A, Chapter A3.3.



**Q. What makes a database relational?**

- (a) **Tables  <-- CORRECT**
- (b) Field
- (c) Records
- (d) Tuple

> **Why:** The defining feature of the relational model is organising all data into tables. Fields, records and tuples are parts of a table. See Part F, Chapter F1.4.



**Q. Which type of computer program acts as a bridge between a computer user and the computer hardware?**

- (a) Random Access Memory
- (b) User thread
- (c) **Operating system  <-- CORRECT**
- (d) Kernel

> **Why:** The kernel is the OS core; the full user-to-hardware bridge is the operating system. See Part C, Chapter C1.1.



**Q. ______ is also referred to as the Sales-Force-Composite method or the Collective Opinion Method.**

- (a) Consumer interview method
- (b) Substitute approach
- (c) Evolutionary approach
- (d) **Opinion survey  <-- CORRECT**

> **Why:** Both alternative names refer to collecting and combining the sales force's opinions. See Part J, Chapter J6.7.



**Q. Which of the following DBMS scenarios will NOT really follow Armstrong's Axiom?**

- (a) Reflexivity rule
- (b) **Pseudo transitivity rule  <-- CORRECT**
- (c) Transitivity rule
- (d) Armstrong's axioms

> **Why:** Armstrong's axioms proper are exactly three: Reflexivity, Augmentation, Transitivity. Pseudo-transitivity is a *derived* rule. See Part F, Chapter F3.3.



**Q. In a management information system, what is/are the formal social unit that is/are devoted to attaining specified goals?**

- (a) Organisation, management and marketing
- (b) **Organisation  <-- CORRECT**
- (c) Management
- (d) Marketing

> **Why:** An organisation is the formal social structure; management is a function, marketing an activity. See Part I, Chapter I4.2.



**Q. What is effective desire?**

- (a) Demand
- (b) **Consumption  <-- CORRECT**
- (c) Calculus
- (d) Utility

> **Why:** **KEY NOTE.** The key says Consumption. Standard economics defines **demand** as effective desire (desire + ability + willingness to pay). If both appear again, Demand is the theoretically correct answer. See Part J, Chapter J6.7.



**Q. In a global system of world-wide computer networks, interconnection is essential for which purpose of computations?**

- (a) Market data analysis
- (b) **Messages for communication  <-- CORRECT**
- (c) Sharing files of different types
- (d) Data for transactions

> **Why:** Message exchange is the foundational purpose; every other activity is built on top of it. See Part G, Chapter G1.1.



## L3 Paper 1 - Discipline 3



**Q. ______ primarily deals with buying and selling, particularly on a large scale.**

- (a) **Commerce  <-- CORRECT**
- (b) Finance
- (c) Supply chain
- (d) Distribution

> **Why:** Commerce is defined by the act of buying and selling at scale. See Part H, Chapter H7.1.



**Q. Memory that does not change its contents due to external causes is referred to as:**

- (a) dynamic memory
- (b) fixed memory
- (c) **static memory  <-- CORRECT**
- (d) temporary memory

> **Why:** DRAM contents decay and need refreshing; SRAM ("static") holds its value while powered. See Part A, Chapter A4.2.



**Q. What will the output of the given program be? printf(6+"Hello World\n");**

- (a) 6Hello World
- (b) **Compilation error  <-- CORRECT**
- (c) World
- (d) Hello

> **Why:** **KEY NOTE.** The key says compilation error. Technically `6 + "Hello World\n"` advances the pointer 6 characters, so a modern compiler prints **World**. Know both. See Part D, Chapter D1.5 (Trap 11).



**Q. In which of the following directories are the configuration files found?**

- (a) /dev
- (b) /root
- (c) **/etc/  <-- CORRECT**
- (d) /bin

> **Why:** /etc holds configuration; /dev holds device files; /bin holds command binaries; /root is the superuser's home. See Part C, Chapter C6.1.



**Q. Which probability calculus of views obeys particular rules?**

- (a) Standard deviation
- (b) Variance
- (c) **Bayesian probability  <-- CORRECT**
- (d) Frequency probability

> **Why:** Bayesian probability treats probability as a degree of belief updated by evidence. Standard deviation and variance measure spread. See Part J, Chapter J3.2.



**Q. The ______ E-commerce segment(s) is/are represented by OLX.**

- (a) C2C, B2C and B2B
- (b) B2B
- (c) **C2C  <-- CORRECT**
- (d) B2C

> **Why:** Individuals sell to other individuals; OLX only provides the platform. See Part H, Chapter H7.2.



**Q. ______ is the address of the current tunnel endpoint for MN that can be chosen via DHCP.**

- (a) **FA  <-- CORRECT**
- (b) COA
- (c) HA
- (d) CN

> **Why:** The Foreign Agent terminates the tunnel in the visited network. COA is the address value, HA is the tunnel start. See Part G, Chapter G8.3.



**Q. Interpolation is carried out using data from:**

- (a) regression analysis
- (b) curve fitting and regression analysis
- (c) linear interpolation
- (d) **curve fitting and linear analysis  <-- CORRECT**

> **Why:** Interpolation passes exactly through known points; regression finds a best fit that need not. See Part J, Chapter J2.1.



**Q. Which of the following are the most essential components a computer system uses for communication over internet?**

- (a) Applications and mouse
- (b) Monitor and keyboard
- (c) **NIC and TCP/IP  <-- CORRECT**
- (d) Camera and microphone

> **Why:** You need hardware to connect (NIC) and a protocol suite to agree on rules (TCP/IP). See Part G, Chapter G1.1.



**Q. Who invented the probability definition?**

- (a) **Simon Laplace  <-- CORRECT**
- (b) Euclid
- (c) None of the given answer
- (d) Einstein

> **Why:** Laplace gave the classical definition in 1812. Euclid is geometry. See Part J, Chapter J3.1.



**Q. A particular organisation's or industry's most successful solutions or problem-solving methods are called ________.**

- (a) knowledge warehouse
- (b) **knowledge management  <-- CORRECT**
- (c) organisational learning
- (d) best practices

> **Why:** **KEY NOTE.** The key says knowledge management. The phrase actually describes **best practices**, which was also an option. Be alert if both appear. See Part I, Chapter I4.6.



**Q. Which of the following accounts is/are prepared for net profit?**

- (a) **Profit and loss account  <-- CORRECT**
- (b) Trading account, profit and loss account and balance sheet
- (c) Trading account
- (d) Balance sheet

> **Why:** Trading account gives gross profit; P&L gives net profit; balance sheet shows position. See Part J, Chapter J6.2.



**Q. ______ and ______ views cannot be framed together for rendering a computer visual appropriately.**

- (a) **Orthogonal projection, horizontal view  <-- CORRECT**
- (b) Vertical view, rear projection
- (c) Front-side, rear-side
- (d) Parallel projection, perspective projection

> **Why:** Orthographic projection uses projectors perpendicular to the plane, which conflicts with a horizontal viewing direction in the same frame. See Part I, Chapter I3.5.



**Q. Communication between an application program and a database server occurs via:**

- (a) **ODBC OR JDBC  <-- CORRECT**
- (b) API
- (c) web server
- (d) HTTP

> **Why:** ODBC and JDBC are the driver-based standards for issuing SQL from application code. See Part H, Chapter H1.3.



**Q. In C, variable list arguments are denoted by the standard header:**

- (a) <unistd.h>
- (b) <string.h>
- (c) **<stdio.h>  <-- CORRECT**
- (d) <stdarg.h>

> **Why:** **KEY NOTE.** The key says stdio.h. The correct header for va_list, va_start and va_arg is **stdarg.h**, which was also an option. Prefer stdarg.h if the question mentions the macros. See Part D, Chapter D1.1.



**Q. Which of the following algorithm design techniques is used in the merge sort algorithm?**

- (a) Greedy algorithm
- (b) Backtracking
- (c) **Divide and conquer  <-- CORRECT**
- (d) Divide and conquer, backtracking and greedy algorithm

> **Why:** Merge sort divides in half, sorts each half, then combines. See Part E, Chapter E5.1.



**Q. Identify the command that is used to delete files in Linux.**

- (a) **rm  <-- CORRECT**
- (b) Rmdir
- (c) Delete
- (d) Rdir

> **Why:** "Delete" and "Rdir" are not Linux commands; rmdir removes only empty directories. See Part C, Chapter C6.2.



**Q. Identify the generic probability density function that corresponds with discrete random variables.**

- (a) Cumulative distribution
- (b) Gaussian distribution
- (c) **Poisson distribution  <-- CORRECT**
- (d) Rayleigh distribution

> **Why:** Gaussian and Rayleigh are continuous; only Poisson is discrete. See Part J, Chapter J3.4.



**Q. The ______ interpolation method is used in probability theory and statistics, and the Gaussian process is one example.**

- (a) linear
- (b) polynomial
- (c) spline
- (d) **nonlinear  <-- CORRECT**

> **Why:** The Gaussian process (kriging) is a nonlinear probabilistic interpolation method. See Part J, Chapter J2.2.



**Q. ______ and ______ are used in conjunction for making a complete process subroutine.**

- (a) **fork(), join()  <-- CORRECT**
- (b) fork(), sleep()
- (c) sleep(), join()
- (d) join(), fork()

> **Why:** fork() splits execution, join() merges it back by waiting. Order matters - fork must come first. See Part C, Chapter C2.4.



## L4 Paper 1 - Discipline 4



**Q. Find a unit vector normal to the surface x^3 + y^3 + 3xyz = 3 at the point (1, 2, -1).**

- (a) (1/sqrt2)(i - 3j - 2k)
- (b) (1/sqrt14)(i - 3j + 2k)
- (c) **(1/sqrt14)(-i + 3j + 2k)  <-- CORRECT**
- (d) (i + 3j + 2k)

> **Why:** grad F at that point is -3i + 9j + 6k = 3(-i + 3j + 2k); magnitude of the bracket is sqrt14. Full working in Part J, Chapter J4.3.



**Q. Which of the following is NOT a network layer function?**

- (a) **Error control and flow control  <-- CORRECT**
- (b) Intra-routing
- (c) Routing
- (d) Congestion control

> **Why:** Error and flow control belong to the Data Link (per hop) and Transport (end to end) layers. See Part G, Chapter G2.4.



**Q. scanf() is a predefined function in which of the following header files?**

- (a) ctype.h
- (b) **stdio.h  <-- CORRECT**
- (c) unistd.h
- (d) string.h

> **Why:** Both printf and scanf are declared in stdio.h. See Part D, Chapter D1.1.



**Q. A public company must have at least ______ members.**

- (a) 14
- (b) **7  <-- CORRECT**
- (c) 2
- (d) 3

> **Why:** Public company minimum 7; private company minimum 2. See Part J, Chapter J6.5.



**Q. ______ are a set of computer programs with necessary documentation.**

- (a) Relative programs
- (b) **Software packages  <-- CORRECT**
- (c) File packages
- (d) Application programs

> **Why:** The phrase "with necessary documentation" is the signature of a *package*. See Part A, Chapter A2.1.



**Q. Which of the following 4-byte IP addresses are used for internet protocol layer?**

- (a) Network address and port address
- (b) Network address and MAC address
- (c) **Network address and host address  <-- CORRECT**
- (d) Host address and port address

> **Why:** An IPv4 address splits into network and host parts. Ports are Transport layer; MAC is Data Link. See Part G, Chapter G4.1.



**Q. Communication between end systems is encrypted using a key that is commonly referred to as a:**

- (a) single key
- (b) **session key  <-- CORRECT**
- (c) private key
- (d) public key

> **Why:** A session key is a temporary symmetric key generated for one session and then discarded. See Part G, Chapter G7.4.



**Q. A computer bus line is made up of which of the following components?**

- (a) Registers
- (b) **Set of parallel lines  <-- CORRECT**
- (c) Accumulators
- (d) RAM and ROM

> **Why:** A bus is physically just a bundle of parallel conductors. See Part B, Chapter B2.2.



**Q. Does polarisation vary with direction?**

- (a) Polarising axis
- (b) **Transverse wave  <-- CORRECT**
- (c) Propagating axis
- (d) Pass axis

> **Why:** Polarisation is direction-dependent only because light is a transverse wave. Longitudinal waves cannot be polarised. See Part J, Chapter J5.2.



**Q. Which of the following business structures has limited liability to its members?**

- (a) Partnership
- (b) Cooperative society
- (c) **Company  <-- CORRECT**
- (d) Sole proprietorship

> **Why:** A company is a separate legal person, so members' liability is limited to unpaid share capital. See Part J, Chapter J6.5.



**Q. According to business economics, the growth of an existing product is used to estimate the demand for a new product using:**

- (a) growth curve approach
- (b) vicarious approach
- (c) **substitute approach  <-- CORRECT**
- (d) opinion polling approach

> **Why:** The new product is assumed to substitute for the existing one, so the existing product's growth indicates its potential. See Part J, Chapter J6.7.



**Q. Identify the descending order of strict access protection.**

- (a) Public, protected, private, package
- (b) **Private, protected, package, public  <-- CORRECT**
- (c) Public, private, protected, package
- (d) Private, package, protected, public

> **Why:** **KEY NOTE.** Strictly, Java order is private > default(package) > protected > public, because protected also admits subclasses in other packages. Look for the option starting with Private and ending with public. See Part D, Chapter D3.3.



**Q. The process of verifying a user's identity is called:**

- (a) integrity
- (b) **authentication  <-- CORRECT**
- (c) validation
- (d) confidentiality

> **Why:** Authentication = "who are you?"; authorisation = "what may you do?"; validation checks data format. See Part G, Chapter G7.1.



**Q. Which method is used for demand forecasting of new products?**

- (a) **Evolutionary approach, opinion polling approach and vicarious approach  <-- CORRECT**
- (b) Opinion polling approach
- (c) Evolutionary approach
- (d) Vicarious approach

> **Why:** A brand-new product has no sales history, so firms use several indirect techniques together. See Part J, Chapter J6.7.



**Q. ________ are a database applications' universal front end that connects to the back end via the internet.**

- (a) **Web browsers  <-- CORRECT**
- (b) Web server
- (c) Software programs
- (d) Web application

> **Why:** Whatever the database or platform, the same browser can serve as the interface - that universality is the point. See Part H, Chapter H1.1.



**Q. Which command is used to remove a directory in Linux?**

- (a) **Rm  <-- CORRECT**
- (b) Delete
- (c) Erase
- (d) Rm, Delete and Erase

> **Why:** `rm -r` removes directories with their contents. "Delete" and "Erase" are not Linux commands. See Part C, Chapter C6.2.



**Q. Which layer is responsible for sending data as a bit stream?**

- (a) Presentation layer
- (b) Network layer
- (c) Physical layer
- (d) **Data link layer  <-- CORRECT**

> **Why:** **KEY NOTE.** The key says Data link. Textbook theory assigns the raw **bit stream** to the **Physical** layer; the data link layer works with frames. Prefer Physical if the question says "raw bit stream over the medium". See Part G, Chapter G2.2.



**Q. What is the average case time complexity of merge sort?**

- (a) **O(n log n)  <-- CORRECT**
- (b) O(n)
- (c) O(1)
- (d) O(n^2 log n)

> **Why:** Merge sort always splits exactly in half, so best, average and worst are all O(n log n). See Part E, Chapter E4.2.



**Q. The information transformed during encryption is __________.**

- (a) encrypted message
- (b) coded message
- (c) cipher text
- (d) **plain text  <-- CORRECT**

> **Why:** The question asks what goes IN. Plain text is transformed into cipher text. See Part G, Chapter G7.2.



**Q. The construction of computer-generated simulations that simulate real-world activities using interactive graphics software and hardware is called:**

- (a) **virtual reality systems  <-- CORRECT**
- (b) hybrid systems
- (c) genetic algorithms
- (d) fuzzy neural networks

> **Why:** The other three are Artificial Intelligence techniques, not graphics simulations. See Part I, Chapter I3.7.



## L5 Paper 1 - Discipline 5 and Teaching Methodology



### Discipline 5



**Q. In building software, ______ should preferably be lower and ______ is preferred to be on the higher side.**

- (a) inheritance from parent class, dependency with peer classes
- (b) aggregation with peer components, composition among classes
- (c) none of the given answer
- (d) **coupling among components, cohesion in bonding components  <-- CORRECT**

> **Why:** Low coupling means changes do not ripple; high cohesion means each module has one clear purpose. See Part I, Chapter I1.4.



**Q. What is a long-term asset in accounting?**

- (a) Intangible assets
- (b) Current liabilities
- (c) Fixed liabilities
- (d) **Fixed assets  <-- CORRECT**

> **Why:** Fixed assets are held for use in the business for more than one year. See Part J, Chapter J6.3.



**Q. Which storage media supports only sequential access?**

- (a) Hard disk
- (b) CD
- (c) **Magnetic tape  <-- CORRECT**
- (d) DVD

> **Why:** Tape must be run through from the start, like an audio cassette. The others are direct-access. See Part A, Chapter A4.3.



**Q. What feature of OOP allows an instance of a class to take on many forms?**

- (a) Operator overriding
- (b) Multiple inheritance
- (c) Nested class
- (d) **Operator overloading  <-- CORRECT**

> **Why:** The concept is polymorphism; since that was not an option, the mechanism implementing it is operator overloading. Note "operator overriding" is not a real term. See Part D, Chapter D2.2.



**Q. A register contains a 3's complement number 10100. If it is divided by 2, find the value of the register.**

- (a) 01100
- (b) 00110
- (c) **01010  <-- CORRECT**
- (d) 11010

> **Why:** Dividing a register value by 2 means shifting every bit one place right: 10100 becomes 01010. See Part A, Chapter A5.6.



**Q. What is an endpoint of an inter-process communication?**

- (a) Tunnel
- (b) Port
- (c) **Socket  <-- CORRECT**
- (d) Pipe

> **Why:** A socket is one endpoint of a two-way link, identified by IP + port + protocol. A port is only one component of it. See Part C, Chapter C2.5.



**Q. Which access modifier can be used to access members in a deriving class?**

- (a) Void
- (b) **Protected  <-- CORRECT**
- (c) Private
- (d) Public

> **Why:** protected is the modifier designed for inheritance. `private` blocks subclasses; `Void` is a return type. See Part D, Chapter D3.3.



**Q. What is the size of the computer accumulator register?**

- (a) 8 bytes
- (b) 16 bytes
- (c) 8 KB
- (d) **4 bytes  <-- CORRECT**

> **Why:** The accumulator matches the word size; on a standard 32-bit machine that is 4 bytes. See Part B, Chapter B2.1.



**Q. What is the name of the .NET collection class that enables an element to be accessed using a unique key?**

- (a) Linked list
- (b) **Hashtable  <-- CORRECT**
- (c) Double linked list
- (d) Array list

> **Why:** A Hashtable maps unique keys to values with average O(1) lookup. See Part D, Chapter D3.9.



**Q. Which of the following computer programs provides instructions for computer operations?**

- (a) **System software  <-- CORRECT**
- (b) System utility
- (c) Magnetic card
- (d) System application

> **Why:** System software runs and manages the computer itself. See Part A, Chapter A2.2.



### Teaching Methodology



**Q. Which of the following ailments is NOT caused by obesity?**

- (a) High blood pressure
- (b) **AIDS  <-- CORRECT**
- (c) Orthopedic problem
- (d) Diabetes

> **Why:** AIDS is caused by the HIV virus; obesity is metabolic. See Part K, Chapter K1.6.



**Q. When learning is meaning making, then students are the meaning makers. The learning process in this context is ________.**

- (a) **student-centred  <-- CORRECT**
- (b) teacher-centred
- (c) society-centred
- (d) subject-centred

> **Why:** If students make the meaning, the process revolves around the students - the constructivist view. See Part K, Chapter K3.5.



**Q. Which of the following statement is NOT correctly matched?**

- (a) Child with special need - should be seated near the board
- (b) **Performing art - every child should have clear view of board  <-- CORRECT**
- (c) Group work - sitting arrangement should be in clump or clustered
- (d) Group discussion - teacher should have eye contact with every child

> **Why:** Performing arts need open floor space for movement, not a view of the board. See Part K, Chapter K3.8.



**Q. Integrated child development service provides nutritious food for children who are ______.**

- (a) School going
- (b) School drop-out
- (c) **Below age of six years and too young to go to school  <-- CORRECT**
- (d) Girls below 12 years of age

> **Why:** ICDS targets 0-6 years through Anganwadis; school children are covered by the Mid-Day Meal scheme. See Part K, Chapter K5.3.



**Q. Which of the following is the activity related to community services?**

- (a) Collect picture about different musical instrument and dances
- (b) Collect information about handicrafts of different place
- (c) **Participating in decoration at the time of events  <-- CORRECT**
- (d) Explore food habit and living style of the people of different state

> **Why:** Ask whether the student GIVES to the community or GETS information from it. Only decorating is giving. See Part K, Chapter K6.2.



**Q. Auditory and visual co-ordination system is present in child from ______.**

- (a) **Birth  <-- CORRECT**
- (b) 3 weeks of birth
- (c) 6 days of birth
- (d) 6 months of birth

> **Why:** A newborn turns its head and eyes toward a sound - an innate ability. See Part K, Chapter K1.4.



**Q. All of the given are the methods of Information and Communication Technology-based assessment except ______.**

- (a) Concept map construction
- (b) **Writing reflection journal on paper  <-- CORRECT**
- (c) Multimedia program development
- (d) Computer-based testing

> **Why:** The qualifier "on paper" removes all technology from the method. See Part K, Chapter K4.3.



**Q. Which of the following is correctly matched? I. A child calling all four legged animals doggie - under-generalization. II. A child using word 'duck' for only his toy duck - over-generalizing.**

- (a) Both I and II
- (b) **Neither I nor II  <-- CORRECT**
- (c) Only II
- (d) Only I

> **Why:** Both labels are swapped: all animals = OVER-generalisation; only one toy = UNDER-generalisation. See Part K, Chapter K2.7.



**Q. The philosophy of inclusive education was added in District Primary Education Programme (DPEP) in ________ year.**

- (a) 1966
- (b) **1997  <-- CORRECT**
- (c) 2012
- (d) 1950

> **Why:** DPEP launched 1994; Salamanca Statement 1994; inclusion added to DPEP 1997. See Part K, Chapter K5.2.



**Q. The given statement is referring to which type of identity status in adolescents? 'Experimenting and actively searching for alternatives in their struggle to establish their identity.'**

- (a) **Identity moratorium  <-- CORRECT**
- (b) Identity diffusion
- (c) Identity foreclosure
- (d) Identity achievement

> **Why:** Exploration in progress but no commitment yet. Moratorium literally means a pause. See Part K, Chapter K2.4.

