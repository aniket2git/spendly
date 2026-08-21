
## L6 Paper 2 - Discipline 1



**Q. ________ does NOT have any child ClassLoaders.**

- (a) BootStrap ClassLoader
- (b) Extension ClassLoader
- (c) Primordial ClassLoader
- (d) **System ClassLoader  <-- CORRECT**

> **Why:** Hierarchy is Bootstrap to Extension to System, so System is at the bottom. "Primordial" is another name for Bootstrap. See Part D, Chapter D3.2.



**Q. The lowest cost solution to developing a KM system is:**

- (a) **in-house development  <-- CORRECT**
- (b) outsourcing
- (c) development by end users
- (d) off-the-shelf solution

> **Why:** Building internally uses existing staff and infrastructure, avoiding vendor fees and licences. See Part I, Chapter I4.6.



**Q. ______ is a set of interrelated components that collect (or retrieve), process, store and distribute information to support decision-making and control in an organisation.**

- (a) An information technology
- (b) Mini model of a processed system
- (c) Max model of a processed system
- (d) **An information system  <-- CORRECT**

> **Why:** IT is the technology; an information system is technology + people + processes. See Part I, Chapter I4.2.



**Q. Which of the following services is NOT provided by the operating system?**

- (a) Resource management
- (b) Inter process for communication
- (c) **Translate source into machine code  <-- CORRECT**
- (d) Program execution

> **Why:** Translation is the compiler's job; the OS merely runs the compiler. See Part C, Chapter C1.2.



**Q. How to write the dot net server control?**

- (a) <asp:controlType ID="ControlID" runin="server" ...>
- (b) <asp:controlType ID="ControlID" runas="server" ...>
- (c) <asp:controlType ID="ControlID" run="server" ...>
- (d) **<asp:controlType ID="ControlID" runat="server" ...>  <-- CORRECT**

> **Why:** Every ASP.NET server control needs `runat="server"` - memorise the exact spelling. See Part D, Chapter D4.2.



**Q. Which of the following is NOT a type of computer architecture?**

- (a) Micro Architecture
- (b) Harvard Architecture
- (c) **Software Architecture  <-- CORRECT**
- (d) Instruction Set Architecture

> **Why:** Software architecture belongs to Software Engineering, not hardware design. See Part B, Chapter B1.2.



**Q. A network on the internet has a subnet mask of 255.255.240.0. What is the maximum number of hosts it can handle?**

- (a) 1024
- (b) 3072
- (c) 2048
- (d) **4094  <-- CORRECT**

> **Why:** The mask is /20, leaving 12 host bits: 2^12 - 2 = 4094. Note 4096 is the total addresses, not usable hosts. Full working in Part G, Chapter G4.3.



**Q. Which of the following statements is true?**

- (a) Circuit setup is not required in both a datagram network and virtual-circuit network.
- (b) Circuit setup is required in both a datagram network and virtual-circuit network.
- (c) **Circuit setup is required in a virtual-circuit network.  <-- CORRECT**
- (d) Circuit setup is required in a datagram network.

> **Why:** A virtual circuit establishes a logical path first; a datagram network sends each packet independently with no setup. See Part G, Chapter G1.6.



**Q. Which of the following is NOT a risk management methodology?**

- (a) Acceptance of threats
- (b) **Risk generation  <-- CORRECT**
- (c) Avoidance of threats
- (d) Transfer of risks

> **Why:** The four genuine strategies are avoid, accept, transfer and mitigate. Nobody generates risk deliberately. See Part G, Chapter G7.7.



**Q. The decimal equivalent of the binary number 111111 is:**

- (a) 46
- (b) **63  <-- CORRECT**
- (c) 52
- (d) 36

> **Why:** Six ones in a row = 2^6 - 1 = 63. See Part A, Chapter A5.2.



**Q. What are the articulation points in the given graph?**

- (a) 1, 2 and 3
- (b) 2, 3 and 4
- (c) 3, 4 and 5
- (d) **2, 3 and 5  <-- CORRECT**

> **Why:** Remove each vertex and check whether the graph splits: removing 3 isolates 9 and 10; removing 2 separates the two clusters; removing 5 isolates 6. Full method in Part E, Chapter E3.6.



**Q. DSS is a computer program application used to improve a company's ______ capabilities.**

- (a) **decision-making capabilities  <-- CORRECT**
- (b) marketing capabilities
- (c) delegation capabilities
- (d) resources utilisation capabilities

> **Why:** The name says it: Decision Support System. See Part I, Chapter I4.3.



**Q. ______ is a code that consists of CPU and platform-independent set of instructions, which can be easily converted to the native code.**

- (a) DLL
- (b) FCL
- (c) JIT
- (d) **MSIL  <-- CORRECT**

> **Why:** MSIL is the intermediate language; JIT is the converter, FCL is a library, DLL is a compiled file. See Part D, Chapter D4.2.



**Q. CMM stands for:**

- (a) Cognitive Modularity Model
- (b) Capability Modularity Model
- (c) Cognitive Measurable Model
- (d) **Capability Maturity Model  <-- CORRECT**

> **Why:** Capability (what the organisation can do) + Maturity (how disciplined its process is). See Part I, Chapter I2.7.



**Q. Marginal revenue is calculated by ______.**

- (a) dividing the change in total output quantity by the change in total revenue
- (b) dividing the change in total cost by the change in total output quantity
- (c) **dividing the change in total revenue by the change in total output quantity  <-- CORRECT**
- (d) dividing the change in total revenue by the change in total profit

> **Why:** Revenue change on top, quantity change at the bottom. The total-cost version defines marginal cost. See Part J, Chapter J6.7.



**Q. Which of the following statements is FALSE?**

- (a) **Burst Time: Time required by a process to start its execution  <-- CORRECT**
- (b) Turn Around Time: Time difference between the completion time and arrival time
- (c) Completion Time: Time at which a process completes its execution
- (d) Arrival Time: Time at which a process arrives in the ready queue

> **Why:** Burst time is the time required to EXECUTE on the CPU, not to start. See Part C, Chapter C3.1.



**Q. In C++ language, the instruction 'ignore(x,y);' ________.**

- (a) skips the last x characters and stops if character y is encountered
- (b) skips the first y characters and stops if character x is encountered
- (c) **skips the first x characters and stops if character y is encountered  <-- CORRECT**
- (d) skips the last y characters and stops if character x is encountered

> **Why:** cin.ignore(count, delimiter): x is the count, y is the delimiter. See Part D, Chapter D4.1.



**Q. Page fault means:**

- (a) **accessing the page that is not currently in the memory  <-- CORRECT**
- (b) removing the page whenever it is needed
- (c) fetching the page whenever it is needed
- (d) an error that always occurs in the page

> **Why:** A page fault is a normal, expected event, not a program error. See Part C, Chapter C4.5.



**Q. Any account or goods used by the owner of the business for his personal use is called as:**

- (a) sales
- (b) **drawings  <-- CORRECT**
- (c) general expenses
- (d) expenses

> **Why:** Drawings reduce the owner's capital. See Part J, Chapter J6.3.



**Q. Which of the following parameters is used to create a hyperlink in HTML?**

- (a) Link
- (b) url
- (c) Path
- (d) **Href  <-- CORRECT**

> **Why:** href = Hypertext REFerence. The anchor tag does nothing without it. See Part H, Chapter H2.3.



## L7 Paper 2 - Discipline 2



**Q. Select the true statement about try-catch blocks.**

- (a) A try block must have at least 1 catch to have a finally block.
- (b) A try block must have only 1 finally block for each catch block.
- (c) **A try block can have many catches but only 1 finally block.  <-- CORRECT**
- (d) A try block can have many catches and many finally blocks.

> **Why:** Many catch blocks are allowed; exactly one finally. A try with only finally and no catch is also legal. See Part D, Chapter D3.6.



**Q. A four-way set-associative cache memory unit with a capacity of 32 KB is built using a block size of 1 K words. The word length is 8 bits. The size of physical address space is 32 GB. The number of bits for the TAG field is:**

- (a) **22  <-- CORRECT**
- (b) 24
- (c) 25
- (d) 23

> **Why:** 35 total address bits - 3 set bits - 10 offset bits = 22. Full five-step working in Part B, Chapter B5.3.



**Q. Which of the following statements is true?**

- (a) POST is the process performed by BIOS immediately after the system is shutdown.
- (b) The bootstrap program is stored in RAM.
- (c) **CMOS chip is powered by the battery located on the mother board.  <-- CORRECT**
- (d) BIOS was developed by Charles Babbage.

> **Why:** POST happens at start-up; the bootstrap is in ROM; Babbage died a century before BIOS existed. See Part B, Chapter B1.3.



**Q. A body of mass 4.9 kg hangs from a spring and oscillates with a period of 0.6 sec. How much will the spring shorten when the body is removed?**

- (a) 0.809 metre
- (b) 1.089 metre
- (c) 1.009 metre
- (d) **0.089 metre  <-- CORRECT**

> **Why:** x = gT^2/(4 pi^2) = 9.8 x 0.36 / 39.478 = 0.089 m. The mass cancels out. See Part J, Chapter J5.4.



**Q. Which of the following statements is NOT true?**

- (a) etc: It contains other additional commands that are related to system maintenance and administration.
- (b) **usr: It contains temporary files created by Linux or other users.  <-- CORRECT**
- (c) bin: It contains executable files for the UNIX commands.
- (d) dev: It contains device drivers that control various peripherals.

> **Why:** Temporary files live in /tmp, not /usr. See Part C, Chapter C6.1.



**Q. Elasticity of demand explains the ______ of the correlation between price and quantity.**

- (a) level, degree and angle
- (b) angle
- (c) level
- (d) **degree  <-- CORRECT**

> **Why:** Elasticity measures the magnitude of responsiveness - the "degree". See Part J, Chapter J6.7.



**Q. 'FORTRAN' stands for ______.**

- (a) Format Translation
- (b) Format Transfer
- (c) **Formula Translation  <-- CORRECT**
- (d) Formula Transfer

> **Why:** FORmula TRANslation - the first successful high-level scientific language. See Part A, Chapter A2.5.



**Q. In a path-graph having 'n' vertices, where 'n' > 2, ______ is the number of vertices with degree 2.**

- (a) 3
- (b) **n - 2  <-- CORRECT**
- (c) 2
- (d) 0

> **Why:** The two end vertices have degree 1; all n-2 middle vertices have degree 2. See Part E, Chapter E3.6.



**Q. Which of the following is NOT a type of business?**

- (a) Experience driven
- (b) **Expense driven  <-- CORRECT**
- (c) Efficiency driven
- (d) Expert driven

> **Why:** The genuine categories are experience-driven, efficiency-driven and expert-driven. See Part J, Chapter J6.8.



**Q. The algebraic sum of deviations is zero when measured from the ______.**

- (a) second quartile
- (b) geometric mean
- (c) **arithmetic mean  <-- CORRECT**
- (d) harmonic mean

> **Why:** SUM(x - mean) = SUM x - n x mean = 0 by the definition of the mean. See Part J, Chapter J3.5.



**Q. Which of the following is NOT the application of Divide and Conquer?**

- (a) Binary Search
- (b) **All Pairs Shortest Path Problem  <-- CORRECT**
- (c) Quick Sort
- (d) Strassen's Matrix Multiplication

> **Why:** All-pairs shortest path uses Floyd-Warshall, which is dynamic programming - subproblems overlap. See Part E, Chapter E5.1.



**Q. The volume of the tetrahedron bounded by the surfaces x = 0, y = 0, z = 0 and x/a + y/b + z/c = 1 is:**

- (a) abc/4
- (b) abc/2
- (c) abc/10
- (d) **abc/6  <-- CORRECT**

> **Why:** The corner tetrahedron is one sixth of the cuboid with sides a, b, c. See Part J, Chapter J4.4.



**Q. Which of the following opens the linked document in the window's full body among the target values?**

- (a) _self
- (b) **_top  <-- CORRECT**
- (c) _blank
- (d) _parent

> **Why:** _top escapes every enclosing frameset; _parent climbs only one level. See Part H, Chapter H2.3.



**Q. Which of the following is a conflict serializable schedule? S1: R1(A); R1(B); R2(A); R2(B); W2(B); W1(A) and S2: R1(A); R2(A); R2(B); W2(B); R1(B); W1(A)**

- (a) S1 is conflict serializable but S2 is not.
- (b) **S1 is not conflict serializable but S2 is conflict serializable.  <-- CORRECT**
- (c) Both are not conflict serializable.
- (d) Both are conflict serializable.

> **Why:** S1's precedence graph has edges both T1 to T2 and T2 to T1 - a cycle. S2's edges all point T2 to T1 - no cycle. Full working in Part F, Chapter F5.5.



**Q. Which of the following is the syntax to write an external CSS?**

- (a) <style rel="stylesheet" type="text/css" href="style.css">
- (b) <style> href="style.css" </style>
- (c) **<link rel="stylesheet" type="text/css" href="style.css">  <-- CORRECT**
- (d) <a href="style.css" rel="stylesheet" type="text/css">

> **Why:** External CSS uses the `<link>` tag. `<style>` is for internal CSS; `<a>` makes a hyperlink. See Part H, Chapter H3.2.



**Q. Which of the following methods is used to slide down an element?**

- (a) **slideDown()  <-- CORRECT**
- (b) moveBelow()
- (c) moveDown()
- (d) slideBelow()

> **Why:** jQuery's sliding family is slideDown, slideUp and slideToggle. See Part H, Chapter H4.5.



**Q. Which of the following is a clipping algorithm?**

- (a) Simple DDA
- (b) **Liang Barsky's algorithm  <-- CORRECT**
- (c) Bresenham's algorithm
- (d) Mid-point Algorithm

> **Why:** DDA and Bresenham draw lines; mid-point draws circles. Only Liang-Barsky clips. See Part I, Chapter I3.3.



**Q. According to the double entry system, every transaction will have ______ entries.**

- (a) Right and Left
- (b) Up and Down
- (c) **Debt and Credit  <-- CORRECT**
- (d) Up and Left

> **Why:** Every transaction has a debit side and a credit side of equal value. See Part J, Chapter J6.1.



**Q. Which of the following is a default permission for the text file in Linux?**

- (a) rwx r-- r--
- (b) **rw- r-- r--  <-- CORRECT**
- (c) rwx rwx rwx
- (d) rwx --- ---

> **Why:** Base 666 minus umask 022 gives 644 = rw-r--r--. A data file is never executable by default. See Part C, Chapter C6.3.



**Q. Which of the following statements is true about Home Location Register (HLR) and Visitor Location Register (VLR)?**

- (a) VLR is not responsible for the MS to inform the MLR about location changes.
- (b) VLR is not responsible for the MS to inform the HLR about location changes.
- (c) **VLR is responsible for the MS to inform the HLR about location changes.  <-- CORRECT**
- (d) HLR is responsible for the MS to inform the VLR about location changes.

> **Why:** Reporting direction is always VLR to HLR, so the home network knows which VLR is serving you. See Part G, Chapter G8.1.



## L8 Paper 2 - Discipline 3



**Q. An LED emits green light of wavelength 5511.11 Angstrom. Find the value of Eg.**

- (a) 1.25 eV
- (b) **2.25 eV  <-- CORRECT**
- (c) 3.606 eV
- (d) 36.06 eV

> **Why:** Eg(eV) = 12400 / lambda(Angstrom) = 12400 / 5511.11 = 2.25 eV. See Part J, Chapter J5.3.



**Q. Which of the following is NOT true about the Waterfall model?**

- (a) Long duration
- (b) **High cost  <-- CORRECT**
- (c) High-risk involvement
- (d) Low cost

> **Why:** Waterfall is a low-cost model - no prototyping or repeated risk analysis. Its real drawbacks are duration and risk. See Part I, Chapter I2.2.



**Q. Which of the following is the easiest to be transformed into a computer program?**

- (a) **Pseudo-code  <-- CORRECT**
- (b) Algorithm
- (c) Flowchart
- (d) None of the above

> **Why:** Pseudo-code already uses programming constructs, so conversion is nearly line-by-line. See Part I, Chapter I2.9.



**Q. Arrange the following in the order of growth: O(n), O(n^2), O(2^n), O(log n), O(n log n), O(n^2 log n)**

- (a) O(n), O(n^2), O(log n), O(2^n), O(n log n), O(n^2 log n)
- (b) O(n), O(2^n), O(2^n), O(log n), O(n^2 log n), O(n log n)
- (c) **O(log n), O(n), O(n log n), O(n^2), O(n^2 log n), O(2^n)  <-- CORRECT**
- (d) O(n^2), O(n), O(2^n), O(log n), O(n log n), O(n^2 log n)

> **Why:** Substitute n = 1024 and compare. Polynomials always beat exponentials. See Part E, Chapter E1.4.



**Q. How to change all images to black and white (100% grey)?**

- (a) img { filter: graycolor(100%);}
- (b) **img { filter: grayscale(100%);}  <-- CORRECT**
- (c) img { graycolor(100%);}
- (d) img { filter: "grayscale(100%)";}

> **Why:** The property is `filter`, the function is `grayscale`, and the value is unquoted. See Part H, Chapter H3.5.



**Q. Grep command is used to:**

- (a) change the case of alphabets
- (b) **search for a specific pattern from a specified file and display those lines containing the pattern  <-- CORRECT**
- (c) cut the columns/fields of a specified file
- (d) redirect the output of one command to another command

> **Why:** GREP = Globally search for a Regular Expression and Print. See Part C, Chapter C6.2.



**Q. Which of the following is NOT an XML Parser?**

- (a) **Shell  <-- CORRECT**
- (b) JDOM
- (c) DOM
- (d) SAX

> **Why:** A shell is an OS command interpreter. DOM, SAX and JDOM are genuine XML parsers. See Part H, Chapter H5.2.



**Q. Which of these is NOT a parameter upon which the influence of lightning is based?**

- (a) Light Source
- (b) Position of Observer
- (c) **Rendering Algorithm  <-- CORRECT**
- (d) Surface

> **Why:** The physical inputs are light source, surface and observer position. The rendering algorithm is the method, not a parameter. See Part I, Chapter I3.6.



**Q. Which of the following statements is NOT true?**

- (a) 5 kilobytes is equal to 10,240 half bytes
- (b) 3 kilobytes is equal to 24,576 bits
- (c) **4 kilobytes is equal to 4069 bytes  <-- CORRECT**
- (d) 2 kilobytes is equal to 4096 nibbles

> **Why:** 4 KB = 4 x 1024 = 4096 bytes, not 4069. A classic digit-swap trap. See Part A, Chapter A4.4.



**Q. What is the value of Delta^n e^(ax+b)?**

- (a) (e^(ah) - 1)^n e^(ax-b)
- (b) **(e^(ah) - 1)^n e^(ax+b)  <-- CORRECT**
- (c) (e^(ah) + 1)^n e^(ax-b)
- (d) (e^(ah) + 1)^n e^(ax+b)

> **Why:** One difference multiplies by (e^(ah) - 1); n differences multiply by that factor n times. See Part J, Chapter J2.4.



**Q. A Mod-6 counter and a Mod-8 counter in cascade give a ______ counter.**

- (a) Mod-14
- (b) Mod-68
- (c) Mod-2
- (d) **Mod-48  <-- CORRECT**

> **Why:** Cascading multiplies the moduli: 6 x 8 = 48. Do not add. See Part A, Chapter A7.6.



**Q. A three-variable function (A XOR B XOR C)' = ?**

- (a) (A XNOR B XNOR C)'
- (b) A XOR B XNOR C'
- (c) A XNOR B XOR C
- (d) **A XOR B XNOR C  <-- CORRECT**

> **Why:** Complementing an XOR chain equals complementing any one operand, and XOR with a complemented operand is XNOR. See Part A, Chapter A6.4.



**Q. How to write the external DTD?**

- (a) <!DOCTYPE SYSTEM "file-name">
- (b) <!DOCTYPE element ROOT "file-name">
- (c) <!DOCTYPE SYSTEM "file-name" root-element>
- (d) **<!DOCTYPE root-element SYSTEM "file-name">  <-- CORRECT**

> **Why:** Order matters: DOCTYPE, then the root element name, then SYSTEM, then the quoted filename. See Part H, Chapter H5.3.



**Q. Consider the relation R(PQRSTU) with F = {P to RT, Q to S, R to PS, QS to TU}. Find the closure of PQ.**

- (a) PQRST
- (b) PQRTU
- (c) PQRSU
- (d) **PQRSTU  <-- CORRECT**

> **Why:** Start with {P,Q}; P gives R,T; Q gives S; then QS gives U. Result is all six attributes. See Part F, Chapter F3.4.



**Q. The values of x are 1, 3, 4 and those of f(x) are 1, 27, 64. What is the polynomial equation using the Lagrange interpolation formula?**

- (a) **8x^2 - 19x + 12  <-- CORRECT**
- (b) 8x^2 + 9x + 12
- (c) 8x^2 - 9x + 12
- (d) 8x^2 + 9x + 12

> **Why:** Verify by substitution: at x=1 it gives 1, at x=3 it gives 27, at x=4 it gives 64. See Part J, Chapter J2.3.



**Q. If two dice are thrown, find the probability that the sum is neither 5 nor 9.**

- (a) 3/9
- (b) 5/9
- (c) 1/9
- (d) **7/9  <-- CORRECT**

> **Why:** Sum 5 has 4 ways, sum 9 has 4 ways, so 8/36 = 2/9; the complement is 7/9. See Part J, Chapter J3.3.



**Q. The general solution of dy/dx = e^(x+y) is:**

- (a) e^(-x) - e^(-y) = c
- (b) e^(-x) + e^y = c
- (c) **e^x + e^(-y) = c  <-- CORRECT**
- (d) e^(-x) + e^y = c

> **Why:** Separate to e^(-y)dy = e^x dx, integrate to get -e^(-y) = e^x + k, then rearrange. See Part J, Chapter J4.6.



**Q. What feature of the transport layer prevents data loss?**

- (a) Encryption
- (b) Packet switching
- (c) Addressing
- (d) **Flow control  <-- CORRECT**

> **Why:** Flow control stops a fast sender overflowing a slow receiver's buffer. See Part G, Chapter G2.4.



**Q. Descriptive attributes are used to:**

- (a) **record the information about relationships  <-- CORRECT**
- (b) record the information about attributes
- (c) record the information about participating entities
- (d) record the information about data

> **Why:** A descriptive attribute belongs to a relationship, not to either entity - e.g. the grade on an "enrols in" relationship. See Part F, Chapter F2.3.



**Q. Which of the following statements is FALSE about TCP?**

- (a) It uses a three-way handshake to establish a connection.
- (b) It receives data from application as a single stream.
- (c) It is a connection-oriented protocol.
- (d) **It is a connection-less protocol.  <-- CORRECT**

> **Why:** TCP is definitively connection-oriented; UDP is the connectionless one. See Part G, Chapter G5.1.



## L9 Paper 2 - Discipline 4



**Q. Which of the following is FALSE about packages?**

- (a) **Packages cannot provide controlled access.  <-- CORRECT**
- (b) Packages are used to prevent naming conflicts.
- (c) Packages are considered data encapsulation.
- (d) Packages prevent naming conflicts and are considered data encapsulation.

> **Why:** Packages DO provide controlled access through default and protected visibility. See Part D, Chapter D3.8.



**Q. Which of the following statements is true about the slow start phase of TCP congestion control?**

- (a) Congestion window increases by 1 Maximum Segment Size every round trip time.
- (b) **Congestion window approximately doubles every round trip time.  <-- CORRECT**
- (c) Congestion window increases by 2 MSS on every successful acknowledgement.
- (d) Congestion window approximately doubles on every successful acknowledgement.

> **Why:** It grows 1 MSS per ACK, which doubles the window per RTT. "Increases by 1 MSS per RTT" describes congestion avoidance. See Part G, Chapter G5.4.



**Q. Which of the following is NOT the purpose of knowledge management system?**

- (a) Driving strategy
- (b) Integration
- (c) Sharing of knowledge
- (d) **Portability  <-- CORRECT**

> **Why:** Portability is a software quality attribute, unrelated to KM goals. See Part I, Chapter I4.4.



**Q. Which of the following is NOT true about software?**

- (a) **System software is written in a high-level language.  <-- CORRECT**
- (b) Application software is written in a high-level language.
- (c) System software plays a vital role for the effective functioning of a system.
- (d) System software is written in a low-level language.

> **Why:** System software is normally written in a low-level language for direct hardware access. See Part A, Chapter A2.2.



**Q. Which of the following is NOT a shell in Linux?**

- (a) C shell
- (b) Korn shell
- (c) Bourne shell
- (d) **Alpha cell  <-- CORRECT**

> **Why:** No such shell exists - note the deliberate spelling "cell". See Part C, Chapter C6.4.



**Q. Which of the following is an example of the fifth-generation language?**

- (a) Java
- (b) Cobol
- (c) **Prolog  <-- CORRECT**
- (d) Python

> **Why:** Prolog is a logic-programming language used in AI. Java, Cobol and Python are 3GL. See Part A, Chapter A2.5.



**Q. Which of the following is NOT a phase of the RAD model?**

- (a) **Development modelling  <-- CORRECT**
- (b) Business modelling
- (c) Process modelling
- (d) Data modelling

> **Why:** RAD phases are Business, Data, Process modelling, then Application Generation and Testing. See Part I, Chapter I2.4.



**Q. If u = tan inverse (y/x), then x du/dx + y du/dy = ?**

- (a) Sin 2u
- (b) **0  <-- CORRECT**
- (c) None of the given options
- (d) Cos 2u

> **Why:** u is a function of the pure ratio y/x, so it is homogeneous of degree 0; Euler's theorem gives 0 x u = 0. See Part J, Chapter J4.2.



**Q. Which of the following inflations describes how demand for goods and services can drive up their prices?**

- (a) Cost-push inflation
- (b) Built-in Inflation
- (c) **Demand-pull inflation  <-- CORRECT**
- (d) Demand-push inflation

> **Why:** Demand PULLS prices up; costs PUSH them up. "Demand-push" does not exist. See Part J, Chapter J6.8.



**Q. Program links with other parts of the program in a flowchart are represented by ________.**

- (a) rectangles
- (b) **circles  <-- CORRECT**
- (c) trapezoids
- (d) rhombuses

> **Why:** The connector symbol is a circle. Rectangles are processing; rhombuses are decisions. See Part I, Chapter I2.9.



**Q. ______ is the process of visiting different web sites on the internet hosted by various companies, organisations, educational institutions, magazines, individuals, etc.**

- (a) Webbing
- (b) Searching
- (c) Chatting
- (d) **Web surfing  <-- CORRECT**

> **Why:** Surfing means browsing around generally; searching implies a specific query. See Part H, Chapter H7.4.



**Q. The part of the firm's capital that is required for conducting day to day expenses is called:**

- (a) **working capital  <-- CORRECT**
- (b) asset
- (c) expenses
- (d) fixed capital

> **Why:** "Day to day" is the trigger; long-term needs are met by fixed capital. See Part J, Chapter J6.3.



**Q. Who is the father of e-commerce in India?**

- (a) Bryan Eisenberg
- (b) Michael Aldrich
- (c) **K Vaitheeswaran  <-- CORRECT**
- (d) Tim Ferris

> **Why:** K Vaitheeswaran founded Fabmart/Indiaplaza in 1999. Michael Aldrich invented online shopping globally in 1979. See Part H, Chapter H7.4.



**Q. The advantage of SSTF (Shortest Seek Time First) is:**

- (a) high variance of response time as SSTF favours only some requests
- (b) overhead to calculate seek time in advance
- (c) **average response time decreases  <-- CORRECT**
- (d) throughput decreases

> **Why:** The other three are disadvantages dressed up as advantages; SSTF actually increases throughput. See Part C, Chapter C5.5.



**Q. Which of the following is an addressing mode used in an instruction of the form ADD R1, [R2]?**

- (a) **Register Indirect  <-- CORRECT**
- (b) Register
- (c) Indexed Register
- (d) Assembly Register

> **Why:** The brackets mean "the value at the address stored in R2" - the register acts as a pointer. See Part B, Chapter B4.1.



**Q. What is the output of the following code? int Integer = 24; char String = 'I'; System.out.print(Integer); System.out.print(String);**

- (a) I
- (b) Compiler Error
- (c) Throws Exception
- (d) **24I  <-- CORRECT**

> **Why:** "Integer" and "String" are class names, not reserved keywords, so they are legal identifiers. print() adds no newline. See Part D, Chapter D3.7.



**Q. An organisation structure establishes relationships between:**

- (a) **people, work and resources  <-- CORRECT**
- (b) organisations and environment
- (c) suppliers and customers
- (d) organisations and society

> **Why:** Structure defines who does what work with which resources, and who reports to whom. See Part J, Chapter J6.6.



**Q. Which of the following is NOT a symmetric-key cryptographic algorithm?**

- (a) AES
- (b) RC4
- (c) **RSA  <-- CORRECT**
- (d) DES

> **Why:** RSA is the classic asymmetric/public-key algorithm. See Part G, Chapter G7.3.



**Q. ______ is a person who carries on business by himself/herself.**

- (a) Cooperative
- (b) **Sole proprietorship  <-- CORRECT**
- (c) Partnership
- (d) Trader

> **Why:** One owner, unlimited liability, no separate legal entity. See Part J, Chapter J6.5.



**Q. Which of the following is NOT true about NTFS?**

- (a) It utilises the disk space efficiently by using a smaller size of clusters.
- (b) NTFS's attributes are read-only, hidden, system, archive, not content indexed, off-line, temporary and compressed.
- (c) It introduced improved performance, scalable in comparison with its precursor.
- (d) **It does not support the compression of files and directories to optimise storage space.  <-- CORRECT**

> **Why:** NTFS does support built-in compression. See Part C, Chapter C5.4.



## L10 Paper 2 - Discipline 5 and Teaching Methodology



### Discipline 5



**Q. The set of processes developed in an organisation to create, gather, store, transfer and apply knowledge best describes:**

- (a) **knowledge management  <-- CORRECT**
- (b) organisational learnings
- (c) knowledge asset
- (d) organisational memory

> **Why:** A knowledge asset is the thing managed; organisational memory is the store; learning is the outcome. See Part I, Chapter I4.4.



**Q. Which of the following is the execution engine for .NET applications and servers as the interface between .NET applications and the operating system?**

- (a) Framework Class Library (FCL)
- (b) Common Type System (CTS)
- (c) Common Language Specifications (CLS)
- (d) **Common Language Runtime (CLR)  <-- CORRECT**

> **Why:** The CLR executes managed code and handles memory, security and exceptions. See Part D, Chapter D4.2.



**Q. Which of the following is NOT a feature of ADO.net?**

- (a) Maintainability
- (b) Interoperability
- (c) **Reachability  <-- CORRECT**
- (d) Scalability

> **Why:** ADO.NET features are interoperability, maintainability, programmability, performance and scalability. See Part D, Chapter D4.2.



**Q. Find the value of F = xy + x'z using distributive law.**

- (a) (x + z)(y + z)
- (b) (x + y')(x + z)
- (c) (x' + y)(y + z)
- (d) **(x' + y)(x + z)(y + z)  <-- CORRECT**

> **Why:** Apply A + BC = (A+B)(A+C) twice, then eliminate (x + x') = 1. See Part A, Chapter A6.4.



**Q. The refractive index of the core of an optical fibre is greater than that of cladding because:**

- (a) the light gets reflected at the entrance end of the optical fibre
- (b) **the light gets totally internally reflected into the core  <-- CORRECT**
- (c) the light gets restricted at the entrance end of the optical fibre
- (d) the light gets refracted into cladding

> **Why:** Higher core index enables total internal reflection, trapping light inside the core. See Part G, Chapter G1.4.



**Q. Which directive is used for binding the model data to the view?**

- (a) ng-model-view
- (b) ng-model-app
- (c) **ng-model  <-- CORRECT**
- (d) ng-app-model

> **Why:** ng-model provides two-way data binding. The other three names are invented. See Part H, Chapter H4.6.



**Q. If mu is an averaging operator and delta^n is the nth central difference operator, then what is the value of mu^2?**

- (a) **mu^2 = (1/4)(delta^2 + 4)  <-- CORRECT**
- (b) mu^2 = (1/2)(delta^2 + 4)
- (c) mu^2 = (1/4)(delta^2 + 6)
- (d) mu^2 = (1/4)(delta^2 + 8)

> **Why:** Square mu = (E^(1/2) + E^(-1/2))/2 and substitute E + E^(-1) = delta^2 + 2. See Part J, Chapter J2.4.



**Q. For what minimum value of propagation delay in each FF will a 10-bit ripple counter skip a count when it is clocked at 10 MHz?**

- (a) **10 ns  <-- CORRECT**
- (b) 25 ns
- (c) 100 ns
- (d) 50 ns

> **Why:** Clock period = 100 ns; ripple delays add, so t = 100/10 = 10 ns. See Part A, Chapter A7.6.



**Q. What are the solutions for the following sum of a subset problem? w[1:5] = {2,7,8,9,15}; Sum required = 17.**

- (a) 11100; 10101; 00110
- (b) **11100; 10001; 00110  <-- CORRECT**
- (c) 11000; 10001; 00110
- (d) 11100; 10101; 00111

> **Why:** 2+7+8 = 17; 2+15 = 17; 8+9 = 17. Just add up the weights each bit string selects. See Part E, Chapter E5.3.



**Q. Which of the following systems comprises word processing, electronic filing, electronic mail, message switching, data storage and data and voice communication?**

- (a) Executive Support Systems
- (b) **Office Automation Systems  <-- CORRECT**
- (c) Customer Relationship Management
- (d) Decision Support Systems

> **Why:** Every listed item is a routine office function. See Part I, Chapter I4.3.



### Teaching Methodology



**Q. Who among the following is known as Lokhitwadi?**

- (a) Ishwar Chandra Vidyasagar
- (b) **GopalHari Deshmukh  <-- CORRECT**
- (c) Rabindranath Tagore
- (d) Ram Mohan Roy

> **Why:** Gopal Hari Deshmukh, the Marathi social reformer, wrote under the pen name "Lokhitwadi" (one who desires people's welfare).



**Q. For preparing a unit plan, which of the following procedure is followed? I. Formation of proper units and sub-units if not prescribed in the syllabus. II. Determination of methods of assessment.**

- (a) **Both I and II  <-- CORRECT**
- (b) Neither I nor II
- (c) Only I
- (d) Only II

> **Why:** A unit plan must define its boundaries and specify how learning will be assessed. See Part K, Chapter K3.7.



**Q. David Kolb's model of learning style is based on which type of learning?**

- (a) Inquiry-based learning
- (b) Integrative learning
- (c) Collaborative learning
- (d) **Experiential learning  <-- CORRECT**

> **Why:** Kolb defined learning as knowledge created through the transformation of experience. See Part K, Chapter K3.2.



**Q. Inconsistency in the development of different type of conservation is called ______.**

- (a) **Horizontal Decalage  <-- CORRECT**
- (b) Meta-cognition
- (c) Selective attention
- (d) Immersion

> **Why:** Decalage means gap; horizontal means within the same stage - a gap across tasks. See Part K, Chapter K2.1.



**Q. Heuristic method of teaching science was introduced by ______.**

- (a) William James
- (b) **Henry Edward Armstrong  <-- CORRECT**
- (c) Lev Vygotsky
- (d) Abraham Maslow

> **Why:** Armstrong, an English chemist, argued students should learn science by investigating like scientists. See Part K, Chapter K3.4.



**Q. Which of the following statement is correct regarding vision of new-born babies? I. Neonates can discriminate stationary black and white stripes 1/8 inch wide. II. By three months babies can see stripes as narrow as 1/64 inch.**

- (a) **Both I and II  <-- CORRECT**
- (b) Neither I nor II
- (c) Only I
- (d) Only II

> **Why:** Standard infant acuity findings: 1/8 inch at birth improving to 1/64 inch by three months. See Part K, Chapter K1.4.



**Q. In the context of Parenting, which of the following is correctly matched?**

- (a) Clearly communicating parent - Child being less liked
- (b) Power assertive parents - Coercive tactics in peer used by child
- (c) Parents being harsh - Unattractive social behavior of child
- (d) **Give and take relationship of parents - Children show same relationship with peer  <-- CORRECT**

> **Why:** Children model the reciprocal give-and-take style they experience at home. See Part K, Chapter K2.8.



**Q. Broca's area and Wernicke's area are concerned with language. These are the areas of ______. I. right hemisphere. II. left hemisphere.**

- (a) **Only II  <-- CORRECT**
- (b) Only I
- (c) Both I and II
- (d) Neither I nor II

> **Why:** Language is lateralised to the LEFT hemisphere in about 95% of right-handers. See Part K, Chapter K1.5.



**Q. Which of the following is NOT a Neo-Freudian Theory of Development? I. Sullivan's Interpersonal Theory. II. Erikson's Psycho-social Development.**

- (a) Only II
- (b) Both I and II
- (c) **Neither I nor II  <-- CORRECT**
- (d) Only I

> **Why:** Both ARE Neo-Freudian, so neither qualifies as "not Neo-Freudian". A double-negative trap. See Part K, Chapter K2.6.



**Q. Participation in which of the following activities can enable the community to accept a teacher as one of them? I. Problems of unhygienic conditions. II. Problems of agriculture.**

- (a) Neither I nor II
- (b) Only I
- (c) **Both I and II  <-- CORRECT**
- (d) Only II

> **Why:** Acceptance comes from involvement in matters the community cares about daily. See Part K, Chapter K6.1.

