
---

# PART 2 - Fundamentals, Number Systems, Digital Logic and Architecture

> *Weightage: 11 to 19 marks combined. Mechanical, learnable, and the fastest marks in the paper.*



## 2.1 Computer Fundamentals and Organisation



> **WEIGHTAGE: 4-7 marks in DSSSB (observed) | 4-9 expected across KVS / NVS / EMRS | Priority HIGH**



### 2.1.1 Topic checklist

- Block diagram, ALU / CU / registers, characteristics of computers
- Generations of computers and of programming languages
- Hardware vs software, system vs application software, firmware, open source
- Language translators: compiler, interpreter, assembler, linker, loader
- Input devices, output devices, both-way devices, printer classification
- Memory hierarchy, RAM types, ROM types, cache, secondary storage
- Units of memory and conversions


### 2.1.2 Questions



**Q. [PYQ] Which type of computer program acts as a bridge between a computer user and the computer hardware?**

- (a) Random Access Memory
- (b) User thread
- (c) **Operating system  <-- CORRECT**
- (d) Kernel

> **Why:** The OS is the complete interface layer between user and hardware. The **kernel** is only its innermost core - if a question asks for the "core" or "always-resident part", choose kernel; for the user-to-hardware bridge, choose operating system.



**Q. [PYQ] Which of the following is a translator that translates source code into object target code?**

- (a) Language processor
- (b) Interpreter
- (c) **Compiler  <-- CORRECT**
- (d) Assembler

> **Why:** A compiler translates the entire program at once into object code. An interpreter executes line-by-line and produces no stored object file. An assembler translates *assembly*, not high-level source. "Language processor" is the parent category, too general to be the answer.



**Q. [EXPECTED] Which of the following converts assembly language into machine code?**

- (a) Compiler
- (b) Interpreter
- (c) **Assembler  <-- CORRECT**
- (d) Loader

> **Why:** Assembler is specifically the assembly-to-machine-code translator. Remember the chain: **Preprocessor to Compiler to Assembler to Linker to Loader**.



**Q. [EXPECTED] [TRAP] Which one joins several object files and library routines into a single executable?**

- (a) Loader
- (b) **Linker  <-- CORRECT**
- (c) Assembler
- (d) Debugger

> **Why:** **Linker** combines object modules and resolves external references. **Loader** then brings the finished executable from disk into memory for execution. Candidates routinely swap these two - linker builds, loader launches.



**Q. [PYQ] Which of the following is an example of the fifth-generation language?**

- (a) Java
- (b) Cobol
- (c) **Prolog  <-- CORRECT**
- (d) Python

> **Why:** Prolog is a logic/constraint programming language used in AI, which defines 5GL. Java, Cobol and Python are all third-generation. Remember: **1GL machine, 2GL assembly, 3GL high-level procedural, 4GL non-procedural like SQL, 5GL logic/AI like Prolog and LISP.**



**Q. [PYQ] 'FORTRAN' stands for ______.**

- (a) Format Translation
- (b) Format Transfer
- (c) **Formula Translation  <-- CORRECT**
- (d) Formula Transfer

> **Why:** FORmula TRANslation - the first successful high-level language, built for scientific computing. Related: COBOL = Common Business Oriented Language, BASIC = Beginner's All-purpose Symbolic Instruction Code.



**Q. [PYQ] ______ are a set of computer programs with necessary documentation.**

- (a) Relative programs
- (b) **Software packages  <-- CORRECT**
- (c) File packages
- (d) Application programs

> **Why:** The phrase "**with necessary documentation**" is the signature of a *package*. A bare program has no documentation attached; a package (like MS Office) ships with it.



**Q. [PYQ] [TRAP] Which of the following is NOT true about software?**

- (a) **System software is written in a high-level language.  <-- CORRECT**
- (b) Application software is written in a high-level language.
- (c) System software plays a vital role for the effective functioning of a system.
- (d) System software is written in a low-level language.

> **Why:** System software must talk directly to hardware, so it is normally written in a **low-level** language (assembly or C). Note that the option list deliberately contains both "high-level" and "low-level" versions of the same claim - spot that pattern and you know which one is being tested.



**Q. [PYQ] Which of the following is an example of open-source application software?**

- (a) **GIMP  <-- CORRECT**
- (b) CorelDRAW
- (c) Microsoft Excel
- (d) Adobe Illustrator

> **Why:** GIMP (GNU Image Manipulation Program) is the free open-source image editor. Other open-source names worth knowing: **Linux, LibreOffice, MySQL, Apache, Firefox, Blender, VLC, Audacity**.



**Q. [EXPECTED] Software that is free to use but whose source code is NOT released is called:**

- (a) Open source
- (b) **Freeware  <-- CORRECT**
- (c) Shareware
- (d) Proprietary

> **Why:** **Freeware** = free, closed source (Adobe Reader). **Open source** = source code public. **Shareware** = free trial then paid (WinRAR). Free-of-cost and open-source are not the same thing.



**Q. [EXPECTED] Software permanently embedded into a hardware chip is called:**

- (a) System software
- (b) Application software
- (c) **Firmware  <-- CORRECT**
- (d) Utility software

> **Why:** Firmware sits between hardware and software - BIOS, a router's operating code, a washing-machine controller. It is stored in ROM or flash.



**Q. [PYQ] Which of the following is frequently used to ensure that data is correctly entered into a computer?**

- (a) **Keyboards  <-- CORRECT**
- (b) Speakers
- (c) Input controls
- (d) Digitisers

> **Why:** The keyboard is the standard device for entering and visually verifying data. Speakers are output only; a digitiser converts hand-drawn images.



**Q. [PYQ] Which of the following is an example of an output device?**

- (a) Mouse
- (b) Light pen
- (c) Keyboard
- (d) **Visual Display Unit  <-- CORRECT**

> **Why:** A **light pen is an INPUT device** despite operating on the screen - information flows *into* the computer. Apply the one rule: which way is information flowing?



**Q. [EXPECTED] Which of the following is used to read the magnetic-ink numbers printed on a bank cheque?**

- (a) OCR
- (b) OMR
- (c) **MICR  <-- CORRECT**
- (d) Barcode reader

> **Why:** **MICR** = Magnetic Ink Character Recognition, used exclusively for cheque processing. **OMR** reads pencil bubbles on answer sheets; **OCR** converts printed text images into editable text.



**Q. [EXPECTED] Which of the following is a page printer?**

- (a) Dot matrix printer
- (b) Daisy wheel printer
- (c) **Laser printer  <-- CORRECT**
- (d) Drum printer

> **Why:** Laser printers compose and print an entire **page** at once - the fastest class. Dot-matrix and daisy-wheel are character printers; drum and chain printers are line printers. Resolution is measured in **DPI**.



**Q. [PYQ] Memory that does not change its contents due to external causes is referred to as:**

- (a) dynamic memory
- (b) fixed memory
- (c) **static memory  <-- CORRECT**
- (d) temporary memory

> **Why:** SRAM ("static") retains its value as long as power is applied and needs **no refreshing**. DRAM stores charge in capacitors that leak, so it must be refreshed thousands of times per second.



**Q. [EXPECTED] [TRAP] Which statement about SRAM and DRAM is correct?**

- (a) DRAM is faster and used as cache
- (b) **SRAM is faster and used as cache; DRAM is denser and used as main memory  <-- CORRECT**
- (c) Both need periodic refreshing
- (d) SRAM is cheaper per bit than DRAM

> **Why:** SRAM uses a 6-transistor flip-flop per bit: fast, expensive, low density, no refresh - ideal for **cache**. DRAM uses one transistor plus a capacitor: slow, cheap, high density, needs refresh - ideal for **main memory**.



**Q. [PYQ] Select an appropriate ROM type where data can be erased or destroyed using ultraviolet light.**

- (a) EEPROM
- (b) Flash ROM
- (c) **EPROM  <-- CORRECT**
- (d) PROM

> **Why:** EPROM has a quartz window for **UV** erasure. EEPROM and Flash erase **electrically**; PROM can be written once and never erased; masked ROM is fixed at manufacture.



**Q. [PYQ] Which storage media supports only sequential access?**

- (a) Hard disk
- (b) CD
- (c) **Magnetic tape  <-- CORRECT**
- (d) DVD

> **Why:** Magnetic tape must be wound through from the start, exactly like an audio cassette. Hard disks, CDs, DVDs and SSDs are all **direct (random) access**. Tape survives because it is the cheapest medium per GB for archival backup.



**Q. [EXPECTED] Arrange in order of increasing access time (fastest first).**

- (a) Cache, Register, RAM, Hard disk
- (b) **Register, Cache, RAM, Hard disk  <-- CORRECT**
- (c) RAM, Register, Cache, Hard disk
- (d) Register, RAM, Cache, Hard disk

> **Why:** The hierarchy from fastest/smallest/costliest to slowest/largest/cheapest: **Register, Cache (L1-L2-L3), Main memory (RAM), Secondary storage (SSD/HDD), Tertiary (tape/optical)**.



**Q. [PYQ] [NUMERICAL] Which of the following statements is NOT true?**

- (a) 5 kilobytes is equal to 10,240 half bytes
- (b) 3 kilobytes is equal to 24,576 bits
- (c) **4 kilobytes is equal to 4069 bytes  <-- CORRECT**
- (d) 2 kilobytes is equal to 4096 nibbles

> **Why:** 4 KB = 4 x 1024 = **4096** bytes, not 4069 - a digit-swap trap. Verify the others: 5 KB = 5120 bytes = 10,240 nibbles (a nibble is a half byte); 3 KB = 3072 bytes x 8 = 24,576 bits; 2 KB = 2048 bytes x 2 = 4096 nibbles. **Method: convert everything to bytes first, then look for the number that is slightly off.**



**Q. [EXPECTED] [NUMERICAL] How many bits are there in 2 MB?**

- (a) 2,097,152
- (b) 8,388,608
- (c) **16,777,216  <-- CORRECT**
- (d) 1,048,576

> **Why:** 2 MB = 2 x 1024 x 1024 = 2,097,152 bytes. Multiply by 8: **16,777,216 bits**. Note the distractors are the byte count and the 1 MB byte count - always finish the conversion the question asks for.



**Q. [EXPECTED] 1 nibble equals:**

- (a) 2 bits
- (b) **4 bits  <-- CORRECT**
- (c) 8 bits
- (d) 16 bits

> **Why:** Nibble = 4 bits = half a byte. One nibble represents exactly one hexadecimal digit, which is why hex is grouped in fours.



**Q. [PYQ] Which of the following computer programs provides instructions for computer operations?**

- (a) **System software  <-- CORRECT**
- (b) System utility
- (c) Magnetic card
- (d) System application

> **Why:** System software controls and coordinates the machine itself. A *utility* is a narrower helper program (antivirus, defragmenter) that falls under system software.



**Q. [EXPECTED] Which of the following is NOT a characteristic of a computer?**

- (a) Speed
- (b) Accuracy
- (c) Diligence
- (d) **Intelligence  <-- CORRECT**

> **Why:** A computer has **no intelligence of its own** - it only follows instructions. Errors come from bad data or bad programs, summarised as **GIGO: Garbage In, Garbage Out**.



**Q. [EXPECTED] The first generation of computers used which technology?**

- (a) Transistors
- (b) Integrated circuits
- (c) **Vacuum tubes  <-- CORRECT**
- (d) Microprocessors

> **Why:** **1st = vacuum tubes, 2nd = transistors, 3rd = integrated circuits (IC), 4th = microprocessors (VLSI), 5th = AI / ULSI.** ENIAC and UNIVAC are first-generation machines.



**Q. [EXPECTED] A hybrid computer is best described as one that:**

- (a) Uses two processors
- (b) **Combines analog and digital operation  <-- CORRECT**
- (c) Runs two operating systems
- (d) Has both RAM and ROM

> **Why:** A hybrid computer handles continuous analog inputs and converts them for digital processing. The standard example is an **ICU patient monitor**, which measures analog vital signs and displays them digitally.



## 2.2 Number Systems and Codes



> **WEIGHTAGE: part of the 4-7 mark Digital Logic block | Almost always 1-3 direct questions | Priority HIGH**



### 2.2.1 Topic checklist

- Binary, octal, decimal, hexadecimal and all conversions
- BCD, Gray code, ASCII, EBCDIC, Unicode
- 1's and 2's complement, r's and (r-1)'s complement, signed representations
- Binary arithmetic, shift-as-multiply/divide


### 2.2.2 Questions



**Q. [PYQ] [NUMERICAL] The decimal equivalent of the binary number 111111 is:**

- (a) 46
- (b) **63  <-- CORRECT**
- (c) 52
- (d) 36

> **Why:** Positional weights 32+16+8+4+2+1 = 63. **Shortcut: n consecutive 1s always equal 2^n - 1.** Here 2^6 - 1 = 63.



**Q. [EXPECTED] [NUMERICAL] Convert (1101011) binary to octal.**

- (a) 151
- (b) **153  <-- CORRECT**
- (c) 155
- (d) 143

> **Why:** Group in **threes from the right**: 1 101 011, pad the left to 001 101 011, giving 1, 5, 3 = **153**. Groups of three because 8 = 2^3.



**Q. [EXPECTED] [NUMERICAL] Convert (2AF) hexadecimal to decimal.**

- (a) 683
- (b) **687  <-- CORRECT**
- (c) 675
- (d) 691

> **Why:** 2 x 256 + 10 x 16 + 15 x 1 = 512 + 160 + 15 = **687**. Remember A=10, B=11, C=12, D=13, E=14, F=15.



**Q. [EXPECTED] [NUMERICAL] Convert decimal 45 to binary.**

- (a) 101110
- (b) **101101  <-- CORRECT**
- (c) 110101
- (d) 101011

> **Why:** Divide repeatedly by 2 and read remainders bottom-up: 45 to 101101. Check: 32+8+4+1 = 45.



**Q. [PYQ] [NUMERICAL] Represent (743) in octal in Gray code.**

- (a) **100010010  <-- CORRECT**
- (b) 101011101
- (c) 110100000
- (d) 100010000

> **Why:** Step 1: octal to binary, 3 bits each - 7=111, 4=100, 3=011, giving 111100011. Step 2: Gray - copy the first bit, then XOR each adjacent pair: 1, 1^1=0, 1^1=0, 1^1=0, 1^0=1, 0^0=0, 0^0=0, 0^1=1, 1^1=0 = **100010010**.



**Q. [EXPECTED] [NUMERICAL] The Gray code equivalent of binary 1011 is:**

- (a) 1101
- (b) **1110  <-- CORRECT**
- (c) 1010
- (d) 1001

> **Why:** G1 = B1 = 1; G2 = 1^0 = 1; G3 = 0^1 = 1; G4 = 1^1 = 0. Result **1110**.



**Q. [EXPECTED] Why is Gray code used in rotary position encoders?**

- (a) It is faster to compute
- (b) **Only one bit changes between consecutive values, avoiding transient errors  <-- CORRECT**
- (c) It uses fewer bits than binary
- (d) It supports negative numbers

> **Why:** In binary, 0111 to 1000 flips four bits at once; if the sensor reads mid-transition it can output a wildly wrong value. Gray code changes exactly **one bit** per step, so the worst-case misread is off by one. This is also why **K-map rows and columns are labelled in Gray order**.



**Q. [PYQ] [NUMERICAL] How many INVALID input combinations occur at the input of a BCD adder?**

- (a) 58
- (b) 56
- (c) **156  <-- CORRECT**
- (d) 256

> **Why:** A BCD adder takes two 4-bit digits = 8 input lines = **2^8 = 256** total combinations. Valid BCD digits are 0000-1001, so valid pairs = 10 x 10 = **100**. Invalid = 256 - 100 = **156**. Memorise the triple: 256 total, 100 valid, 156 invalid.



**Q. [EXPECTED] Which of the following is an invalid BCD code?**

- (a) 1001
- (b) 0111
- (c) **1100  <-- CORRECT**
- (d) 0101

> **Why:** BCD encodes single decimal digits 0-9, so only 0000-1001 are legal. **1100 = 12**, which exceeds 9. The six invalid patterns are 1010 through 1111.



**Q. [PYQ] [NUMERICAL] What is the 2's complement of the binary number 1100?**

- (a) **0100  <-- CORRECT**
- (b) 1111
- (c) 11
- (d) 1001

> **Why:** Invert to 0011, then add 1 to get **0100**. Fast trick: copy bits from the right up to and including the first 1, then flip everything to the left - 1100 gives keep "100", flip "1" to 0, giving 0100.



**Q. [EXPECTED] [NUMERICAL] The 1's complement of 10110 is:**

- (a) 10111
- (b) **01001  <-- CORRECT**
- (c) 01010
- (d) 10101

> **Why:** 1's complement simply inverts every bit: 10110 to **01001**. Adding 1 to this would give the 2's complement.



**Q. [PYQ] [NUMERICAL] [TRAP] A register contains a 3's complement number 10100. If it is divided by 2, find the value of the register.**

- (a) 01100
- (b) 00110
- (c) **01010  <-- CORRECT**
- (d) 11010

> **Why:** The complement wording is a distraction. In a register, **dividing by 2 = shifting all bits one place RIGHT**. 10100 shifted right gives **01010**. Corollary: left shift multiplies by 2, and shifting by k multiplies or divides by 2^k.



**Q. [EXPECTED] In an 8-bit signed 2's complement representation, the range of values is:**

- (a) -127 to +127
- (b) **-128 to +127  <-- CORRECT**
- (c) -128 to +128
- (d) 0 to 255

> **Why:** 2's complement is asymmetric: one extra negative value exists because there is only one zero. General formula for n bits: **-2^(n-1) to +2^(n-1) - 1**.



**Q. [EXPECTED] Which character code supports every script in the world including Devanagari?**

- (a) ASCII
- (b) EBCDIC
- (c) BCD
- (d) **Unicode  <-- CORRECT**

> **Why:** Unicode (UTF-8 / UTF-16) covers all writing systems. ASCII is 7-bit English-only (128 characters); EBCDIC is an 8-bit IBM mainframe code. **UTF-8 is backward compatible with ASCII.**



**Q. [EXPECTED] The ASCII value of 'a' is:**

- (a) 65
- (b) **97  <-- CORRECT**
- (c) 48
- (d) 90

> **Why:** 'A' = 65, 'a' = 97 (exactly 32 more), '0' = 48. From these three anchors you can derive any letter or digit value.



## 2.3 Boolean Algebra and Logic Gates



> **WEIGHTAGE: 2-4 marks | Very high certainty - gates or K-map appear in almost every paper | Priority HIGH**



### 2.3.1 Topic checklist

- All seven gates and truth tables; universal gates
- Boolean laws, De Morgan's theorems, distributive law
- SOP / POS, minterms / maxterms, canonical vs standard form
- K-map rules, prime implicants, don't-care conditions
- XOR properties and parity


### 2.3.2 Questions



**Q. [PYQ] What does the XNOR gate output when A=1 and B=0?**

- (a) B
- (b) **0  <-- CORRECT**
- (c) A
- (d) 1

> **Why:** XNOR outputs 1 only when inputs are **identical**. Here they differ, so output is 0. Hook: **XOR = "X marks the difference"; XNOR = "No difference".**



**Q. [PYQ] Which of the following statements is false about universal logic gates?**

- (a) All basic logic gates can be implemented through universal logic gates.
- (b) NOR gate is known as universal logic gate.
- (c) NAND gate is known as universal logic gate.
- (d) **All basic logic gates cannot be implemented using universal logic gates.  <-- CORRECT**

> **Why:** This contradicts the definition. **NAND and NOR are the two universal gates** - either one alone can build NOT, AND, OR, XOR and XNOR, and therefore any digital circuit.



**Q. [EXPECTED] [NUMERICAL] How many NAND gates are required to implement a 2-input AND gate?**

- (a) 1
- (b) **2  <-- CORRECT**
- (c) 3
- (d) 4

> **Why:** A NAND gives the inverted AND, so you need a second NAND wired as an inverter: `A AND B = (A NAND B) NAND (A NAND B)`. Hence **2**. For comparison, OR from NAND needs 3.



**Q. [EXPECTED] The output of a 3-input XOR gate is 1 when:**

- (a) All inputs are 1
- (b) All inputs are 0
- (c) **An odd number of inputs are 1  <-- CORRECT**
- (d) An even number of inputs are 1

> **Why:** XOR is the **parity** function: output 1 for an odd count of 1s. This is why XOR chains are used for parity generation and error detection.



**Q. [PYQ] [TRAP] A three-variable function (A XOR B XOR C)' = ?**

- (a) (A XNOR B XNOR C)'
- (b) A XOR B XNOR C'
- (c) A XNOR B XOR C
- (d) **A XOR B XNOR C  <-- CORRECT**

> **Why:** Complementing an XOR chain equals complementing **any one** operand, and XOR against a complemented operand is exactly XNOR. Useful identities: A XOR 0 = A, A XOR 1 = A', A XOR A = 0, A XOR A' = 1.



**Q. [PYQ] Find the value of F = xy + x'z using distributive law.**

- (a) (x + z)(y + z)
- (b) (x + y')(x + z)
- (c) (x' + y)(y + z)
- (d) **(x' + y)(x + z)(y + z)  <-- CORRECT**

> **Why:** Apply A + BC = (A+B)(A+C) twice: xy + x'z = (xy + x')(xy + z) = (x + x')(y + x')(x + z)(y + z). Since (x + x') = 1 by the complement law, that factor vanishes, leaving **(x' + y)(x + z)(y + z)**.



**Q. [EXPECTED] According to De Morgan's theorem, (A + B)' equals:**

- (a) A' + B'
- (b) **A' . B'  <-- CORRECT**
- (c) A . B
- (d) (A . B)'

> **Why:** "**Break the bar, change the sign**": the OR becomes AND and each variable is individually complemented. The companion theorem is (A.B)' = A' + B'.



**Q. [EXPECTED] The Boolean expression A + AB simplifies to:**

- (a) AB
- (b) **A  <-- CORRECT**
- (c) B
- (d) A + B

> **Why:** The **absorption law**: A + AB = A(1 + B) = A(1) = A. Its dual is A(A + B) = A.



**Q. [EXPECTED] A + A'B simplifies to:**

- (a) A
- (b) B
- (c) **A + B  <-- CORRECT**
- (d) AB

> **Why:** The **redundancy law**. Verify with a truth table, or expand: A + A'B = (A + A')(A + B) = 1(A + B) = A + B.



**Q. [PYQ] [TRAP] Which statement is false about simplification of Boolean functions using the Karnaugh Map technique?**

- (a) K-map is used to simplify POS form.
- (b) **In Karnaugh Map, the rows and columns are represented in binary code sequence.  <-- CORRECT**
- (c) You group adjacent squares in powers of two, covering as many minterms or maxterms as you can.
- (d) K-map is used to simplify SOP form.

> **Why:** K-map rows and columns use **GRAY code** (00, 01, 11, 10), never plain binary order. That is precisely what makes physically adjacent cells differ in exactly one variable, which is the whole basis of the method. This is one of the most repeated "false statement" questions in the subject.



**Q. [EXPECTED] In a K-map, a group of 4 adjacent 1s eliminates how many variables?**

- (a) 1
- (b) **2  <-- CORRECT**
- (c) 3
- (d) 4

> **Why:** A group of 2^k cells eliminates **k** variables. Group of 2 removes 1, group of 4 removes 2, group of 8 removes 3. Bigger groups always give simpler expressions, so make each group as large as possible.



**Q. [EXPECTED] To simplify a function into POS form using a K-map, you group:**

- (a) the 1s
- (b) **the 0s  <-- CORRECT**
- (c) the don't-cares
- (d) alternate cells

> **Why:** Group the **0s** for POS (product of sums) and the **1s** for SOP (sum of products). Don't-care cells (X) may be included in either if doing so enlarges a group.



**Q. [EXPECTED] A minterm of a 3-variable function contains:**

- (a) Any number of literals
- (b) **All three variables, each exactly once  <-- CORRECT**
- (c) Only the complemented variables
- (d) At most two variables

> **Why:** A minterm is a full AND term containing every variable once, either plain or complemented. For n variables there are 2^n minterms. A **canonical** expression is made only of full minterms or maxterms.



**Q. [EXPECTED] Which method is preferred over the K-map when the number of variables exceeds six?**

- (a) Boolean algebra
- (b) Truth table
- (c) **Quine-McCluskey method  <-- CORRECT**
- (d) De Morgan's theorem

> **Why:** The Quine-McCluskey tabular method scales beyond the visual limit of K-maps and, crucially, **can be programmed**, whereas K-map simplification relies on human pattern recognition.



## 2.4 Combinational and Sequential Circuits



> **WEIGHTAGE: 1-3 marks | Counters and adders are the recurring favourites | Priority MEDIUM-HIGH**



### 2.4.1 Questions



**Q. [EXPECTED] In a half adder, the SUM output is produced by which gate?**

- (a) AND
- (b) OR
- (c) **XOR  <-- CORRECT**
- (d) NAND

> **Why:** Sum = A XOR B, Carry = A AND B. A **full adder** adds three bits: Sum = A XOR B XOR Cin, and it can be built from two half adders plus one OR gate.



**Q. [EXPECTED] A BCD adder adds which value to correct a result that exceeds 9?**

- (a) 0100
- (b) **0110  <-- CORRECT**
- (c) 1010
- (d) 1001

> **Why:** It adds **6 (0110)** to skip the six invalid codes 1010-1111 and return to valid BCD.



**Q. [EXPECTED] A multiplexer with 8 data inputs requires how many select lines?**

- (a) 2
- (b) **3  <-- CORRECT**
- (c) 4
- (d) 8

> **Why:** A 2^n-to-1 MUX needs **n** select lines, and 2^3 = 8, so 3 lines. A MUX is "many inputs, one output" - a data selector - and a single 2^n-to-1 MUX can implement any Boolean function of n variables.



**Q. [EXPECTED] [TRAP] Which of the following converts an n-bit code into 2^n output lines, activating exactly one?**

- (a) Encoder
- (b) **Decoder  <-- CORRECT**
- (c) Multiplexer
- (d) Comparator

> **Why:** **Decoder**: few inputs, many outputs, one active - used for memory address selection and seven-segment displays. **Encoder** is the reverse: 2^n inputs to n outputs. Students swap these constantly; remember a decoder *expands*.



**Q. [EXPECTED] Which flip-flop has a forbidden input combination?**

- (a) JK flip-flop
- (b) D flip-flop
- (c) **SR flip-flop  <-- CORRECT**
- (d) T flip-flop

> **Why:** In an SR flip-flop, **S = R = 1** is invalid (it tries to set and reset simultaneously). The **JK** flip-flop resolves this by making J = K = 1 **toggle** the output.



**Q. [EXPECTED] Which flip-flop simply passes its input to the output at each clock edge?**

- (a) SR
- (b) JK
- (c) **D  <-- CORRECT**
- (d) T

> **Why:** The **D (data/delay)** flip-flop sets Q = D at the active clock edge. It is the simplest and the most used in registers and shift registers.



**Q. [PYQ] [NUMERICAL] A Mod-6 counter and a Mod-8 counter in cascade give a ______ counter.**

- (a) Mod-14
- (b) Mod-68
- (c) Mod-2
- (d) **Mod-48  <-- CORRECT**

> **Why:** Cascading counters **multiplies** their moduli: 6 x 8 = **48**. The second counter advances once per complete cycle of the first. Never add them.



**Q. [EXPECTED] [NUMERICAL] How many flip-flops are needed to build a MOD-10 (decade) counter?**

- (a) 3
- (b) **4  <-- CORRECT**
- (c) 5
- (d) 10

> **Why:** You need n flip-flops such that 2^n is at least 10. 2^3 = 8 (too few), 2^4 = 16 (sufficient), so **4** flip-flops. Six of the sixteen states are unused.



**Q. [PYQ] [NUMERICAL] For what minimum value of propagation delay in each flip-flop will a 10-bit ripple counter skip a count when clocked at 10 MHz?**

- (a) **10 ns  <-- CORRECT**
- (b) 25 ns
- (c) 100 ns
- (d) 50 ns

> **Why:** Clock period T = 1/(10 x 10^6) = **100 ns**. In a **ripple** counter delays accumulate, so total = 10t. Setting 10t = 100 ns gives t = **10 ns**. General formula: **t = clock period / number of flip-flops.**



**Q. [EXPECTED] [TRAP] Which is the key advantage of a synchronous counter over an asynchronous (ripple) counter?**

- (a) It needs fewer flip-flops
- (b) **All flip-flops are clocked together, so delays do not accumulate  <-- CORRECT**
- (c) It can count higher
- (d) It needs no clock

> **Why:** In a synchronous counter every flip-flop shares one clock, so total delay equals **one** propagation delay rather than n of them. This is exactly why the ripple counter in the previous question miscounts at high frequency.



**Q. [EXPECTED] Output depends only on present inputs in which type of circuit?**

- (a) Sequential
- (b) **Combinational  <-- CORRECT**
- (c) Both
- (d) Neither

> **Why:** **Combinational** circuits (adders, MUX, decoders) have no memory. **Sequential** circuits (flip-flops, registers, counters) depend on present inputs *and* stored state.



## 2.5 Computer Architecture



> **WEIGHTAGE: 3-5 marks in DSSSB | 3-6 expected | Priority MEDIUM**



### 2.5.1 Topic checklist

- Von Neumann vs Harvard, ISA, micro-architecture
- Boot process, BIOS, POST, CMOS, bootstrap loader
- Registers (PC, IR, MAR, MDR, accumulator, flags)
- Buses, instruction cycle, pipelining and hazards
- RISC vs CISC, addressing modes
- Cache mapping, TAG-bit calculation, write policies, replacement
- I/O: programmed, interrupt-driven, DMA


### 2.5.2 Questions



**Q. [PYQ] Which architecture is the most energy efficient?**

- (a) CISC
- (b) IANA
- (c) ISA
- (d) **RISC  <-- CORRECT**

> **Why:** RISC uses simple fixed-length instructions and a **hardwired** control unit, so far fewer transistors switch per instruction. That is why every phone and tablet uses an ARM (RISC) processor. Note the distractor **IANA** is a networking body, not an architecture.



**Q. [PYQ] Which of the following is NOT a type of computer architecture?**

- (a) Micro Architecture
- (b) Harvard Architecture
- (c) **Software Architecture  <-- CORRECT**
- (d) Instruction Set Architecture

> **Why:** "Software architecture" belongs to **Software Engineering** - it describes module organisation, not hardware design.



**Q. [EXPECTED] [TRAP] The main advantage of Harvard architecture over von Neumann is:**

- (a) It uses less memory
- (b) **Instructions and data can be fetched simultaneously through separate buses  <-- CORRECT**
- (c) It supports more instructions
- (d) It requires no control unit

> **Why:** Von Neumann shares one memory and bus for both code and data, creating the "**von Neumann bottleneck**". Harvard separates them so both fetches can happen at once. Modern CPUs use **modified Harvard**: separate L1 instruction and data caches over one unified main memory.



**Q. [PYQ] Which of the following statements is true?**

- (a) POST is performed by BIOS immediately after the system is shutdown.
- (b) The bootstrap program is stored in RAM.
- (c) **CMOS chip is powered by the battery located on the mother board.  <-- CORRECT**
- (d) BIOS was developed by Charles Babbage.

> **Why:** POST runs at **start-up**, not shutdown. The bootstrap loader must be in **ROM** because RAM is empty at power-on. Babbage died in 1871, long before BIOS. The CMOS chip holding BIOS settings and the clock is kept alive by the motherboard's **CR2032 button cell**.



**Q. [EXPECTED] Which register holds the address of the next instruction to be executed?**

- (a) Instruction Register
- (b) Accumulator
- (c) **Program Counter  <-- CORRECT**
- (d) Memory Data Register

> **Why:** The **PC** (also called Instruction Pointer) holds the *address*; the **IR** holds the *instruction itself* once fetched. MAR holds the address being accessed in memory, MDR the data.



**Q. [PYQ] What is the size of the computer accumulator register?**

- (a) 8 bytes
- (b) 16 bytes
- (c) 8 KB
- (d) **4 bytes  <-- CORRECT**

> **Why:** The accumulator matches the machine **word size**; on a standard 32-bit machine that is 32 bits = **4 bytes**.



**Q. [PYQ] A computer bus line is made up of which of the following components?**

- (a) Registers
- (b) **Set of parallel lines  <-- CORRECT**
- (c) Accumulators
- (d) RAM and ROM

> **Why:** A bus is physically nothing more than a bundle of **parallel conductors**. Three kinds: address bus (one-way), data bus (bidirectional), control bus.



**Q. [EXPECTED] [NUMERICAL] If a CPU has 20 address lines, how much memory can it directly address?**

- (a) 512 KB
- (b) **1 MB  <-- CORRECT**
- (c) 2 MB
- (d) 4 MB

> **Why:** 2^20 = 1,048,576 locations = **1 MB**. Learn the ladder: 16 lines = 64 KB, 20 = 1 MB, 24 = 16 MB, 32 = 4 GB, 36 = 64 GB.



**Q. [PYQ] Which cycle is primarily managed by the Control Unit?**

- (a) I/O cycle
- (b) Memory refresh cycle
- (c) **Instruction cycle (Fetch-Decode-Execute cycle)  <-- CORRECT**
- (d) Arithmetic cycle

> **Why:** The **CU** fetches, decodes and sequences; the **ALU** only computes. If a question asks who *performs the operation*, the answer is ALU; who *directs* it, the CU.



**Q. [PYQ] Select the INCORRECT option among the phases of the CPU Instruction Cycle.**

- (a) Execute
- (b) **Encode  <-- CORRECT**
- (c) Store
- (d) Fetch

> **Why:** The phases are **Fetch, Decode, Execute, Store**. An instruction is *decoded*, never encoded, by the CPU.



**Q. [PYQ] Which of the following is an addressing mode used in an instruction of the form ADD R1, [R2]?**

- (a) **Register Indirect  <-- CORRECT**
- (b) Register
- (c) Indexed Register
- (d) Assembly Register

> **Why:** The **square brackets** are decisive: `R2` alone would be register mode (value in R2), while `[R2]` means "the value at the memory address held in R2" - the register acts as a pointer. "Assembly Register" is not a real addressing mode.



**Q. [EXPECTED] In which addressing mode is the operand value contained within the instruction itself?**

- (a) Direct
- (b) Register
- (c) **Immediate  <-- CORRECT**
- (d) Indirect

> **Why:** **Immediate** mode, e.g. `MOV R1, #25`. Fastest, since no memory access is needed, but the value is fixed at assembly time.



**Q. [EXPECTED] Which addressing mode is used for relocatable code and branch instructions?**

- (a) Immediate
- (b) **PC-relative  <-- CORRECT**
- (c) Register
- (d) Implied

> **Why:** PC-relative computes the effective address as **PC + offset**, so the code works regardless of where it is loaded in memory.



**Q. [PYQ] Which of the following is a key design goal of an Instruction Set Architecture?**

- (a) Minimizing the transistor count
- (b) Ensuring only complex instructions are supported
- (c) Maximizing the instruction decode time
- (d) **Balancing simplicity and performance for ease of programming and efficiency  <-- CORRECT**

> **Why:** You want to **minimise** decode time, not maximise it, and transistor count is a chip-fabrication concern rather than an ISA goal. Good ISA design aims for completeness, orthogonality, regularity and efficiency.



**Q. [PYQ] [NUMERICAL] A four-way set-associative cache of 32 KB uses a block size of 1 K words. Word length is 8 bits and the physical address space is 32 GB. The number of TAG bits is:**

- (a) **22  <-- CORRECT**
- (b) 24
- (c) 25
- (d) 23

> **Why:** Address space 32 GB = 2^35 bytes, and words are 1 byte, so **35 address bits**. Block = 1 K words = 2^10, so **10 offset bits**. Cache = 32 KB = 2^15 bytes, lines = 2^15/2^10 = 32; four-way means 32/4 = 8 sets = 2^3, so **3 set bits**. TAG = 35 - 3 - 10 = **22**.



**Q. [EXPECTED] [TRAP] Which cache mapping technique suffers most from conflict misses?**

- (a) Fully associative
- (b) **Direct mapping  <-- CORRECT**
- (c) Two-way set associative
- (d) Four-way set associative

> **Why:** In **direct mapping** each memory block has exactly one permitted cache line, so two frequently used blocks competing for that line evict each other repeatedly. Fully associative has no conflict misses at all (a block may go anywhere) but needs expensive parallel tag comparison.



**Q. [EXPECTED] In the write-back cache policy:**

- (a) Memory is updated on every write
- (b) **Memory is updated only when the block is evicted, tracked by a dirty bit  <-- CORRECT**
- (c) Writes bypass the cache
- (d) Writes are not allowed

> **Why:** **Write-back** is faster but leaves memory temporarily stale. **Write-through** updates both cache and memory immediately - simpler and always consistent, but slower.



**Q. [EXPECTED] [NUMERICAL] If the cache hit ratio is 0.9, cache access time is 10 ns and memory access time is 100 ns, the average access time is:**

- (a) 10 ns
- (b) **19 ns  <-- CORRECT**
- (c) 55 ns
- (d) 100 ns

> **Why:** Average = H x Tc + (1 - H) x Tm = 0.9(10) + 0.1(100) = 9 + 10 = **19 ns**. This formula appears in some form in most architecture papers.



**Q. [EXPECTED] Which I/O technique transfers a whole block between device and memory with minimal CPU involvement?**

- (a) Programmed I/O
- (b) Interrupt-driven I/O
- (c) **DMA  <-- CORRECT**
- (d) Polling

> **Why:** **DMA** (Direct Memory Access) uses a separate controller and interrupts the CPU only once, at completion. Programmed I/O wastes the CPU in a polling loop; interrupt-driven I/O still involves the CPU per byte.



**Q. [EXPECTED] In pipelining, a branch instruction causes which type of hazard?**

- (a) Structural
- (b) Data
- (c) **Control  <-- CORRECT**
- (d) Resource

> **Why:** A **control (branch) hazard** occurs because instructions already fetched may be from the wrong path. Mitigated by **branch prediction**. Data hazards come from unavailable results (fixed by forwarding); structural hazards from two instructions needing the same unit.



**Q. [PYQ] Which logical operation does the ALU perform that results in a 1 output only when both inputs are different?**

- (a) AND
- (b) **XOR  <-- CORRECT**
- (c) OR
- (d) NOR

> **Why:** XOR is the difference detector. AND needs both 1; OR needs at least one 1; NOR needs both 0.

