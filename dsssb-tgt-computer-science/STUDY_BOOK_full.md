# DSSSB TGT Computer Science - Complete Study Book


---

# PART 0 - Before You Begin

> *Understand the exam first. A student who knows the target scores more than a student who only knows the subject.*



## 0.1 The Exam, The Pattern and The Plan



### What the DSSSB TGT Computer Science paper looks like


DSSSB means **Delhi Subordinate Services Selection Board**. TGT means **Trained Graduate Teacher**. So this exam picks teachers who will teach Computer Science in Delhi government schools.

The question paper is a single objective (MCQ) paper. Based on the papers you shared, the structure is like this:


| Section | What it contains | Rough share |
|---|---|---|
| General Awareness / Reasoning / Hindi / English | Comprehension passages, current affairs, arithmetic, logic | About 80 marks |
| Subject Discipline (Computer Science) | Split into Discipline-1 to Discipline-5, roughly 20 questions each | About 100 questions |
| Teaching Methodology / Pedagogy | Child development, teaching methods, assessment, education policy | About 20 questions |



> **NOTE: Three things to notice about the pattern**
>
> The Computer Science part is **not** one long section. It is broken into Discipline-1, Discipline-2, Discipline-3, Discipline-4 and Discipline-5. Each block mixes every topic together - one question on Operating Systems, the next on Accounting, the next on Physics. So you can never say "this section is only networks".
>
> The paper is **very wide but not very deep**. It touches almost forty different topics, but most questions are one-line factual or single-step reasoning questions. Depth is rarely more than a first-year degree level.
>
> There is **negative marking** in DSSSB papers (normally 0.25 mark per wrong answer). So a wild guess is not free. An educated guess after eliminating two options is still worth taking.



### Why the papers contain non-computer questions


You will have noticed questions on Physics (lasers, polarisation, optical fibre), Accounting (gross profit, drawings, balance sheet), Business Economics (demand forecasting, elasticity) and Mathematics (differential equations, probability) sitting inside the Discipline sections.

This happens because DSSSB draws the "Discipline" bank from the broader graduate-level syllabus of the subject stream. You cannot control this. What you **can** do:

- Master the pure Computer Science topics completely. They are the biggest and most predictable chunk.
- Learn only the **most repeated** formulas and definitions from Physics, Accounting and Economics. This book gives you exactly those in Part J and Part M - not a whole textbook.
- Never leave Teaching Methodology for the last day. It is the easiest 20 marks in the paper and most candidates lose it carelessly.


### The high-yield topic list (from the actual papers you shared)


Counting the questions across the three papers, this is where the marks actually are:


| Priority | Topic | Why |
|---|---|---|
| 1 | Operating Systems | Process states, scheduling, memory management, paging, virtual memory, disk scheduling, Linux commands - appears 8-12 times per paper |
| 1 | Computer Networks | OSI/TCP-IP layers, TCP vs UDP, IP addressing, ARP, cryptography - appears 8-12 times |
| 1 | Data Structures & Algorithms | Complexity, sorting, linked lists, divide-and-conquer - appears 6-10 times |
| 1 | C / Java programming output | "What will be the output" questions - appears 8-15 times |
| 2 | DBMS & SQL | SQL commands, keys, normalisation, transactions - appears 5-8 times |
| 2 | Digital Logic | Gates, K-map, number systems, counters - appears 4-7 times |
| 2 | Web Technologies | HTML, CSS, JavaScript, XML, PHP, AJAX - appears 4-8 times |
| 2 | Software Engineering | SDLC models, coupling/cohesion, CMM - appears 3-5 times |
| 3 | Computer Graphics | Transformations, clipping, projections - appears 2-4 times |
| 3 | MIS / Knowledge Management | MIS, DSS, KM, tacit knowledge - appears 3-6 times |
| 3 | Teaching Methodology | Fixed 10-20 questions |



### A 90-day study plan you can actually follow



| Days | What to do |
|---|---|
| 1-15 | Part A, B (Fundamentals, Number Systems, Logic, Architecture). Solve every in-chapter question. |
| 16-32 | Part C (Operating Systems) + Linux. This is the highest-return block. |
| 33-45 | Part D (C, C++, OOP, Java). Practise output-prediction questions daily. |
| 46-56 | Part E (Data Structures & Algorithms). Learn every complexity by heart. |
| 57-66 | Part F (DBMS & SQL). |
| 67-76 | Part G (Networks & Security). |
| 77-83 | Part H + Part I (Web, Software Engineering, Graphics, MIS). |
| 84-88 | Part J (Maths/Stats) + Part K (Teaching Methodology). |
| 89-90 | Part M only (rapid revision). Plus re-solve Part L papers. |



> **TIP: How to read this book**
>
> Every chapter follows the same rhythm: (1) a plain-language explanation using an everyday example, (2) the exact technical definition the examiner wants, (3) a comparison table, (4) the actual previous-year questions with full reasoning, and (5) extra questions of the same type that can appear next time.
>
> Do not skip the everyday example even if it feels childish. That example is the hook your memory will use inside the exam hall when you are nervous and the technical words have gone blank.




---

# PART A - Computer Fundamentals, Number Systems and Digital Logic

> *The foundation. Every other part of the syllabus stands on top of these six chapters.*



## A1 What a Computer Really Is



### A1.1 Start with something you already know


Imagine a **juice shop**. You hand over oranges (that is the input). The machine squeezes them (that is the processing). Juice comes out into a glass (that is the output). If the shopkeeper writes down how many glasses he sold in a notebook, that notebook is the storage.

A computer is exactly this juice machine, except it squeezes **information** instead of oranges.

- **Data** - Raw, unorganised facts. Example: 45, 90, 72. By themselves they mean nothing.
- **Information** - Data that has been processed so it now has meaning. Example: "the average marks of the class are 69".
- **Processing** - The act of turning data into information.


> **NOTE: The one-line definition the examiner wants**
>
> A computer is an **electronic device** that accepts data as input, processes it according to a set of stored instructions (a program), stores the data and the result, and produces output - all automatically and at very high speed.



### A1.2 The block diagram of a computer


Every computer, from a Rs. 500 calculator to a supercomputer, has the same five functional blocks.


*The classic block diagram*
```
        +-------------+                          +--------------+
        | INPUT UNIT  |  ---->                   | OUTPUT UNIT  |
        +-------------+        |                 +--------------+
                              v                        ^
                    +---------------------------+       |
                    |     CENTRAL PROCESSING    |-------+
                    |         UNIT  (CPU)       |
                    |   +-------+   +-------+   |
                    |   |  ALU  |   |  CU   |   |
                    |   +-------+   +-------+   |
                    |       + Registers        |
                    +---------------------------+
                              ^   |
                              |   v
                    +---------------------------+
                    |     MEMORY UNIT           |
                    | Primary  +  Secondary     |
                    +---------------------------+
```



#### 1. Input Unit

Takes data from the outside world and converts it into the electrical 0s and 1s the machine understands. Keyboard, mouse, scanner, microphone.


#### 2. CPU - the Central Processing Unit

Often called the **brain** of the computer. It has three parts:

- **ALU (Arithmetic and Logic Unit)** - does the actual work. Arithmetic means +, -, x, /. Logic means comparisons and Boolean operations (AND, OR, NOT, XOR).
- **CU (Control Unit)** - the manager. It does not calculate anything itself. It fetches each instruction, decodes it, and tells every other unit what to do and when. The **instruction cycle (Fetch - Decode - Execute - Store)** is managed by the Control Unit.
- **Registers** - a handful of tiny, ultra-fast storage boxes inside the CPU used to hold the numbers being worked on right now.


#### 3. Memory Unit

Holds the program and the data. Primary memory (RAM) is fast and temporary; secondary memory (hard disk) is slow and permanent.


#### 4. Output Unit

Converts the internal 0s and 1s back into a form humans understand - text on a monitor, ink on paper, sound from a speaker.


#### 5. Storage Unit

Keeps data for later use, even after the power goes off.


> **TIP: Exam-favourite distinction**
>
> The **ALU** performs the operation. The **CU** decides which operation to perform and controls the sequence. If a question says "which unit manages the fetch-decode-execute cycle", the answer is the **Control Unit**, not the ALU.



### A1.3 Characteristics of a computer



| Characteristic | Meaning |
|---|---|
| Speed | Measured in millions/billions of instructions per second (MIPS, FLOPS) |
| Accuracy | A computer never makes a mistake on its own. Errors come from wrong data or wrong programs - this is called GIGO (Garbage In, Garbage Out) |
| Diligence | It never gets tired or bored; the 10 millionth calculation is as accurate as the first |
| Versatility | The same machine can play music, do accounts and control a rocket |
| Storage capacity | Can hold enormous amounts of data and recall any item instantly |
| Automation | Once a program is loaded, it runs without human help |
| No IQ / No intelligence | It cannot decide anything on its own; it only follows instructions |



### A1.4 Generations of computers



| Generation | Period | Main technology | Example / feature |
|---|---|---|---|
| First | 1940-1956 | Vacuum tubes | ENIAC, UNIVAC. Huge, hot, machine language only |
| Second | 1956-1963 | Transistors | IBM 1401. Assembly language, magnetic core memory |
| Third | 1964-1971 | Integrated Circuits (IC) | IBM 360. High-level languages, keyboards and monitors |
| Fourth | 1971-1980s | Microprocessors (VLSI) | Intel 4004, personal computers, GUI |
| Fifth | 1980s-present | ULSI, AI, parallel processing | Artificial Intelligence, natural language, Prolog / LISP |



### A1.5 Types of computers by size and power



| Type | Description |
|---|---|
| Microcomputer | Single-user personal computer: desktop, laptop, tablet, smartphone |
| Minicomputer | Mid-size, serves a small department, multi-user |
| Mainframe | Very large, thousands of users at once, used by banks, railways, insurance |
| Supercomputer | Fastest of all, used for weather forecasting, nuclear simulation, genome research (India: PARAM, PRATYUSH, AIRAWAT) |
| Workstation | Single user but very high performance, used for engineering design, animation |
| Server | A computer dedicated to serving other computers on a network |


Another useful classification is by **the kind of data handled**:

- **Analog computer** - Works with continuously varying physical quantities (voltage, pressure). Example: a speedometer, an old slide rule.
- **Digital computer** - Works with discrete values - 0s and 1s. All modern computers.
- **Hybrid computer** - Combines both. Common in hospitals: an ICU monitor measures a patient's heartbeat as an analog signal and converts it to digital for display.


## A2 Hardware and Software



### A2.1 The simple difference


**Hardware** is anything you can touch. **Software** is the set of instructions you cannot touch.

Think of a music system. The speaker, the wires, the buttons - hardware. The song - software. A speaker with no song is useless; a song with no speaker cannot be heard. Both are needed.

- **Hardware** - The physical, tangible parts of a computer: CPU, RAM, keyboard, monitor, hard disk.
- **Software** - A set of programs and the associated documentation that tells hardware what to do.
- **Firmware** - Software that is permanently written into a hardware chip. It sits between the two. Example: the BIOS, a washing-machine controller.
- **Software package** - A collection of related programs supplied together **with the necessary documentation**. Example: Microsoft Office.


> **NOTE: Direct PYQ**
>
> "________ are a set of computer programs with necessary documentation." The answer is **Software packages**. The phrase "with necessary documentation" is the give-away - a plain program has no documentation; a *package* does.



### A2.2 The two great families of software



#### System Software

Software that runs and manages the computer itself. It is the bridge between the user/application and the bare hardware.

- **Operating System** - Windows, Linux, macOS, Android. This is the program that "acts as a bridge between a computer user and the computer hardware".
- **Language translators** - compiler, interpreter, assembler.
- **Utility programs** - antivirus, disk defragmenter, backup tool, file compression.
- **Device drivers** - small programs that let the OS talk to a specific printer or graphics card.


#### Application Software

Software written to do a job **for the user**.

- **General purpose / packaged**: MS Word, Excel, Photoshop, browsers.
- **Custom / bespoke**: a school's own fee-management program.


| Point | System software | Application software |
|---|---|---|
| Purpose | Runs and manages the computer | Solves a user's problem |
| Written in | Usually low-level language (assembly / C) for speed and hardware access | Usually high-level language |
| Runs | From the moment the computer starts | Only when the user opens it |
| Dependence | Independent of applications | Cannot run without system software |
| Examples | Windows, Linux, compiler, BIOS | MS Word, Chrome, Tally, VLC |



> **NOTE: Tricky PYQ - read it twice**
>
> "Which of the following is NOT true about software?" The correct choice was **"System software is written in a high-level language."** System software is normally written in a **low-level** language (assembly or C) because it must talk directly to hardware. That statement is therefore the false one.



### A2.3 Open source, freeware, proprietary



| Term | Meaning | Example |
|---|---|---|
| Open source | Source code is public; anyone may read, modify, redistribute | Linux, GIMP, LibreOffice, MySQL, Apache, Firefox |
| Freeware | Free to use but source code is NOT given | Adobe Reader, Skype |
| Shareware | Free for a trial period, then you must pay | WinRAR (nagware) |
| Proprietary / Licensed | You buy a licence; source code is secret | Windows, MS Office, CorelDRAW, Adobe Illustrator, Photoshop |



> **NOTE: Direct PYQ**
>
> "Which of the following is an example of open-source application software?" Options were GIMP, CorelDRAW, Microsoft Excel, Adobe Illustrator. Answer: **GIMP** (GNU Image Manipulation Program) - the free open-source alternative to Photoshop. The other three are all paid, closed-source products.



### A2.4 Language translators - compiler vs interpreter vs assembler


You speak English. The computer speaks only binary. A translator is needed.

- **Source code** - The program as the human wrote it (in C, Java, Python).
- **Object code / Target code** - The machine-level code produced by the translator.
- **Language processor** - The umbrella term for any translator (compiler, interpreter, assembler are all language processors).


| Translator | Input | What it does |
|---|---|---|
| Compiler | High-level language | Translates the WHOLE program at once into object code. Reports all errors together. Fast execution afterwards. |
| Interpreter | High-level language | Translates and executes LINE BY LINE. Stops at the first error. Slower execution, easier debugging. |
| Assembler | Assembly language | Converts mnemonics (ADD, MOV) into machine code |
| Linker | Object files | Joins several object files and library code into one executable |
| Loader | Executable file | Loads the executable from disk into main memory for execution |
| Preprocessor | Source code | Handles directives like #include and #define before compilation |



> **NOTE: Direct PYQ**
>
> "Which of the following is a translator that translates source code into object target code?" Options: Language processor, Interpreter, Compiler, Assembler. Answer: **Compiler**.
>
> Why not the others? "Language processor" is too general (it is the parent category). An "Interpreter" executes directly and does not normally produce a stored object file. An "Assembler" translates assembly language, not source code in the high-level sense.



### A2.5 Generations of programming languages



| Generation | Name | Description | Examples |
|---|---|---|---|
| 1GL | Machine language | Pure binary 0s and 1s | 10110000 01100001 |
| 2GL | Assembly language | Mnemonics, needs an assembler | MOV, ADD, JMP |
| 3GL | High-level / procedural | English-like, portable | C, C++, Java, FORTRAN, COBOL, Pascal, Python |
| 4GL | Very high level / non-procedural | You say WHAT you want, not HOW | SQL, MATLAB, report generators |
| 5GL | Logic / constraint / AI languages | Based on solving problems using constraints and logic | Prolog, LISP, Mercury |



> **NOTE: Direct PYQ**
>
> "Which of the following is an example of the fifth-generation language?" Options: Java, Cobol, Prolog, Python. Answer: **Prolog**. Java, Cobol and Python are all third-generation (high-level procedural / object-oriented) languages. Prolog is a logic-programming language used in Artificial Intelligence, which is the mark of 5GL.



#### Full forms you must know

- **FORTRAN** - **FOR**mula **TRAN**slation - the first successful high-level language, for scientific computing.
- **COBOL** - Common Business Oriented Language.
- **BASIC** - Beginner's All-purpose Symbolic Instruction Code.
- **ALGOL** - Algorithmic Language.
- **LISP** - LISt Processing.
- **PASCAL** - Named after Blaise Pascal (not an acronym).


## A3 Input and Output Devices



### A3.1 The rule that decides input or output


Ask one question: **which way is the information flowing?**

- Information flowing **into** the computer = **input device**
- Information flowing **out of** the computer = **output device**
- Information flowing **both ways** = **input-output device**


### A3.2 Input devices



| Device | What it does |
|---|---|
| Keyboard | Types characters. Standard QWERTY layout, 104 keys. The most common device used to make sure data is entered correctly (with on-screen validation) |
| Mouse | Pointing device; click, double-click, drag, scroll |
| Light pen | A pen-shaped device touched to the screen to draw or select. It is an INPUT device even though it works on the screen |
| Touch screen | Both input and output |
| Joystick | Gaming and simulation control |
| Trackball | An upside-down mouse; the ball is rolled with the thumb |
| Digitiser / Graphics tablet | Converts hand-drawn analog drawings into digital coordinates |
| Scanner | Converts a printed page into a digital image |
| OCR (Optical Character Recognition) | Reads printed/handwritten text from an image and turns it into editable text |
| OMR (Optical Mark Recognition) | Reads pencil marks on bubble sheets - used for OMR answer sheets |
| MICR (Magnetic Ink Character Recognition) | Reads the magnetic-ink numbers at the bottom of a bank cheque |
| Barcode / QR reader | Reads the striped or square code on products |
| Microphone | Captures sound |
| Webcam | Captures video |
| Biometric scanner | Fingerprint, iris, face |



### A3.3 Output devices



| Device | What it does |
|---|---|
| Monitor / VDU (Visual Display Unit) | Shows a soft copy on screen. Types: CRT, LCD, LED, OLED |
| Printer | Produces a hard copy on paper |
| Plotter | Draws large, precise line drawings - maps, engineering blueprints |
| Speaker / Headphone | Sound output |
| Projector | Throws the display onto a large screen |



> **NOTE: Direct PYQ**
>
> "Which of the following is an example of an output device?" Options: Mouse, Light pen, Keyboard, Visual Display Unit. Answer: **Visual Display Unit**. Mouse, light pen and keyboard are all input devices.



#### Printer classification (frequently asked)


| Class | How it prints | Examples | Quality / speed |
|---|---|---|---|
| Impact | A physical part strikes the paper through a ribbon | Dot matrix, daisy wheel, line printer | Noisy, low quality, can print carbon copies |
| Non-impact | Nothing touches the paper | Inkjet, Laser, Thermal | Quiet, high quality |
| Character printer | One character at a time | Dot matrix, daisy wheel | Slowest |
| Line printer | One whole line at a time | Drum, chain printer | Medium |
| Page printer | One whole page at a time | Laser | Fastest |


Printer resolution is measured in **DPI (dots per inch)**. Printer speed is measured in **CPS** (characters per second) for character printers, **LPM** (lines per minute) for line printers and **PPM** (pages per minute) for page printers.


### A3.4 Input-output (both-way) devices


Touch screen, modem, network interface card, hard disk, pen drive, headset with microphone, multifunction printer (print + scan).


## A4 Memory and Storage



### A4.1 The memory hierarchy - a pyramid of speed


Picture a student at a desk.

- The **book open in your hand** = register. Instantly available, but you can hold only one.
- The **few books on your desk** = cache memory. Very fast to reach.
- The **bookshelf in your room** = RAM. Bigger, a little slower.
- The **school library** = hard disk. Enormous, but slow to fetch from.
- The **archive in another city** = magnetic tape / cloud backup. Huge and cheap, extremely slow.


*Memory hierarchy: fastest and costliest at the top*
```
                    ^  FASTEST, SMALLEST, COSTLIEST per byte
                    |   +----------------------+
                    |   |      REGISTERS       |   (inside CPU, bytes)
                    |   +----------------------+
                    |   |    CACHE  L1/L2/L3   |   (KB to MB)
                    |   +----------------------+
                    |   |  MAIN MEMORY (RAM)   |   (GB)
                    |   +----------------------+
                    |   | SECONDARY: HDD / SSD |   (GB to TB)
                    |   +----------------------+
                    |   | TERTIARY: Tape, DVD  |   (TB and beyond)
                    v   +----------------------+
                        SLOWEST, LARGEST, CHEAPEST per byte
```



### A4.2 Primary memory



#### RAM - Random Access Memory

- **Volatile**: it forgets everything the moment power is lost.
- **Read and write** both allowed.
- Called "random access" because any location can be reached directly in the same amount of time - you do not have to pass through the earlier locations.
- Also called **main memory** or **working memory**.


| Point | SRAM (Static RAM) | DRAM (Dynamic RAM) |
|---|---|---|
| Storage element | Flip-flop (6 transistors) | Capacitor + 1 transistor |
| Refreshing | NOT needed - contents stay as long as power is on | Must be refreshed thousands of times per second (the capacitor leaks) |
| Speed | Very fast | Slower |
| Cost / density | Expensive, low density | Cheap, high density |
| Power | More power (but no refresh circuitry) | Less power per bit |
| Used as | Cache memory | Main memory (your 8 GB RAM stick) |



> **NOTE: Direct PYQ**
>
> "Memory that does not change its contents due to external causes is referred to as ______." Options: dynamic memory, fixed memory, static memory, temporary memory. Answer: **static memory**.
>
> Why: DRAM contents decay and must be refreshed - an external cause changes them. SRAM ("static") holds its value without refreshing. The word "static" literally means "not changing".



#### ROM - Read Only Memory

- **Non-volatile**: remembers even with the power off.
- Normally only read, not written by ordinary programs.
- Holds the **bootstrap loader / BIOS** - the first program that runs when you press the power button.


| Type | Full form | How it is written / erased |
|---|---|---|
| ROM | Read Only Memory | Programmed once at the factory (masked ROM). Can never be changed |
| PROM | Programmable ROM | Written once by the user with a special device (a "ROM burner"), then permanent |
| EPROM | Erasable Programmable ROM | Erased by exposing the chip to strong ULTRAVIOLET light through a quartz window, then rewritten |
| EEPROM | Electrically Erasable Programmable ROM | Erased and rewritten electrically, byte by byte, while in the circuit |
| Flash ROM | - | An improved EEPROM erased in blocks, very fast. Used in pen drives, SSDs, BIOS chips, memory cards |



> **NOTE: Direct PYQ**
>
> "Select an appropriate ROM type where data can be erased or destroyed using ultraviolet light." Answer: **EPROM**. The "E" for Erasable + UV window is the signature of EPROM. EEPROM and Flash are erased **electrically**, and PROM cannot be erased at all.



#### Cache memory

A small, very fast SRAM buffer sitting between the CPU and RAM. The CPU checks the cache first.

- **Cache hit** - The data the CPU wanted was found in the cache. Fast.
- **Cache miss** - Not found; the CPU must go to slower RAM. A "penalty" is paid.
- **Hit ratio** - Number of hits divided by total accesses. Higher is better.
- **Locality of reference** - The principle that makes caching work: programs tend to use the same data again soon (temporal locality) and data stored nearby (spatial locality).
- **Levels** - L1 is smallest and fastest (inside each core), then L2, then L3 (shared).


### A4.3 Secondary storage



| Medium | Access type | Notes |
|---|---|---|
| Magnetic tape | SEQUENTIAL ONLY | You must run through the tape from the beginning to reach the middle - exactly like an old audio cassette. Cheapest per GB, used for backup/archive |
| Hard Disk Drive (HDD) | Direct / random | Spinning magnetic platters, read/write head, organised into tracks, sectors, cylinders |
| Floppy disk | Direct | Obsolete, 1.44 MB |
| CD-ROM | Direct | 700 MB, read by laser |
| DVD | Direct | 4.7 GB single layer |
| Blu-ray | Direct | 25 GB per layer |
| SSD (Solid State Drive) | Direct | Flash memory, no moving parts, very fast, silent |
| Pen drive / Flash card | Direct | Flash memory over USB |
| Cloud storage | Direct over network | Google Drive, OneDrive |



> **NOTE: Direct PYQ**
>
> "Which storage media supports only sequential access?" Options: Hard disk, CD, Magnetic tape, DVD. Answer: **Magnetic tape**. Hard disks, CDs and DVDs are all direct-access (random-access) media.



#### Hard disk geometry - the words you must know

- **Track** - One concentric circle on a platter surface.
- **Sector** - A pie-slice division of a track; the smallest addressable unit (traditionally 512 bytes).
- **Cluster / Block** - A group of sectors; the smallest unit the file system allocates.
- **Cylinder** - The same-numbered track on all platters, stacked vertically.
- **Seek time** - Time for the head to move to the correct track. Usually the largest component.
- **Rotational latency** - Time for the required sector to spin under the head. On average, half a rotation.
- **Transfer time** - Time to actually read/write the data.
- **Access time** - Seek time + rotational latency + transfer time.


### A4.4 Units of memory - and the trap in them



| Unit | Size |
|---|---|
| 1 bit | A single binary digit: 0 or 1 |
| 1 nibble | 4 bits |
| 1 byte | 8 bits (one character) |
| 1 kilobyte (KB) | 1024 bytes = 2^10 bytes |
| 1 megabyte (MB) | 1024 KB = 2^20 bytes |
| 1 gigabyte (GB) | 1024 MB = 2^30 bytes |
| 1 terabyte (TB) | 1024 GB = 2^40 bytes |
| 1 petabyte (PB) | 1024 TB |
| Then | Exabyte, Zettabyte, Yottabyte |



> **NOTE: PYQ worked out - "Which statement is NOT true?"**
>
> The options were about kilobyte conversions. Let us check each.
>
> **"5 kilobytes is equal to 10,240 half bytes"** - 5 KB = 5 x 1024 = 5120 bytes. A half byte is a nibble, and each byte = 2 nibbles, so 5120 bytes = 10,240 nibbles. **TRUE.**
>
> **"3 kilobytes is equal to 24,576 bits"** - 3 x 1024 = 3072 bytes; 3072 x 8 = 24,576 bits. **TRUE.**
>
> **"4 kilobytes is equal to 4069 bytes"** - 4 x 1024 = **4096** bytes, not 4069. **FALSE - this is the answer.**
>
> **"2 kilobytes is equal to 4096 nibbles"** - 2 x 1024 = 2048 bytes; x 2 = 4096 nibbles. **TRUE.**
>
> Lesson: in this kind of question, just convert everything to bytes first and look for the one number that is slightly "off". 4069 vs 4096 is a classic digit-swap trap.



## A5 Number Systems



### A5.1 Why computers count in twos


A light switch has only two states: ON and OFF. A computer is built from millions of such switches (transistors). ON is called **1**, OFF is called **0**. That is all a computer can store. So to store the number "thirteen", the computer must write thirteen using only 0s and 1s.


| System | Base | Digits allowed |
|---|---|---|
| Binary | 2 | 0, 1 |
| Octal | 8 | 0 to 7 |
| Decimal | 10 | 0 to 9 |
| Hexadecimal | 16 | 0-9 then A=10, B=11, C=12, D=13, E=14, F=15 |



### A5.2 Positional value - the single idea behind all conversions


In decimal, 375 means 3x100 + 7x10 + 5x1, that is 3x10^2 + 7x10^1 + 5x10^0. The **position** of a digit decides its weight, and the weights are powers of the base.

The same rule works in every base. Only the base changes.


#### Any base to decimal: multiply each digit by base^position and add


*Binary 1011 to decimal*
```
1011 (base 2)
= 1x2^3 + 0x2^2 + 1x2^1 + 1x2^0
= 8 + 0 + 2 + 1
= 11 (decimal)
```



*PYQ: decimal equivalent of binary 111111*
```
Positions (left to right): 2^5 2^4 2^3 2^2 2^1 2^0
                            32  16   8   4   2   1
All six bits are 1, so add them all:
32 + 16 + 8 + 4 + 2 + 1 = 63

SHORTCUT: n ones in a row always equal (2^n - 1).
Here n = 6, so 2^6 - 1 = 64 - 1 = 63.   ANSWER = 63
```



#### Decimal to any base: divide repeatedly by the base, collect remainders bottom-up


*Decimal 45 to binary*
```
45 / 2 = 22 remainder 1   <- least significant bit
22 / 2 = 11 remainder 0
11 / 2 =  5 remainder 1
 5 / 2 =  2 remainder 1
 2 / 2 =  1 remainder 0
 1 / 2 =  0 remainder 1   <- most significant bit
Read remainders bottom to top: 101101
Check: 32 + 8 + 4 + 1 = 45. Correct.
```



### A5.3 The three shortcut conversions you must never compute the long way



#### Binary to Octal: group the bits in THREES from the right

Because 8 = 2^3, exactly three bits make one octal digit.

```
Binary 110101110  ->  110 101 110  ->  6 5 6  ->  Octal 656
```



#### Binary to Hexadecimal: group the bits in FOURS from the right

Because 16 = 2^4.

```
Binary 110101110 -> pad to 0001 1010 1110 -> 1 A E -> Hex 1AE
```



#### Octal to Binary / Hex to Binary: expand each digit

Each octal digit becomes 3 bits; each hex digit becomes 4 bits.


*Octal 743 to binary  (needed for the Gray-code question)*
```
7 = 111
4 = 100
3 = 011
So (743) octal = 111 100 011 = 111100011 in binary
```



| Decimal | Binary (4 bit) | Octal | Hex |
|---|---|---|---|
| 0 | 0000 | 0 | 0 |
| 1 | 0001 | 1 | 1 |
| 2 | 0010 | 2 | 2 |
| 3 | 0011 | 3 | 3 |
| 4 | 0100 | 4 | 4 |
| 5 | 0101 | 5 | 5 |
| 6 | 0110 | 6 | 6 |
| 7 | 0111 | 7 | 7 |
| 8 | 1000 | 10 | 8 |
| 9 | 1001 | 11 | 9 |
| 10 | 1010 | 12 | A |
| 11 | 1011 | 13 | B |
| 12 | 1100 | 14 | C |
| 13 | 1101 | 15 | D |
| 14 | 1110 | 16 | E |
| 15 | 1111 | 17 | F |



> **TIP: Memorise this table**
>
> Almost every number-system question in DSSSB can be solved in ten seconds if you know the 0-15 row by heart. Write it out from memory once a day for a week.



### A5.4 BCD - Binary Coded Decimal


In BCD, each **decimal digit** is written separately using 4 bits. It is not the same as plain binary.


*59 in plain binary vs BCD*
```
Plain binary:  59 = 111011
BCD:           5 = 0101 , 9 = 1001  ->  0101 1001
```


Because a decimal digit only goes up to 9, the six patterns **1010, 1011, 1100, 1101, 1110, 1111** (that is 10 to 15) are **invalid in BCD**.


> **NOTE: PYQ worked out - invalid input combinations of a BCD adder**
>
> "How many INVALID input combinations occur at the input of a BCD adder?" Answer given: **156**.
>
> Reasoning: a BCD adder adds two BCD digits, so it has two 4-bit inputs = 8 input lines = 2^8 = **256** total combinations. A valid BCD digit has only 10 patterns (0000 to 1001), so valid pairs = 10 x 10 = **100**. Therefore invalid = 256 - 100 = **156**.
>
> Remember the two numbers: total 256, valid 100, invalid 156.



### A5.5 Gray code - the code where only one bit changes at a time


Ordinary binary counting can change many bits at once: going from 0111 to 1000 flips all four bits. In a mechanical sensor that causes momentary wrong readings. **Gray code** is arranged so that consecutive values differ in exactly **one** bit.


#### Rule: Binary to Gray

- The **first (most significant) Gray bit = the first binary bit**, copied as it is.
- Every following Gray bit = **XOR of the two neighbouring binary bits** (the current one and the one before it).
- XOR means: same digits give 0, different digits give 1.


*PYQ worked out: represent (743) octal in Gray code*
```
Step 1 - octal to binary, 3 bits per digit:
   7 -> 111 ,  4 -> 100 ,  3 -> 011
   Binary = 1 1 1 1 0 0 0 1 1

Step 2 - binary to Gray:
   Binary : 1  1  1  1  0  0  0  1  1
            |  \  /  \  /  \/  \/  \/  \/
   Gray   : 1  0  0  0  1  0  0  1  0

   G1 = B1                = 1
   G2 = B1 XOR B2 = 1^1   = 0
   G3 = B2 XOR B3 = 1^1   = 0
   G4 = B3 XOR B4 = 1^1   = 0
   G5 = B4 XOR B5 = 1^0   = 1
   G6 = B5 XOR B6 = 0^0   = 0
   G7 = B6 XOR B7 = 0^0   = 0
   G8 = B7 XOR B8 = 0^1   = 1
   G9 = B8 XOR B9 = 1^1   = 0

   ANSWER = 100010010
```



#### Rule: Gray to Binary

- First binary bit = first Gray bit.
- Each next binary bit = previous **binary** bit XOR current **Gray** bit.


| Decimal | Binary | Gray code |
|---|---|---|
| 0 | 000 | 000 |
| 1 | 001 | 001 |
| 2 | 010 | 011 |
| 3 | 011 | 010 |
| 4 | 100 | 110 |
| 5 | 101 | 111 |
| 6 | 110 | 101 |
| 7 | 111 | 100 |



> **TIP: Where Gray code is used**
>
> Rotary shaft encoders, position sensors, and - very important for the exam - the **row and column labelling of a Karnaugh map**. K-map rows are labelled 00, 01, 11, 10 (Gray order), not 00, 01, 10, 11 (binary order).



### A5.6 Complements and signed numbers


Computers must store negative numbers too. Three schemes exist.


#### 1. Sign-magnitude

The leftmost bit is the sign (0 = positive, 1 = negative); the rest is the plain magnitude.
+5 = 0101, -5 = 1101. Problem: there are two zeros (+0 = 0000 and -0 = 1000).


#### 2. One's complement

Negative numbers are made by **flipping every bit**.
+5 = 0101, -5 = 1010. Still has two zeros.


#### 3. Two's complement - what real computers use

**Rule: flip every bit, then add 1.** (Equivalently: r's complement with r = 2.)


*PYQ worked out: 2's complement of binary 1100*
```
Step 1 - invert (1's complement):  1100 -> 0011
Step 2 - add 1:                    0011 + 1 = 0100

ANSWER = 0100

Fast trick: copy the bits from the right up to and including the FIRST 1,
then flip everything to the left of it.
    1100 -> keep "100", flip "1" -> 0 100 -> 0100.  Same answer.
```



#### The general formula

For a number N with n digits in base r:
- **(r-1)'s complement** - (r^n - 1) - N. For binary this is the 1's complement (just invert all bits).
- **r's complement** - r^n - N, which equals the (r-1)'s complement plus 1. For binary this is the 2's complement.
- **9's complement (decimal)** - Subtract each digit from 9.
- **10's complement (decimal)** - 9's complement + 1.


> **NOTE: PYQ worked out - the 3's complement question**
>
> "A register contains a 3's complement number 10100. If it is divided by 2, find the value of the register." Answer given: **01010**.
>
> The key idea being tested is much simpler than the words suggest: **in a register, dividing a binary number by 2 means shifting every bit one place to the RIGHT** (and dividing by 4 means shifting twice, and so on). Multiplying by 2 means shifting one place LEFT.
>
> 10100 shifted right by one place = 01010. That matches the answer.
>
> Memorise: **right shift = divide by 2; left shift = multiply by 2.** This single fact answers many questions.



### A5.7 Character codes



| Code | Bits | Notes |
|---|---|---|
| BCD | 4 per digit | Only decimal digits |
| ASCII | 7 bits (128 characters), extended to 8 bits (256) | The standard for English text. 'A' = 65, 'a' = 97, '0' = 48 |
| EBCDIC | 8 bits | IBM mainframe code |
| Unicode | 16 bits (UTF-16) or variable (UTF-8) | Supports every script in the world - Devanagari, Chinese, emoji. UTF-8 is backward-compatible with ASCII |



> **TIP: The three ASCII values worth memorising**
>
> 'A' = 65, 'a' = 97 (exactly 32 more than 'A'), '0' = 48. From these you can work out any other letter or digit.



## A6 Boolean Algebra and Logic Gates



### A6.1 What a logic gate is


A **gate** is a tiny electronic circuit that takes one or more 0/1 inputs and produces one 0/1 output according to a fixed rule. Think of it as a security guard who follows one instruction and never deviates.


### A6.2 The seven gates and their truth tables



#### AND gate - "both must agree"

Output is 1 only if **all** inputs are 1. Think of two switches in series - the bulb glows only if both are pressed. Symbol: A.B or AB.


| A | B | A AND B |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |



#### OR gate - "at least one is enough"

Output is 1 if **any** input is 1. Two switches in parallel. Symbol: A + B.


| A | B | A OR B |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |



#### NOT gate (inverter) - "the opposite"

One input, one output. Turns 0 into 1 and 1 into 0. Symbol: A' or A-bar.


#### NAND gate - NOT of AND

Output is 0 only when **all** inputs are 1; otherwise 1. It is the exact opposite of AND.


#### NOR gate - NOT of OR

Output is 1 only when **all** inputs are 0; otherwise 0.


#### XOR gate (Exclusive OR) - "different means yes"

Output is 1 when the inputs are **different**. Symbol: A (+) B.


| A | B | A XOR B |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |



#### XNOR gate (Exclusive NOR) - "same means yes"

Output is 1 when the inputs are the **same**. Also called the equivalence or comparator gate.


| A | B | A XNOR B |
|---|---|---|
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |



> **NOTE: Direct PYQ**
>
> "What does the XNOR gate output when A=1 and B=0?" Answer: **0**.
>
> Reasoning: XNOR gives 1 only when both inputs are identical. Here A=1 and B=0 are different, so the output is 0. Do not confuse this with XOR, which would give 1 for these inputs.



> **TIP: The one-line memory hook for XOR and XNOR**
>
> XOR = "**X** marks the **difference**" - output 1 when inputs differ.
> XNOR = "**N**o difference" - output 1 when inputs are the same.



### A6.3 Universal gates - NAND and NOR


A gate is called **universal** if you can build **every** other gate using only copies of it.

**NAND and NOR are the two universal gates.** From NAND alone you can build NOT, AND, OR, XOR, XNOR - and therefore any digital circuit at all. The same is true of NOR alone.


*Building the basic gates from NAND only*
```
NOT A          = A NAND A
A AND B        = (A NAND B) NAND (A NAND B)
A OR B         = (A NAND A) NAND (B NAND B)
```


Why does industry care? Because a factory can mass-produce a single type of chip and build anything from it. This lowers cost and simplifies design.


> **NOTE: PYQ worked out**
>
> "Which of the following statements is FALSE about universal logic gates?" The options were:
> (a) All basic logic gates can be implemented through universal logic gates - **TRUE**
> (b) NOR gate is known as universal logic gate - **TRUE**
> (c) NAND gate is known as universal logic gate - **TRUE**
> (d) All basic logic gates **cannot** be implemented using universal logic gates - **FALSE**
>
> Answer: option (d). It directly contradicts the definition of a universal gate.



### A6.4 Boolean algebra laws



| Law | OR form | AND form |
|---|---|---|
| Identity | A + 0 = A | A . 1 = A |
| Null / Dominance | A + 1 = 1 | A . 0 = 0 |
| Idempotent | A + A = A | A . A = A |
| Complement | A + A' = 1 | A . A' = 0 |
| Involution | (A')' = A | - |
| Commutative | A + B = B + A | A . B = B . A |
| Associative | A + (B + C) = (A + B) + C | A(BC) = (AB)C |
| Distributive | A + BC = (A+B)(A+C) | A(B + C) = AB + AC |
| Absorption | A + AB = A | A(A + B) = A |
| Redundancy | A + A'B = A + B | A(A' + B) = AB |
| De Morgan 1 | (A + B)' = A' . B' | - |
| De Morgan 2 | (A . B)' = A' + B' | - |



> **TIP: De Morgan in plain words**
>
> "**Break the bar, change the sign.**" When you remove a NOT that covers a whole expression, every AND becomes OR, every OR becomes AND, and each individual variable gets its own NOT.



> **NOTE: PYQ worked out - using the distributive law**
>
> "Find the value of F = xy + x'z using distributive law." Answer: **(x' + y)(x + z)(y + z)**.
>
> The relevant identity here is the second distributive law read backwards:
> A + BC = (A + B)(A + C)
>
> Take F = xy + x'z. Treat it as a sum of two products and expand:
> xy + x'z = (xy + x')(xy + z)              [distributing over the sum]
> = (x + x')(y + x')(x + z)(y + z) [distributing again]
> = 1 . (x' + y)(x + z)(y + z)
> = (x' + y)(x + z)(y + z)
>
> Note (x + x') = 1 by the complement law, which is why that factor disappears. This kind of question is really a test of whether you know the complement law and the distributive law together.



> **NOTE: PYQ worked out - XOR identity**
>
> "A three-variable function (A (+) B (+) C)' = ?" Answer: **A (+) B (.) C**, i.e. A XOR B XNOR C.
>
> The rule to remember: **complementing an XOR chain is the same as complementing any ONE of its terms.** So (A (+) B (+) C)' = A (+) B (+) C' , and since (+) with a complement on the last operand is exactly XNOR, this equals A (+) B XNOR C.
>
> Two useful XOR facts:
> A (+) 0 = A ; A (+) 1 = A' ; A (+) A = 0 ; A (+) A' = 1.
> XOR of an odd number of 1s is 1; XOR of an even number of 1s is 0. (This is the parity property.)



### A6.5 SOP, POS, minterms and maxterms


- **Literal** - A variable or its complement: A, A', B.
- **Minterm** - A product (AND) term containing **every** variable exactly once. For 3 variables there are 8 minterms, m0 to m7.
- **Maxterm** - A sum (OR) term containing every variable exactly once. M0 to M7.
- **SOP (Sum of Products)** - OR of AND terms. Example: F = AB' + A'C. Built from the rows where the output is **1**.
- **POS (Product of Sums)** - AND of OR terms. Example: F = (A+B)(A'+C). Built from the rows where the output is **0**.
- **Canonical form** - Every term contains every variable (pure minterms / maxterms).
- **Standard form** - Terms may be missing some variables.


### A6.6 Karnaugh map (K-map)


A K-map is a picture of a truth table drawn so that **physically adjacent squares differ in only one variable**. That lets you spot simplifications by eye instead of doing algebra.


*A 2-variable and a 3-variable K-map skeleton*
```
 2-variable                     3-variable  (note the GRAY order of BC)
        B=0   B=1                        BC=00  01   11   10
      +-----+-----+                    +-----+-----+-----+-----+
 A=0  | m0  | m1  |               A=0  | m0  | m1  | m3  | m2  |
      +-----+-----+                    +-----+-----+-----+-----+
 A=1  | m2  | m3  |               A=1  | m4  | m5  | m7  | m6  |
      +-----+-----+                    +-----+-----+-----+-----+
```



#### The rules of grouping

- Group only **1s** when simplifying SOP form; group only **0s** when simplifying POS form.
- Group sizes must be a **power of two**: 1, 2, 4, 8, 16.
- Groups must be **rectangular** (horizontal or vertical), never diagonal.
- Make each group **as large as possible** - a bigger group removes more variables.
- Groups **may overlap**, and they **wrap around** the edges of the map (left edge is adjacent to right edge, top to bottom).
- A group of 2 removes 1 variable; a group of 4 removes 2 variables; a group of 8 removes 3 variables.
- **Don't-care** conditions (marked X) may be included in a group if that makes the group bigger, or ignored otherwise.


> **NOTE: PYQ worked out - "Which statement is FALSE about K-maps?"**
>
> The options were:
> (a) K-map is used to simplify POS form - **TRUE** (group the 0s)
> (b) In K-map, the rows and columns are represented in **binary code sequence** - **FALSE**
> (c) You group adjacent squares in powers of two, covering as many minterms/maxterms as possible - **TRUE**
> (d) K-map is used to simplify SOP form - **TRUE**
>
> Answer: option (b). K-map rows and columns are labelled in **GRAY code** order (00, 01, 11, 10), not binary order (00, 01, 10, 11). This is the whole reason adjacent cells differ by exactly one bit. This is one of the most commonly asked "false statement" questions in the subject - lock it in.


- **Prime implicant** - A group that cannot be made any larger.
- **Essential prime implicant** - A prime implicant that is the only one covering some particular 1. It must appear in the final answer.
- **Quine-McCluskey method** - A tabular alternative to the K-map, used when there are more than 5 or 6 variables. It can be programmed; a K-map cannot.


## A7 Combinational and Sequential Circuits



### A7.1 The big split



| Point | Combinational circuit | Sequential circuit |
|---|---|---|
| Output depends on | ONLY the present inputs | Present inputs AND past history (state) |
| Memory | None | Has memory (flip-flops) |
| Clock | Not needed | Usually clock-driven |
| Examples | Adder, subtractor, multiplexer, decoder, encoder, comparator | Flip-flop, register, counter, shift register, RAM |



### A7.2 Adders



#### Half adder

Adds two single bits. Two outputs: Sum and Carry.
- **Sum** - A XOR B
- **Carry** - A AND B


| A | B | Sum | Carry |
|---|---|---|---|
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |



#### Full adder

Adds **three** bits: A, B and a carry-in from the previous stage.
- **Sum** - A XOR B XOR Cin
- **Carry-out** - AB + Cin(A XOR B)

A full adder can be built from **two half adders plus one OR gate**. An n-bit **ripple carry adder** is n full adders chained together; it is simple but slow because each carry must "ripple" through. A **carry look-ahead adder** computes carries in parallel and is much faster.


#### BCD adder

A 4-bit binary adder plus correction logic. If the result exceeds 9 (or a carry is produced), the circuit **adds 6 (0110)** to bring the answer back into valid BCD.


### A7.3 Multiplexer and Demultiplexer


- **Multiplexer (MUX)** - **Many inputs, one output.** A data selector. A 2^n-to-1 MUX needs n select lines. Think of a TV remote choosing which channel reaches the single screen. Also called a "many-to-one" or parallel-to-serial converter.
- **Demultiplexer (DEMUX)** - **One input, many outputs.** The reverse of a MUX; the select lines decide which output the input is routed to. One-to-many, serial-to-parallel.

A MUX is a **universal logic module** - any Boolean function of n variables can be built with a single 2^n-to-1 multiplexer.


### A7.4 Encoder and Decoder


- **Encoder** - Converts 2^n input lines into an n-bit code. Many inputs to few outputs. A "priority encoder" resolves the case where two inputs are active at once.
- **Decoder** - Converts an n-bit code into 2^n output lines, activating exactly one. Few inputs to many outputs. Used for memory address selection and for driving seven-segment displays.


### A7.5 Flip-flops - one bit of memory


A **latch** is level-triggered (responds while the enable signal is high). A **flip-flop** is edge-triggered (responds only at the instant the clock rises or falls). A flip-flop stores exactly one bit.


| Flip-flop | Inputs | Behaviour | Problem |
|---|---|---|---|
| SR (Set-Reset) | S, R | S=1 sets Q to 1; R=1 resets Q to 0 | S=R=1 is FORBIDDEN (invalid / race condition) |
| JK | J, K | Same as SR but J=K=1 TOGGLES the output | Removes the forbidden state; race-around in level-triggered versions |
| D (Data / Delay) | D | Q simply follows D at the clock edge | None - the simplest and most used |
| T (Toggle) | T | T=1 toggles, T=0 holds | Made from JK with J=K=T |
| Master-Slave | - | Two flip-flops in series with inverted clocks | Solves the JK race-around problem |


- **Setup time** - How long the input must be stable BEFORE the clock edge.
- **Hold time** - How long the input must stay stable AFTER the clock edge.
- **Propagation delay** - Time between the clock edge and the output actually changing.


### A7.6 Counters


A counter is a chain of flip-flops that counts clock pulses.


| Type | How it works | Speed |
|---|---|---|
| Asynchronous / Ripple counter | The output of one flip-flop clocks the next. Delays add up (ripple through). | Slow; delay = n x propagation delay |
| Synchronous counter | All flip-flops share one common clock and change together | Fast; delay = one propagation delay |
| Up counter | Counts 0, 1, 2, ... | - |
| Down counter | Counts ..., 2, 1, 0 | - |
| Ring counter | A single 1 circulates through n flip-flops; n states | - |
| Johnson counter | Twisted ring counter; 2n states from n flip-flops | - |



#### Modulus of a counter

The **modulus (MOD)** is the number of distinct states before the count repeats. An n-flip-flop counter has a maximum modulus of 2^n. A MOD-10 counter (decade counter) counts 0 to 9. To build a MOD-m counter you need n flip-flops where 2^n is greater than or equal to m.


> **NOTE: PYQ worked out - cascading counters**
>
> "A Mod-6 counter and a Mod-8 counter in cascade give a ______ counter." Answer: **Mod-48**.
>
> Rule: when counters are cascaded (connected one after another), the moduli **multiply**.
> 6 x 8 = 48.
>
> Do not add them (that would give 14) and do not divide. Cascading multiplies. This is because the second counter advances only once for every complete cycle of the first.



> **NOTE: PYQ worked out - ripple counter skipping a count**
>
> "For what minimum value of propagation delay in each flip-flop will a 10-bit ripple counter skip a count when it is clocked at 10 MHz?" Answer: **10 ns**.
>
> Reasoning. In a **ripple** counter the delays of the flip-flops add up. If each flip-flop has delay t, the worst-case total settling time for 10 flip-flops is 10t. The counter will miscount (skip) if the total delay becomes as large as one clock period.
>
> Clock frequency = 10 MHz, so the clock period T = 1 / (10 x 10^6) = 100 ns.
>
> Setting 10 x t = 100 ns gives t = **10 ns**.
>
> The general formula: **t (minimum for error) = clock period / number of flip-flops.**




---

# PART B - Computer Organisation and Architecture

> *How the CPU is wired inside, how it fetches instructions, and how cache and buses move data around.*



## B1 Architecture vs Organisation, and the Boot Process



### B1.1 The difference between architecture and organisation


Imagine buying a car. **Architecture** is the driver's view: there is a steering wheel, a brake, an accelerator, five gears. **Organisation** is the mechanic's view: which pipes carry the fuel, how the gearbox teeth mesh, how thick the brake pads are.

- **Computer Architecture** - What the machine looks like to the **programmer**. The instruction set, the number of registers, the addressing modes, the data types. It answers "**WHAT** does the machine do?"
- **Computer Organisation** - How the architecture is actually **built** in hardware. Control signals, bus widths, circuit design. It answers "**HOW** is it done?"

Two computers can share the same architecture (both run the same programs) but have completely different organisations (one is cheap and slow, one is expensive and fast).


### B1.2 Types of computer architecture



| Architecture | Idea |
|---|---|
| Von Neumann (Princeton) | ONE memory and ONE bus shared by both instructions and data. Simple and cheap, but instruction fetch and data fetch cannot happen at the same time - this bottleneck is called the "von Neumann bottleneck" |
| Harvard | SEPARATE memories and separate buses for instructions and data. Both can be fetched simultaneously, so it is faster. Used in DSPs and microcontrollers |
| Modified Harvard | Separate caches for instruction and data, but one unified main memory. What almost all modern CPUs actually use |
| Instruction Set Architecture (ISA) | The abstract model of the machine as seen by software: instructions, registers, addressing modes, data types |
| Microarchitecture | The specific hardware implementation of an ISA (pipeline depth, cache sizes, execution units) |



> **NOTE: PYQ worked out**
>
> "Which of the following is NOT a type of computer architecture?" Options: Micro Architecture, Harvard Architecture, **Software Architecture**, Instruction Set Architecture. Answer: **Software Architecture**.
>
> Why: Micro-architecture, Harvard architecture and ISA are all genuine hardware-architecture terms. "Software architecture" belongs to **Software Engineering** - it describes how program modules are organised, not how a computer is built.



### B1.3 What happens when you press the power button


This sequence is a favourite exam target. Learn the order.


*The boot sequence*
```
1.  You press POWER. Electricity reaches the motherboard.
2.  The CPU automatically starts executing from a fixed address in ROM.
3.  BIOS (stored in ROM / flash) starts running.
4.  BIOS runs POST - Power On Self Test - checking RAM, keyboard,
    disk, graphics. Beep codes report failures.
5.  BIOS reads its saved settings from the CMOS chip.
6.  BIOS finds the boot device and loads the BOOTSTRAP LOADER
    (also called the boot loader) from the Master Boot Record.
7.  The bootstrap loader loads the OPERATING SYSTEM KERNEL into RAM.
8.  The kernel takes control, starts drivers and services, shows login.
```


- **BIOS** - **Basic Input Output System**. Firmware stored in ROM/flash on the motherboard. It initialises hardware and hands control to the OS. Its modern replacement is **UEFI**.
- **POST** - **Power On Self Test**. Performed by the BIOS **immediately after the system is switched ON** - not after shutdown.
- **CMOS chip** - **Complementary Metal Oxide Semiconductor**. A tiny low-power memory that stores BIOS settings and the system clock. It is kept alive by a **small button battery (CR2032) located on the motherboard** - that is why your PC remembers the date even when unplugged.
- **Bootstrap program** - The small program that loads the operating system. It is stored in **ROM**, never in RAM, because RAM is empty when the machine starts.
- **Cold boot** - Starting a completely powered-off computer.
- **Warm boot** - Restarting an already running computer (Ctrl+Alt+Del) - POST is usually skipped.


> **NOTE: PYQ worked out - "Which statement is true?"**
>
> (a) POST is the process performed by BIOS immediately after the system is **shutdown** - FALSE, it happens at **start-up**.
> (b) The bootstrap program is stored in **RAM** - FALSE, it is in **ROM**.
> (c) **CMOS chip is powered by the battery located on the motherboard** - TRUE. This is the answer.
> (d) BIOS was developed by **Charles Babbage** - FALSE. Babbage (1791-1871) designed the Difference Engine and Analytical Engine and is called the **Father of the Computer**; he died a century before BIOS existed. BIOS was coined by **Gary Kildall** for CP/M.



> **TIP: Famous names you should recognise**
>
> Charles Babbage - Father of the Computer (Analytical Engine). Ada Lovelace - first programmer. Alan Turing - Turing machine, father of AI/theoretical CS. John von Neumann - stored-program concept. Blaise Pascal - Pascaline calculator. Herman Hollerith - punched cards, founded the company that became IBM. Tim Berners-Lee - World Wide Web. Dennis Ritchie - C language and UNIX. Ken Thompson - UNIX. Bjarne Stroustrup - C++. James Gosling - Java. Guido van Rossum - Python. Linus Torvalds - Linux kernel. E. F. Codd - relational database model.



## B2 Inside the CPU - Registers, Buses and the Instruction Cycle



### B2.1 Registers - the CPU's scratch pad


A register is a very small, very fast storage location **inside** the CPU. If RAM is your bookshelf, registers are the two hands you hold a book with.


| Register | Full form | Job |
|---|---|---|
| PC | Program Counter | Holds the ADDRESS of the NEXT instruction to be executed. Also called Instruction Pointer |
| IR | Instruction Register | Holds the instruction CURRENTLY being executed / decoded |
| MAR | Memory Address Register | Holds the address of the memory location to be read or written |
| MDR / MBR | Memory Data (Buffer) Register | Holds the data just read from, or about to be written to, memory |
| AC | Accumulator | The main working register where arithmetic and logic results are collected |
| General purpose | R0, R1, R2 ... | Hold operands and intermediate values |
| Flag register / PSW | Program Status Word | Individual status bits: Zero, Carry, Sign, Overflow, Parity, Interrupt-enable |
| SP | Stack Pointer | Points to the top of the stack |
| Index register | - | Holds an offset used in indexed addressing |



> **NOTE: PYQ worked out**
>
> "What is the size of the computer accumulator register?" Answer given: **4 bytes**.
>
> Reasoning: the accumulator is normally the same width as the machine's word size. On a standard 32-bit machine, one word = 32 bits = **4 bytes**. That is the intended answer. (On a 64-bit machine it would be 8 bytes, and on old 8-bit machines it was 1 byte - but for DSSSB, treat "accumulator size" as 4 bytes / 32 bits unless the question states otherwise.)



### B2.2 Buses - the roads inside a computer


A **bus** is simply a **bundle of parallel wires** that carries bits from one unit to another. If it has 32 wires, 32 bits travel together in one go.


| Bus | Carries | Direction | Width decides |
|---|---|---|---|
| Address bus | The memory address being accessed | One-way (CPU to memory) | How much memory can be addressed: n lines = 2^n locations |
| Data bus | The actual data | Two-way (bidirectional) | How many bits move per transfer (the word size) |
| Control bus | Control and timing signals: READ, WRITE, CLOCK, interrupt, reset | Mixed | - |



> **NOTE: PYQ worked out**
>
> "A computer bus line is made up of which of the following components?" Options: Registers, **Set of parallel lines**, Accumulators, RAM and ROM. Answer: **Set of parallel lines**.
>
> This is a definition question. A bus is physically nothing more than a group of parallel conductors (wires or PCB traces). Registers and accumulators are storage devices, not buses.



> **TIP: Address bus arithmetic - asked often**
>
> If the address bus has **n** lines, the CPU can address **2^n** distinct locations.
> - 16 lines to 2^16 = 64 KB
> - 20 lines to 2^20 = 1 MB
> - 32 lines to 2^32 = 4 GB
> - 36 lines to 2^36 = 64 GB
> Conversely, to address 32 GB (2^35 bytes) you need **35** address lines.



### B2.3 The instruction cycle (machine cycle)


Every single thing a computer does is this loop, repeated billions of times per second. The **Control Unit** manages it.


*The Fetch - Decode - Execute - Store cycle*
```
   +--> FETCH   : Use the PC to read the next instruction from memory
   |              into the IR. Then increment the PC.
   |
   |    DECODE  : The Control Unit works out what the instruction means
   |              and which operands it needs.
   |
   |    EXECUTE : The ALU (or another unit) actually performs the
   |              operation. Operands may be fetched from memory here.
   |
   +--- STORE   : The result is written back to a register or memory.
        (also called write-back)
```



> **NOTE: Two PYQs on this cycle**
>
> "Which cycle is primarily managed by the Control Unit?" Answer: **Instruction cycle (Fetch-Decode-Execute cycle)**.
>
> "Select the INCORRECT option among the phases of the CPU Instruction Cycle." Options: Execute, **Encode**, Store, Fetch. Answer: **Encode**. The phases are Fetch, Decode, Execute, Store. "Encode" is not a phase - the instruction is **decoded**, never encoded, by the CPU.


- **Fetch cycle** - Also called the instruction cycle's first phase; involves PC, MAR, MDR, IR.
- **Machine cycle** - The set of steps to complete one instruction.
- **Clock cycle** - One tick of the system clock. One machine cycle takes several clock cycles.
- **CPI** - Cycles Per Instruction. Lower is better.
- **MIPS** - Millions of Instructions Per Second. MIPS = Clock frequency / (CPI x 10^6).
- **Interrupt** - A signal that makes the CPU pause its current program, save its state, run an Interrupt Service Routine, and then resume. Checked at the **end** of each instruction cycle.


### B2.4 Pipelining


Think of a laundry: wash, dry, fold. Doing one load completely before starting the next wastes machines. Instead, while load 1 dries, load 2 washes. That is pipelining.

In a CPU, the instruction cycle stages overlap so that several instructions are in progress at once. A **k-stage pipeline** can in the ideal case be k times faster.

- **Speedup** - Ideally equal to the number of stages k.
- **Structural hazard** - Two instructions need the same hardware unit at the same time.
- **Data hazard** - An instruction needs a result that the previous instruction has not produced yet. Fixed by forwarding/bypassing or by stalling (inserting bubbles).
- **Control hazard** - A branch instruction makes the pre-fetched instructions wrong. Fixed by branch prediction.
- **Superscalar** - More than one instruction issued per clock cycle using multiple pipelines.


## B3 RISC and CISC



### B3.1 Two philosophies


Imagine giving directions. **CISC** says: "Take the airport shuttle" - one powerful instruction that does many things. **RISC** says: "Walk 100 m, turn left, walk 50 m, enter gate 3" - many simple steps, each very quick.


| Point | CISC | RISC |
|---|---|---|
| Full form | Complex Instruction Set Computer | Reduced Instruction Set Computer |
| Number of instructions | Large (hundreds) | Small (typically under 100) |
| Instruction length | Variable | Fixed (usually one word) |
| Instruction complexity | One instruction may do several low-level operations | One instruction does one simple operation |
| Clock cycles per instruction | Many, and variable | Mostly ONE (with pipelining) |
| Addressing modes | Many (12 or more) | Few (3 to 5) |
| Registers | Fewer | Many (32 or more) |
| Memory access | Arithmetic instructions can access memory directly | Only LOAD and STORE touch memory |
| Control unit | Microprogrammed (uses microcode) | Hardwired |
| Pipelining | Difficult | Easy and efficient |
| Code size | Smaller program, more complex hardware | Larger program, simpler hardware |
| Compiler burden | Less | More (the compiler must optimise) |
| POWER CONSUMPTION | Higher | LOWER - most energy efficient |
| Examples | Intel x86, AMD, VAX, IBM 370 | ARM, MIPS, SPARC, RISC-V, PowerPC, Apple M-series |



> **NOTE: PYQ worked out**
>
> "Which architecture is the most energy efficient?" Options: CISC, IANA, ISA, **RISC**. Answer: **RISC**.
>
> Why: RISC uses simple fixed-length instructions and a hardwired control unit, so it needs far less decoding circuitry and switches fewer transistors per instruction. That is exactly why every mobile phone uses an ARM (RISC) processor - battery life. Note the distractors: IANA is the Internet Assigned Numbers Authority (a networking body, not an architecture) and ISA is a general term, not a specific competing design.



### B3.2 ISA design goals



> **NOTE: PYQ worked out**
>
> "Which of the following is a key design goal of an Instruction Set Architecture?" Answer: **Balancing simplicity and performance for ease of programming and efficiency**.
>
> Why the others are wrong: "minimising transistor count" is a chip-level manufacturing concern, not an ISA goal. "Ensuring only complex instructions are supported" is the opposite of good design. "Maximising instruction decode time" is absurd - you want to **minimise** decode time.
>
> A good ISA aims for: completeness, orthogonality (instructions and addressing modes combine freely), regularity, efficiency, and backward compatibility.



## B4 Addressing Modes



### B4.1 What an addressing mode is


An instruction must say **where** its operand is. The addressing mode is the rule that tells the CPU how to find it.

Everyday analogy for finding a friend's house:
- I hand you the friend himself - **immediate** (the value is right here).
- I say "he is in room 5" - **direct** (here is the exact address).
- I say "the address is written on the note in room 5" - **indirect** (go there to get the real address).
- I say "he is in the register you are holding" - **register**.
- I say "the address is in register R2" - **register indirect**.


| Mode | How the operand is found | Example |
|---|---|---|
| Immediate | The operand VALUE is inside the instruction itself | MOV R1, #25 |
| Register | The operand is in a register | MOV R1, R2 |
| Direct / Absolute | The instruction contains the memory ADDRESS of the operand | MOV R1, 5000 |
| Indirect | The instruction contains an address; that memory location contains the real address | MOV R1, (5000) |
| Register indirect | A register holds the ADDRESS of the operand. Written with brackets around the register | ADD R1, [R2] |
| Indexed | Effective address = base address + contents of index register | MOV R1, 1000(R2) |
| Base register | Effective address = contents of base register + displacement | Used for relocatable code |
| Relative / PC-relative | Effective address = PC + offset. Used for branches | JMP +8 |
| Auto-increment | Register is used as a pointer, then automatically incremented | MOV R1, (R2)+ |
| Auto-decrement | Register is decremented first, then used | MOV R1, -(R2) |
| Implied / Implicit | The operand is understood, not written | CLA (clear accumulator), NOP, INC A |
| Stack | Operand is on the top of the stack | PUSH, POP |



> **NOTE: PYQ worked out**
>
> "Which of the following is an addressing mode used in an instruction of the form ADD R1, [R2]?" Options: **Register Indirect**, Register, Indexed Register, Assembly Register. Answer: **Register Indirect**.
>
> The square brackets are the give-away. `R2` alone would be *register* mode (the value is in R2). `[R2]` means "the value at the memory address stored in R2" - the register acts as a pointer. That is register indirect. Note "Assembly Register" is not a real addressing mode at all.


- **Effective Address (EA)** - The final actual memory address the CPU computes and uses.
- **Zero-address instruction** - Uses a stack; operands are implied (PUSH/POP machines).
- **One-address instruction** - Uses an accumulator; one operand is implied.
- **Two-address instruction** - One operand doubles as source and destination.
- **Three-address instruction** - Both sources and the destination are named separately.


## B5 Cache Memory and Memory Mapping



### B5.1 Why cache exists


The CPU is extremely fast; RAM is comparatively slow. If the CPU had to wait for RAM every time, most of its speed would be wasted. So a small block of very fast SRAM - the **cache** - keeps copies of the data the CPU is most likely to need next.

This works because of the **principle of locality of reference**:
- **Temporal locality** - data used now will probably be used again soon (a loop counter).
- **Spatial locality** - data near what you just used will probably be needed soon (the next element of an array).


### B5.2 The three mapping techniques


Main memory is divided into **blocks**; the cache is divided into equal-sized **lines** (or slots). Mapping decides which memory block may sit in which cache line.


| Technique | Rule | Advantage | Disadvantage |
|---|---|---|---|
| Direct mapping | Each memory block can go in exactly ONE cache line: line = block number MOD number of lines | Simplest, cheapest, fastest lookup | Very inflicted by conflict misses; two hot blocks fighting for one line |
| Fully associative | A block may go in ANY cache line | Fewest misses, most flexible | Needs to compare the tag against every line - expensive hardware |
| Set associative | The cache is divided into sets of k lines. A block maps to one SET, and may go anywhere within that set (called k-way) | A practical compromise; used in all real CPUs | Moderate complexity |



### B5.3 Address breakdown - how to solve cache numericals



*Address field layout for each mapping type*
```
DIRECT MAPPED:        | TAG | LINE (or block) number | WORD offset |
SET ASSOCIATIVE:      | TAG | SET number             | WORD offset |
FULLY ASSOCIATIVE:    | TAG |                        | WORD offset |
```


The universal method:
1. Compute the **word offset bits** = log2(block size in words).
2. Compute **number of cache lines** = cache size / block size.
3. For set associative, **number of sets** = number of lines / associativity; set bits = log2(number of sets).
4. **TAG bits = total address bits - set bits - offset bits.**


> **NOTE: PYQ worked out - the TAG field question**
>
> "A four-way set-associative cache memory unit with a capacity of 32 KB is built using a block size of 1 K words. The word length is 8 bits. The size of the physical address space is 32 GB. The number of bits for the TAG field is ____." Answer: **22**.
>
> Step 1 - total physical address bits.
> Address space = 32 GB = 2^5 x 2^30 = 2^35 bytes. Word length is 8 bits = 1 byte, so 2^35 words also. Total address bits = **35**.
>
> Step 2 - block (word) offset bits.
> Block size = 1 K words = 2^10 words, so offset = **10 bits**.
>
> Step 3 - number of cache lines.
> Cache capacity = 32 KB = 2^15 bytes = 2^15 words. Lines = 2^15 / 2^10 = 2^5 = **32 lines**.
>
> Step 4 - number of sets.
> Four-way set associative means 4 lines per set. Sets = 32 / 4 = 8 = 2^3, so set bits = **3**.
>
> Step 5 - TAG bits.
> TAG = 35 - 3 - 10 = **22 bits.**



### B5.4 Cache performance and write policies


- **Hit ratio (H)** - hits / total accesses.
- **Miss ratio** - 1 - H.
- **Average access time** - H x (cache time) + (1 - H) x (miss penalty). Learn this formula.
- **Compulsory miss** - First-ever reference to a block (also called a cold-start miss).
- **Conflict miss** - Block evicted because another block wanted the same line. Worst in direct mapping.
- **Capacity miss** - The cache is simply too small to hold the working set.


| Write policy | What happens on a write |
|---|---|
| Write-through | Data is written to BOTH cache and main memory immediately. Simple and always consistent, but slower |
| Write-back (copy-back) | Data is written only to the cache; a "dirty bit" is set, and main memory is updated only when the block is evicted. Faster, but memory is temporarily stale |
| Write allocate | On a write miss, the block is first loaded into the cache |
| No-write allocate | On a write miss, the data is written straight to memory |



#### Replacement algorithms (which cache line to throw out)

- **LRU** - Least Recently Used - discard the line unused for the longest time. Most common and most effective.
- **FIFO** - First In First Out - discard the oldest loaded line.
- **LFU** - Least Frequently Used - discard the line with the fewest accesses.
- **Random** - Pick any line. Surprisingly decent and very cheap.
- **Optimal (OPT/MIN)** - Discard the line that will not be needed for the longest time in future. Impossible to implement (needs the future) but used as a theoretical benchmark.


### B5.5 Interleaved and associative memory


- **Memory interleaving** - Main memory is split into several independent modules that can be accessed simultaneously, so consecutive addresses lie in different modules. Increases effective bandwidth.
- **Associative memory / CAM** - **Content Addressable Memory**. You search by CONTENT rather than by address - you present the data and the memory tells you where it is. Very fast, very expensive. Used in cache tag lookup, TLBs and network routers.
- **Virtual memory** - Covered fully in Part C (Operating Systems).


## B6 I/O Organisation



### B6.1 Three ways to do input-output



| Method | How it works | CPU involvement |
|---|---|---|
| Programmed I/O | The CPU repeatedly checks (polls) the device status flag in a loop until the device is ready | Highest - CPU is fully wasted waiting |
| Interrupt-driven I/O | The device raises an interrupt when it is ready; the CPU does other work in the meantime | Medium - CPU handles each byte/word but does not wait |
| DMA (Direct Memory Access) | A separate DMA controller transfers a whole block directly between the device and memory, then interrupts the CPU once at the end | Lowest - CPU is only involved at start and finish |


- **Cycle stealing** - The DMA controller takes control of the bus for one cycle at a time between CPU accesses.
- **Burst mode / block transfer** - The DMA controller keeps the bus until the whole block is moved.
- **I/O port** - An addressable interface through which the CPU talks to a device.
- **Memory-mapped I/O** - Device registers appear as ordinary memory addresses; normal LOAD/STORE instructions work on them.
- **Isolated (I/O-mapped) I/O** - Devices live in a separate address space with special IN and OUT instructions.
- **Interrupt vector** - A table holding the addresses of interrupt service routines.
- **Maskable interrupt** - Can be disabled by software. **Non-maskable (NMI)** cannot - used for critical failures like power loss.


### B6.2 The ALU and its operations


The ALU performs:
- **Arithmetic**: add, subtract, multiply, divide, increment, decrement, compare.
- **Logical**: AND, OR, NOT, XOR, XNOR.
- **Shift and rotate**: logical shift, arithmetic shift, rotate left/right.


> **NOTE: Direct PYQ**
>
> "Which logical operation does the ALU perform that results in a 1 output only when both inputs are different?" Answer: **XOR**. AND needs both to be 1; OR needs at least one 1; NOR needs both to be 0. Only XOR is the "difference detector".



> **TIP: Shift operations = fast arithmetic**
>
> A **left shift by 1** multiplies by 2. A **right shift by 1** divides by 2 (integer division). Shifting by n multiplies or divides by 2^n. Compilers use this because shifting is far cheaper than multiplying. This idea already appeared in the "3's complement number divided by 2" question in Part A.




---

# PART C - Operating Systems and Linux

> *The single highest-scoring topic in the paper. Expect 8 to 12 questions from this Part alone.*



## C1 What an Operating System Does



### C1.1 The idea in one picture


Think of a **school principal**. Students (programs) all want the same things: the hall, the projector, the sports ground, the teacher's time. If everyone grabbed things directly there would be chaos. The principal decides who gets what, when, and for how long. He also makes sure a student never damages school property or disturbs another class.

An operating system is that principal, sitting between your programs and the hardware.

- **Operating System** - A program that acts as an **interface (bridge) between the computer user / application programs and the computer hardware**. It manages all resources and provides services so users can run programs conveniently and efficiently.


> **NOTE: Direct PYQ**
>
> "Which type of computer program acts as a bridge between a computer user and the computer hardware?" Options: Random Access Memory, User thread, **Operating system**, Kernel. Answer: **Operating system**.
>
> Careful with "Kernel". The kernel is the **core part** of the OS, always resident in memory. The full bridge between user and hardware - including the shell, system programs and the user interface - is the **operating system**. When both appear as options, choose "Operating system" for the user-hardware bridge and "Kernel" only when the question mentions the core/innermost layer.



### C1.2 The services an OS provides



| Service | What it means |
|---|---|
| Program execution | Load a program into memory and run it; handle normal and abnormal termination |
| I/O operations | Provide a uniform way to read/write files and devices |
| File system manipulation | Create, delete, read, write, search files and directories; manage permissions |
| Communication | Let processes exchange information (shared memory or message passing) - Inter Process Communication |
| Error detection and handling | Detect CPU errors, memory errors, device failures, program faults |
| Resource allocation | Share CPU time, memory, files and devices among users and processes |
| Accounting / Logging | Record which user used how much of which resource |
| Protection and security | Stop one process from interfering with another; authenticate users |
| Process management | Create, schedule, suspend, resume and terminate processes |
| Memory management | Track which parts of memory are in use and by whom |



> **NOTE: PYQ worked out - the exception question**
>
> "Which of the following services is NOT provided by the operating system?" Options: Resource management, Inter process communication, **Translate source into machine code**, Program execution. Answer: **Translate source into machine code**.
>
> Why: translating source code into machine code is the job of a **compiler / assembler**, which is a separate piece of system software. The OS *runs* the compiler, but does not itself do the translation. Everything else listed is a genuine core OS service.



### C1.3 Types of operating systems



| Type | Description | Example |
|---|---|---|
| Batch OS | Jobs with similar needs are grouped into batches and run one after another with no user interaction. No priority; long turnaround | Early IBM systems, payroll processing |
| Multiprogramming | Several programs are kept in memory; when one waits for I/O, the CPU switches to another. Goal: maximise CPU utilisation | - |
| Multitasking / Time-sharing | Multiprogramming plus rapid switching so each user feels they have the machine to themselves. Uses a time quantum | UNIX, Windows, Linux |
| Multiprocessing | Two or more CPUs share work in one computer. Increases throughput and reliability | Modern multi-core PCs |
| Real-Time OS (RTOS) | Guarantees a response within a strict deadline. HARD real-time: missing the deadline is a total failure (pacemaker, airbag). SOFT real-time: a miss degrades quality (video streaming) | VxWorks, RTLinux, QNX |
| Distributed OS | Many independent computers appear to the user as one system, connected by a network | Amoeba, LOCUS |
| Network OS | Provides file and printer sharing across a network; each machine keeps its own OS identity | Novell NetWare, Windows Server |
| Embedded OS | Small OS inside a dedicated device | Washing machine, smart TV, router |
| Mobile OS | - | Android, iOS |


- **Multiprogramming vs Multitasking** - Multiprogramming keeps the CPU busy by switching when a process **blocks**. Multitasking switches on a **time quantum** as well, giving interactive response.
- **Multiprocessing vs Multithreading** - Multiprocessing = multiple **CPUs**. Multithreading = multiple **threads inside one process** on possibly one CPU.
- **Symmetric multiprocessing (SMP)** - All processors are peers and share one copy of the OS.
- **Asymmetric multiprocessing** - One master processor controls slave processors.


### C1.4 Kernel and OS structure


- **Kernel** - The core of the OS. It is always resident in main memory and has complete control of the hardware. It handles process scheduling, memory management, device drivers, system calls and interrupts.
- **Shell** - The outer layer that takes user commands and passes them to the kernel. The command interpreter.
- **System call** - The controlled doorway a user program uses to ask the kernel for a service. It switches the CPU from **user mode** to **kernel mode**.
- **User mode vs Kernel mode** - In user mode a program cannot execute privileged instructions or touch hardware directly. In kernel mode everything is allowed. This dual-mode design is what protects the system.


| Kernel type | Idea | Trade-off |
|---|---|---|
| Monolithic kernel | The whole OS - scheduling, memory, file system, drivers - runs as one large program in kernel space | Very fast (no message passing) but huge and hard to maintain; one bug can crash everything. Example: Linux, UNIX |
| Microkernel | Only the bare minimum (scheduling, memory, IPC) is in kernel space; file systems and drivers run as user processes | Very reliable and modular but slower due to message passing. Example: MINIX, QNX, Mach |
| Hybrid kernel | A microkernel design with some services pulled back into kernel space for speed | Windows NT family, macOS (XNU) |
| Exokernel | Gives applications direct, protected access to hardware resources | Research systems |



#### Categories of system calls (learn the five groups)


| Category | Examples |
|---|---|
| Process control | fork(), exec(), exit(), wait(), abort() |
| File management | open(), close(), read(), write(), create(), delete() |
| Device management | ioctl(), read(), write(), request device, release device |
| Information maintenance | getpid(), alarm(), sleep(), time(), get/set system data |
| Communication | pipe(), socket(), send(), receive(), shmget(), mmap() |



> **NOTE: Direct PYQ**
>
> "What is typically returned by the getpid system call in Unix-based operating systems?" Answer: **Process ID of the current process**.
>
> Related: `getppid()` returns the **parent** process ID. Remember the extra "p" = parent. This is a favourite pair.



## C2 Processes and Threads



### C2.1 Program vs process


- **Program** - A **passive** entity: a file sitting on the disk containing instructions. Like a recipe printed in a book.
- **Process** - A program **in execution** - an active entity with a program counter, registers, stack and its own memory. Like actually cooking that recipe right now.

One program can produce many processes (open three Chrome windows and you have several processes from one program).


#### Process Control Block (PCB)

The OS keeps one PCB per process - its "identity card". It contains:
- Process ID (PID) and parent PID
- Process **state**
- Program counter and CPU register values
- CPU scheduling information (priority, queue pointers)
- Memory management information (base/limit registers, page tables)
- Accounting information (CPU used, time limits)
- I/O status (list of open files and allocated devices)


#### The memory layout of a process


*Four segments of a running process*
```
   +---------------------+  high address
   |       STACK         |  local variables, function call frames
   |          |          |  grows DOWNWARD
   |          v          |
   |                     |
   |          ^          |
   |          |          |  grows UPWARD
   |        HEAP         |  dynamic memory: malloc / new
   +---------------------+
   |    DATA segment     |  global and static variables
   +---------------------+
   |    TEXT / CODE      |  the compiled instructions (read-only)
   +---------------------+  low address
```



### C2.2 Process states - the diagram you must be able to draw



*The five-state process model*
```
                        admitted            dispatch
   [NEW] ------------------> [READY] -----------------> [RUNNING]
                               ^   ^                      |    |
              interrupt /      |   |                      |    | exit
              time quantum     |   +----------------------+    |
              expired          |                               v
                               |                          [TERMINATED]
                               |    I/O or event completes
                          [WAITING / BLOCKED] <---- I/O or event wait
```



| State | Meaning |
|---|---|
| New | The process is being created; not yet admitted to the ready queue |
| Ready | Loaded in memory and waiting only for the CPU |
| Running | Instructions are actually being executed on the CPU |
| Waiting / Blocked / Sleeping | Waiting for some event - I/O completion, a signal, a resource. It CANNOT use the CPU even if it is free |
| Terminated / Exit | Execution finished; the process is being removed and its resources reclaimed |
| Suspended ready / Suspended blocked | Swapped out to disk to free memory (in systems with swapping) |



#### The legal transitions (and the illegal ones)

- New to Ready (admitted)
- Ready to Running (dispatched by the scheduler)
- Running to Ready (time quantum expired - preemption)
- Running to Waiting (asks for I/O)
- Waiting to Ready (I/O finished) - note it goes to **Ready**, never straight to Running
- Running to Terminated (finished or killed)

**Illegal:** Ready to Waiting, Waiting to Running, Terminated to anything.


> **NOTE: PYQ worked out - when is memory released?**
>
> "An operating system completely releases the memory allocated to a process after the process transitions from which of the following states?" Options: Sleeping to ready, Ready to running, **Running to terminated**, Running to sleeping. Answer: **Running to terminated**.
>
> Why: memory is only fully reclaimed when the process **ends**. In every other transition the process is still alive and still needs its memory - a sleeping or ready process will resume later and must find its data intact.



> **NOTE: Direct PYQ**
>
> "If a process arrives at time 5, what is the latest possible time for it to start execution if there are no other processes in the system?" Answer: **Time 5**.
>
> Logic: with nothing else competing for the CPU, the scheduler can dispatch it the instant it arrives. It cannot start **before** arriving (so Time 0 and Time 4 are impossible), and there is no reason to delay it to Time 6. So the earliest and latest possible start are both time 5.



### C2.3 Threads


A **thread** is the smallest unit of execution - a single sequence of instructions inside a process. A process with several threads is doing several things at once while sharing one memory space.

Analogy: a process is a **kitchen**. Threads are the **cooks** in that kitchen. They share the same fridge, the same gas stove and the same ingredients (memory), but each is working on a different dish (its own stack and program counter).


| Point | Process | Thread |
|---|---|---|
| Also called | Heavyweight | Lightweight |
| Memory | Own separate address space | Shares the address space of its process |
| Creation cost | High | Low |
| Context switch cost | High | Low |
| Communication | Needs IPC (pipes, sockets, shared memory) | Simply shares variables - very easy |
| Isolation | One crashing process does not kill others | One crashing thread can bring down the whole process |
| What is private | Everything | Only program counter, registers, stack |
| What is shared | Nothing by default | Code, data, heap, open files, signals |



| Thread type | Managed by | Pros and cons |
|---|---|---|
| User-level thread | A thread library in user space; the kernel does not know they exist | Very fast to create and switch, but if ONE thread blocks, the whole process blocks. Cannot use multiple CPUs |
| Kernel-level thread | The operating system kernel | Slower to manage, but a blocking thread does not block the others, and true parallelism on multiple cores is possible |


- **Many-to-One model** - Many user threads mapped to one kernel thread.
- **One-to-One model** - Each user thread has its own kernel thread (Linux, Windows).
- **Many-to-Many model** - Many user threads multiplexed onto a smaller number of kernel threads.
- **Thread pool** - A set of pre-created threads waiting for work - avoids creation overhead.


### C2.4 Process creation: fork(), exec(), wait(), join()


- **fork()** - Creates a **new child process** that is an exact copy of the parent. It returns **0 to the child** and the **child's PID to the parent** (and -1 on failure). This is how one process becomes two.
- **exec() family** - **Replaces** the current process image with a new program. Used right after fork() so the child runs something different.
- **wait()** - Makes the parent **pause until a child finishes**. Prevents zombie processes.
- **join()** - In thread programming (pthread_join, Java Thread.join), makes the calling thread wait until the target thread completes.
- **exit()** - Terminates the calling process and returns a status.
- **Zombie process** - A child that has finished but whose parent has not yet called wait() to collect its exit status. Its PCB lingers.
- **Orphan process** - A process whose parent has died. It is adopted by init / systemd (PID 1).


> **NOTE: PYQ worked out**
>
> "______ and ______ are used in conjunction for making a complete process subroutine." Answer: **fork(), join()**.
>
> The reasoning: fork() **splits** execution into two paths, and join() **merges** them back by waiting for completion. Creating without waiting leaves zombies; waiting without creating is meaningless. The distractors all involve sleep(), which merely pauses for a fixed time and has nothing to do with process creation. Also note the order matters - you must fork before you can join, so "join(), fork()" is wrong.



*How fork() is actually used*
```
pid_t pid = fork();

if (pid < 0) {
    /* fork failed */
} else if (pid == 0) {
    /* THIS IS THE CHILD - pid is 0 here */
    execlp("/bin/ls", "ls", NULL);
} else {
    /* THIS IS THE PARENT - pid holds the child's PID */
    wait(NULL);          /* wait for the child to finish */
}
```



> **TIP: Counting processes after multiple forks**
>
> n consecutive fork() calls create **2^n** total processes (including the original). So 3 forks give 8 processes, meaning 7 **new children**. This is a common numerical.



### C2.5 Inter Process Communication (IPC)


Two processes have separate memory, so they need a special channel to talk.


| Mechanism | Description |
|---|---|
| Pipe | A one-way (half-duplex) channel between related processes (parent-child). Unnamed |
| Named pipe / FIFO | A pipe with a name in the file system, so unrelated processes can use it |
| Message queue | A linked list of messages held by the kernel; processes send and receive by queue ID |
| Shared memory | A region of memory mapped into both processes. FASTEST method because no kernel copying is needed after setup |
| Semaphore | Used for synchronisation and signalling, not bulk data |
| Socket | A communication ENDPOINT. Works between processes on the SAME machine or across a network |
| Signal | A short asynchronous notification, e.g. SIGKILL, SIGINT, SIGSEGV |



> **NOTE: PYQ worked out**
>
> "What is an endpoint of an inter-process communication?" Options: Tunnel, Port, **Socket**, Pipe. Answer: **Socket**.
>
> Definition to memorise: a **socket is one endpoint of a two-way communication link between two programs running on a network**. A socket is identified by the combination of **IP address + port number + protocol**.
>
> Why not "Port"? A port is just a 16-bit number identifying a service - it is one *component* of a socket address, not the endpoint itself. Why not "Pipe"? A pipe is a channel, not an endpoint, and it is not network-capable.



### C2.6 Synchronisation and the critical section problem


When two processes touch the same shared data at the same time, the final answer depends on the exact timing. This bug is called a **race condition**.

- **Critical section** - The part of a program that accesses shared resources and must not be executed by more than one process at a time.
- **Mutual exclusion** - Only one process inside the critical section at a time.
- **Progress** - If no process is in the critical section, a waiting process must be allowed in.
- **Bounded waiting** - There is a limit on how long a process must wait for its turn - no starvation.


| Tool | Description |
|---|---|
| Mutex lock | A binary lock. acquire() before the critical section, release() after. Only the owner can unlock |
| Binary semaphore | Value is 0 or 1. Similar to a mutex |
| Counting semaphore | Value can be any non-negative integer; allows up to N processes in. Operations are wait()/P()/down() which decrements, and signal()/V()/up() which increments |
| Monitor | A high-level construct where only one procedure may be active at a time; uses condition variables |
| Peterson's solution | A pure software solution for two processes using flag[] and turn variables |
| Test-and-Set / Compare-and-Swap | Hardware atomic instructions used to build locks |


- **Busy waiting / Spinlock** - A process loops continuously checking the lock. Wastes CPU but avoids context-switch cost for very short waits.
- **Classic problems** - Producer-Consumer (bounded buffer), Reader-Writer, Dining Philosophers, Sleeping Barber.


### C2.7 Deadlock


**Deadlock** is when a set of processes are each holding a resource and each waiting for a resource held by another - so none of them can ever proceed.

Everyday picture: four cars reach a narrow crossroads at the same time, each blocking the one to its right. Nobody can move.


#### The four necessary conditions (all four must hold at once)

1. **Mutual exclusion** - at least one resource is non-shareable.
2. **Hold and wait** - a process holds a resource while requesting another.
3. **No preemption** - a resource cannot be forcibly taken away; it must be released voluntarily.
4. **Circular wait** - a closed chain of processes each waiting for the next.


#### The four ways to deal with deadlock


| Strategy | Idea |
|---|---|
| Prevention | Design the system so that at least ONE of the four conditions can never hold (e.g. request all resources at once; impose a global ordering on resources) |
| Avoidance | Allow the conditions but check every request before granting it, keeping the system in a SAFE state. The classic algorithm is the BANKER'S ALGORITHM |
| Detection and recovery | Let deadlock happen, detect it with a wait-for graph, then recover by killing a process or rolling back (preempting resources) |
| Ignore it | Assume deadlock is rare and just reboot. This is what UNIX and Windows actually do (the "ostrich algorithm") |


- **Safe state** - A state in which there exists at least one sequence in which all processes can finish.
- **Banker's algorithm** - Deadlock **avoidance** algorithm by Dijkstra. Uses Available, Max, Allocation and Need matrices to test whether granting a request keeps the system safe.
- **Starvation** - A process waits indefinitely because others keep getting preference. Different from deadlock - here the system is progressing, just not for this process.
- **Aging** - A cure for starvation - gradually increase the priority of a long-waiting process.


## C3 CPU Scheduling



### C3.1 The timing terms - learn these exactly


These four definitions are asked directly, and one paper used them as a trick question.


| Term | Exact definition |
|---|---|
| Arrival Time (AT) | The time at which a process ARRIVES in the ready queue |
| Burst Time (BT) | The total time a process REQUIRES ON THE CPU to complete its execution. It is NOT the time to start execution |
| Completion Time (CT) | The time at which the process finishes execution |
| Turn Around Time (TAT) | CT - AT. The total time from arrival to completion (waiting + executing) |
| Waiting Time (WT) | TAT - BT. Time spent sitting in the ready queue doing nothing |
| Response Time (RT) | Time from arrival until the process gets the CPU for the FIRST time |
| Throughput | Number of processes completed per unit time |



> **NOTE: PYQ worked out - the FALSE statement**
>
> "Which of the following statements is FALSE?"
> (a) **Burst Time: Time required by a process to START its execution** - FALSE. Burst time is the time required **to execute on the CPU**, not to start.
> (b) Turn Around Time: difference between completion time and arrival time - TRUE.
> (c) Completion Time: time at which a process completes its execution - TRUE.
> (d) Arrival Time: time at which a process arrives in the ready queue - TRUE.
>
> Answer: option (a). Examiners love changing "to execute" into "to start its execution".



> **TIP: The two formulas that solve every scheduling numerical**
>
> **TAT = CT - AT** and **WT = TAT - BT**. Build a table with columns AT, BT, CT, TAT, WT and fill it row by row. Then average the last two columns.



### C3.2 The scheduling algorithms


- **Preemptive scheduling** - The OS can forcibly take the CPU away from a running process.
- **Non-preemptive scheduling** - Once a process gets the CPU it keeps it until it finishes or blocks voluntarily.


| Algorithm | How it picks | Preemptive? | Notes |
|---|---|---|---|
| FCFS (First Come First Served) | Whoever arrived first | No | Simplest. Implemented with a FIFO queue. Suffers the CONVOY EFFECT: one long process makes everyone wait. Poor average waiting time |
| SJF (Shortest Job First) | Smallest burst time | No | Gives the MINIMUM average waiting time of all non-preemptive algorithms, but needs to know burst times in advance and can starve long jobs |
| SRTF (Shortest Remaining Time First) | Smallest remaining burst | Yes | The preemptive version of SJF. Optimal average waiting time overall |
| Priority scheduling | Highest priority number/level | Either | Risk of STARVATION of low-priority processes; cured by AGING |
| Round Robin (RR) | Each process gets one fixed TIME QUANTUM in circular order | Yes | Best for time-sharing and fairness. Small quantum = more context-switch overhead; very large quantum = behaves like FCFS |
| Multilevel Queue | Several queues with different priorities; a process stays in its queue | Yes | Separates interactive and batch jobs |
| Multilevel Feedback Queue | Like above, but processes can MOVE between queues based on behaviour | Yes | Most flexible and general; used in real systems |
| HRRN (Highest Response Ratio Next) | Ratio = (waiting time + burst) / burst | No | Balances SJF's efficiency with fairness |



*Worked example - FCFS*
```
Process   AT   BT
  P1       0    5
  P2       1    3
  P3       2    8

Gantt chart:  | P1 | P2 | P3          |
              0    5    8            16

P1: CT=5 , TAT=5-0=5 , WT=5-5=0
P2: CT=8 , TAT=8-1=7 , WT=7-3=4
P3: CT=16, TAT=16-2=14, WT=14-8=6

Average TAT = (5+7+14)/3 = 8.67
Average WT  = (0+4+6)/3  = 3.33
```



### C3.3 The three schedulers and the dispatcher


- **Long-term scheduler (Job scheduler)** - Decides which jobs are admitted from disk into the ready queue. Controls the **degree of multiprogramming**. Runs rarely.
- **Short-term scheduler (CPU scheduler)** - Decides which ready process gets the CPU next. Runs very frequently (milliseconds).
- **Medium-term scheduler** - Swaps processes out of memory to disk and back in, to reduce the degree of multiprogramming temporarily.
- **Dispatcher** - The module that actually gives control of the CPU to the chosen process - it performs the context switch, switches to user mode and jumps to the right instruction. The time it takes is **dispatch latency**.
- **Context switch** - Saving the state of the current process in its PCB and loading the state of the next. It is **pure overhead** - no useful work happens during a context switch.


## C4 Memory Management



### C4.1 Why memory must be managed


Many programs sit in RAM at once. The OS must decide where each one goes, stop them from reading each other's data, and reclaim space when they finish.

- **Logical / Virtual address** - The address generated by the CPU as the program sees it.
- **Physical address** - The actual address on the RAM chip.
- **MMU (Memory Management Unit)** - The hardware that translates logical addresses to physical addresses at run time.
- **Base (relocation) register** - Holds the smallest legal physical address; added to every logical address.
- **Limit register** - Holds the size of the range; used to check the address is legal. Together they give **memory protection**.


### C4.2 Contiguous allocation and the fitting algorithms


In contiguous allocation each process gets one single unbroken block of memory. The OS keeps a list of free blocks ("holes") and must choose one.


| Algorithm | Rule | Behaviour |
|---|---|---|
| First Fit | Scan from the start; take the FIRST hole big enough | Fastest search. Good general performance |
| Best Fit | Search the WHOLE list; take the SMALLEST hole that fits | Wastes the least space in that one allocation, but must scan every hole (slow), and the tiny leftovers it creates are useless - so external fragmentation gets worse over time |
| Worst Fit | Take the LARGEST hole | Leaves large usable leftovers in theory, but performs worst in practice and also needs a full scan |
| Next Fit | Like First Fit but resumes scanning from where it stopped last time | Spreads allocations out |



> **NOTE: PYQ worked out - the Best Fit trap**
>
> "How does the Best Fit algorithm impact system performance?" Answer: **It may reduce system performance due to increased search time for free blocks.**
>
> Read the options carefully - three of them praise Best Fit:
> "It improves system performance by reducing memory wastage" - tempting, and partly true for a single allocation, but the question asks about **system performance**, not space.
> "It always improves system performance" - the word "always" makes it wrong.
> "It improves system performance by reducing external fragmentation" - actually FALSE; Best Fit **increases** external fragmentation because it leaves many unusably small holes.
>
> So the correct answer is the one about **search time**: Best Fit must examine the entire free list on every single request.



#### Fragmentation

- **Internal fragmentation** - Wasted space **inside** an allocated block, because the block given is slightly bigger than what was asked. Typical of fixed-size partitions and paging.
- **External fragmentation** - Total free memory is enough, but it is scattered in small pieces so no single piece is large enough. Typical of variable-size partitions and segmentation.
- **Compaction** - Shuffling allocated blocks together to merge all free space into one big hole. Cures external fragmentation but is expensive and needs dynamic relocation.
- **Coalescing** - Merging adjacent free holes into one larger hole.


### C4.3 Paging


Paging removes external fragmentation completely by dropping the requirement that a process be contiguous in physical memory.

- The **logical address space** is divided into fixed-size **pages**.
- **Physical memory** is divided into blocks of the same size called **frames**.
- Any page can go into any free frame. A **page table** records which frame holds which page.


*Address translation in paging*
```
Logical address = | page number (p) | offset (d) |
                            |
                            v
                     +-------------+
                     | PAGE TABLE  |  ->  frame number (f)
                     +-------------+
                            |
                            v
Physical address = | frame number (f) | offset (d) |     (offset is unchanged)
```


- **Page size** - Always a power of two, typically 4 KB.
- **Page table** - One per process; maps page number to frame number. Stored in main memory, pointed to by the Page Table Base Register.
- **TLB (Translation Lookaside Buffer)** - A small, very fast associative cache of recent page-table entries. A **TLB hit** avoids a memory access for the page table. Without it, every memory reference would need two memory accesses.
- **Valid-invalid bit** - Marks whether a page is currently in memory.
- **Paging removes** - External fragmentation. It still has a little **internal** fragmentation in the last page of each process.


### C4.4 Segmentation


Segmentation divides a program the way a **programmer** thinks of it: a code segment, a data segment, a stack segment, one segment per function or array. Segments have **variable length**.


| Point | Paging | Segmentation |
|---|---|---|
| Block size | Fixed | Variable |
| Divided by | The operating system | The programmer / compiler (logical division) |
| Fragmentation | Internal | External |
| Address | One number split into page + offset | Two parts: segment number and offset |
| Visible to programmer | No | Yes |
| Table | Page table (frame number) | Segment table (base + limit) |


**Segmented paging** combines both: segments are divided into pages. This gives the logical view of segmentation without external fragmentation.


### C4.5 Virtual memory and demand paging


- **Virtual memory** - A technique that lets a program larger than physical RAM run, by keeping only the parts currently needed in RAM and the rest on **secondary storage** (the disk). Its main purpose is **to extend the physical memory using secondary storage**.
- **Demand paging** - Pages are brought into memory only when they are actually referenced - never in advance.
- **Swap space** - The area of disk reserved for holding pages that are not in RAM. Called a **page file** in Windows and a **swap partition** in Linux.
- **Page fault** - The event that occurs when a program **accesses a page that is not currently present in main memory**. The MMU raises a trap; the OS finds the page on disk, loads it into a free frame, updates the page table and restarts the instruction.
- **Thrashing** - The system spends more time swapping pages in and out than doing useful work. Caused by too high a degree of multiprogramming. Cured by reducing multiprogramming or by the **working-set model**.
- **Working set** - The set of pages a process is actively using in a recent time window.


> **NOTE: Two direct PYQs**
>
> "What is the main purpose of virtual memory?" Answer: **To extend the physical memory using secondary storage.** Not to increase CPU speed, not to provide cache, not to store BIOS settings.
>
> "Page fault means:" Answer: **accessing the page that is not currently in the memory.** Note the distractors: "removing the page whenever it is needed" and "fetching the page whenever it is needed" describe *actions*, not the fault itself; "an error that always occurs in the page" is nonsense - a page fault is a normal, expected event, not a program error.



### C4.6 Page replacement algorithms


When a page fault occurs and there is no free frame, the OS must choose a **victim** page to evict.


| Algorithm | Rule | Notes |
|---|---|---|
| FIFO | Evict the page that has been in memory longest | Simple. Suffers BELADY'S ANOMALY - giving it MORE frames can cause MORE page faults |
| Optimal (OPT / MIN) | Evict the page that will not be used for the longest time in the future | Lowest possible fault rate, but impossible to implement. Used only as a benchmark |
| LRU (Least Recently Used) | Evict the page unused for the longest time | Good approximation of Optimal; needs counters or a stack. Does NOT suffer Belady's anomaly |
| LFU (Least Frequently Used) | Evict the page with the smallest reference count | Can keep a page that was heavily used long ago |
| MFU | Evict the most frequently used | Rarely useful |
| Second Chance / Clock | FIFO plus a reference bit; a page with the bit set gets one more chance | Cheap and effective; widely used in practice |


- **Belady's anomaly** - The counter-intuitive result that increasing the number of frames can increase the number of page faults. It happens in **FIFO** (and in Second-Chance), but NOT in LRU or Optimal, which are "stack algorithms".


## C5 File Systems and Disk Management



### C5.1 Files and attributes


- **File** - A named collection of related information stored on secondary storage. It is the logical unit the user sees.
- **File attributes** - Name, identifier (inode number), type, location, size, protection bits, timestamps (created/modified/accessed), owner.
- **Metadata** - Data about the data - the attributes, not the content.


#### File access methods


| Method | Description |
|---|---|
| Sequential access | Read/write in order from start to end. Simplest. Magnetic tape supports only this |
| Direct / Random access | Jump straight to any record number. Disks support this |
| Indexed sequential access | An index block holds pointers, allowing quick lookup then sequential reading |



### C5.2 Directory structures



| Single-level | One directory for all files, all users | Name collisions; no grouping |
|---|---|---|
| Two-level | One separate directory per user | Users cannot share conveniently; no sub-grouping |
| Tree-structured | Directories can contain subdirectories - the familiar folder tree | A file has exactly ONE path; sharing is awkward |
| Acyclic graph | Allows LINKS so the same file/directory can appear in several places, but no cycles are allowed | Needs care when deleting (reference counting) |
| General graph | Cycles allowed | Needs garbage collection to reclaim space; traversal can loop forever |



> **NOTE: PYQ worked out**
>
> "In an acyclic graph directory structure, what is a common method used to implement shared directories or files?" Options: File duplication, **Symbolic (soft) links**, Hard links, Directory pointers. Answer: **Symbolic (soft) links**.
>
> Why not hard links? A **hard link** is a second directory entry pointing to the very same inode. Hard links to *directories* are forbidden on UNIX precisely because they could create cycles - which would break the "acyclic" property. A **symbolic link** is a small file containing a path name; it can safely point to a directory and is the standard way to share directories in an acyclic-graph structure.
>
> Learn the pair:
> **Hard link** - same inode number, cannot cross file systems, cannot link directories, file survives if the original name is deleted.
> **Soft/symbolic link** - own inode, stores a path, can cross file systems, can link directories, becomes a "dangling link" if the target is deleted.



### C5.3 File allocation methods



| Method | How blocks are assigned | Pros | Cons |
|---|---|---|---|
| Contiguous | All blocks of a file lie next to each other | Excellent sequential AND direct access | External fragmentation; the file cannot grow easily |
| Linked | Each block stores a pointer to the next | No external fragmentation; file can grow | Direct access is slow (must follow the chain); a lost pointer destroys the rest; pointer wastes space |
| Indexed | One index block holds all the block addresses of the file | Supports direct access; no external fragmentation | The index block itself is overhead; a large file may need multi-level indexing |
| FAT (File Allocation Table) | A table in a reserved area holds the whole chain of links | Simple, direct access via the table | The table must be cached or every access needs two reads |
| Inode (UNIX) | A structure with direct pointers plus single, double and triple indirect pointers | Small files are very efficient, huge files still possible | Multiple reads for very large files |


- **Free space management** - Bit vector / bitmap (one bit per block - simple and fast to find contiguous runs), linked list of free blocks, grouping, counting.


### C5.4 Popular file systems



| File system | Used by | Key points |
|---|---|---|
| FAT16 / FAT32 | Old Windows, USB drives | FAT32 max file size 4 GB. Very compatible |
| NTFS | Modern Windows | Journaling, file-level security/ACLs, encryption (EFS), disk quotas, SUPPORTS COMPRESSION of files and folders, small cluster sizes for efficiency, very large volumes |
| exFAT | Flash drives | No 4 GB limit, cross-platform |
| ext2 | Old Linux | No journaling |
| ext3 | Linux | Adds journaling |
| ext4 | DEFAULT Linux file system | Journaling, extents, larger files and volumes, delayed allocation |
| XFS / Btrfs / ZFS | Linux / Unix | High-performance and advanced features (snapshots, checksums) |
| HFS+ / APFS | macOS | - |



> **NOTE: Two direct PYQs on file systems**
>
> "The default file system type in Linux is:" Answer: **Ext4** (not Ext2, Ext3 or Ext1).
>
> "Which of the following is NOT true about NTFS?" Answer: **"It does not support the compression of files and directories to optimise storage space."** This is false - NTFS **does** support built-in compression. The other three statements (efficient use of disk space via smaller clusters; attributes such as read-only, hidden, system, archive, not-content-indexed, off-line, temporary and compressed; improved performance and scalability over its precursor FAT) are all TRUE of NTFS.


- **Journaling** - The file system first writes an intention record to a log (journal), then performs the change. After a crash the journal is replayed, so the file system is never left inconsistent.


### C5.5 Disk scheduling algorithms


The disk arm is slow to move, so the order in which requests are served matters a lot. The goal is to minimise total **seek time**.


| Algorithm | How the head moves |
|---|---|
| FCFS | Serves requests in the order they arrive. Fair but the head may jump wildly back and forth |
| SSTF (Shortest Seek Time First) | Always serves the request CLOSEST to the current head position. Reduces average response time, but can STARVE far-away requests and needs the seek time computed in advance |
| SCAN (Elevator) | The head sweeps in ONE direction serving every request until it reaches the END of the disk, then REVERSES and sweeps back. Like a lift going to the top floor before coming down |
| C-SCAN (Circular SCAN) | Sweeps one way to the end, then JUMPS back to the beginning without serving anything on the return, and sweeps again. More uniform waiting time |
| LOOK | Like SCAN but reverses at the LAST REQUEST, not at the physical end of the disk |
| C-LOOK | Like C-SCAN but jumps back from the last request instead of the disk end |



> **NOTE: PYQ worked out - identify the algorithm**
>
> "In which scheduling algorithm does the disk head move in one direction, satisfying all requests until it reaches the END, and then reverses direction?" Answer: **SCAN**.
>
> The phrase "**until it reaches the end**" is decisive. If the question had said "until the last request", the answer would be **LOOK**. If it said "then jumps back to the start without serving", the answer would be **C-SCAN**. Memorise these three trigger phrases.



> **NOTE: PYQ worked out - advantage of SSTF**
>
> "The advantage of SSTF (Shortest Seek Time First) is:" Answer: **average response time decreases**.
>
> The other options are all **disadvantages**, cleverly listed as if they were advantages: "high variance of response time as SSTF favours only some requests" is a drawback; "overhead to calculate seek time in advance" is a drawback; "throughput decreases" is wrong because SSTF actually **increases** throughput.



## C6 Linux and UNIX Essentials



### C6.1 The Linux directory tree


Linux has one single tree starting at **/** (root). Learn what lives where - this is asked directly.


| Directory | What it holds |
|---|---|
| / | The root of everything |
| /bin | Essential user command BINARIES (executable files for UNIX commands) - ls, cp, mv, cat |
| /sbin | System binaries for the administrator - fdisk, shutdown, ifconfig |
| /etc | CONFIGURATION FILES and additional commands related to system maintenance and administration - passwd, hosts, fstab |
| /dev | DEVICE FILES / device drivers that control peripherals connected to the system |
| /home | Users' personal home directories - /home/ravi |
| /root | The home directory of the root (superuser) account. NOT the same as / |
| /usr | User programs and read-only shareable data: /usr/bin, /usr/lib, /usr/share. It is NOT for temporary files |
| /var | VARIABLE data that keeps changing - logs (/var/log), mail spools, print queues |
| /tmp | TEMPORARY files, usually cleared on reboot |
| /lib | Shared libraries needed by /bin and /sbin |
| /boot | Kernel image and boot loader files |
| /mnt , /media | Mount points for temporary and removable file systems |
| /proc | A virtual file system exposing kernel and process information as files |
| /opt | Optional third-party software |



> **NOTE: PYQ worked out - two questions on directories**
>
> "In which of the following directories are the configuration files found?" Options: /dev, /root, **/etc/**, /bin. Answer: **/etc/**.
>
> "Which of the following statements is NOT true?" The false statement was **"usr: It contains temporary files created by Linux or other users."** That describes **/tmp**, not /usr. The true statements were: etc contains additional commands related to system maintenance and administration; bin contains executable files for UNIX commands; dev contains device drivers that control peripherals.



### C6.2 The commands you must know



| Command | Purpose |
|---|---|
| ls | List directory contents. `ls -l` long format, `ls -a` show hidden files |
| cd | Change directory |
| pwd | Print working directory |
| mkdir | Make a directory |
| rmdir | Remove an EMPTY directory only |
| rm | REMOVE / DELETE files. `rm -r` deletes a directory and everything inside it recursively; `rm -f` forces |
| cp | Copy files or directories |
| mv | Move or rename |
| cat | Display, create or concatenate files |
| more / less | View a file one screen at a time |
| head / tail | Show the first / last few lines. `tail -f` follows a growing log |
| touch | Create an empty file or update its timestamp |
| grep | SEARCH FOR A SPECIFIC PATTERN in a file and display the lines containing that pattern. `grep -i` ignores case, `grep -v` inverts, `grep -r` recurses |
| find | Search for files by name, size, time, permission |
| wc | Word, line and character count |
| sort / uniq | Sort lines; remove duplicates |
| cut | Cut out selected COLUMNS or fields of a file |
| tr | Translate or change the case of characters |
| sed | Stream editor - find and replace |
| awk | Pattern scanning and field processing |
| chmod | Change file permissions |
| chown / chgrp | Change owner / group |
| ps | Report current processes. `ps -ef` shows all |
| top / htop | Live view of processes and resource use |
| kill / killall | Send a signal to a process. `kill -9` forces termination |
| df / du | Disk free space / disk usage of files |
| tar | Archive files. `tar -cvf` create, `tar -xvf` extract |
| gzip / gunzip | Compress / decompress |
| man | Manual page for a command |
| who / whoami | Logged-in users / your own username |
| echo | Print text |
| pipe symbol | Send the output of one command as input to the next |
| redirection | `>` overwrite to file, `>>` append to file, `<` take input from file |



> **NOTE: Three direct PYQs on commands**
>
> "Identify the command that is used to delete files in Linux." Answer: **rm**. ("Delete" and "Erase" are not Linux commands at all; "Rmdir" removes only empty directories.)
>
> "Which command is used to remove a directory in Linux?" The answer key gave **Rm** - because `rm -r` is the general command that removes directories along with their contents. (`rmdir` works only on empty directories, and it was not offered as an option.)
>
> "Grep command is used to:" Answer: **search for a specific pattern from a specified file and display those lines containing the pattern.** The distractors describe `tr` (change case), `cut` (cut columns/fields) and the pipe (redirect output of one command to another).



> **TIP: GREP full form**
>
> GREP = **G**lobally search for a **R**egular **E**xpression and **P**rint. Knowing the full form makes the definition unforgettable.



### C6.3 File permissions


Every Linux file has permissions for three classes of people, in this fixed order:
**u = user (owner), g = group, o = others.**

Each class has three permissions:
**r = read (4), w = write (2), x = execute (1).**


*Reading a permission string*
```
   -  rw-  r--  r--
   |   |    |    |
   |   |    |    +--- others  : r-- = read only          = 4
   |   |    +-------- group   : r-- = read only          = 4
   |   +------------- user    : rw- = read and write     = 6
   +----------------- file type ( - = regular file, d = directory,
                                  l = symbolic link )

   So this file is 644.
```



| Octal | Permission | Meaning |
|---|---|---|
| 7 | rwx | read + write + execute |
| 6 | rw- | read + write |
| 5 | r-x | read + execute |
| 4 | r-- | read only |
| 0 | --- | nothing |


- **umask** - The mask that decides default permissions. Default base is 666 for files and 777 for directories; the umask is subtracted. With the usual umask of 022, a new **file** becomes 666 - 022 = **644** (rw- r-- r--) and a new **directory** becomes 777 - 022 = 755 (rwx r-x r-x).
- **Why files never get x by default** - For security - a newly created data file should not be executable.


> **NOTE: PYQ worked out**
>
> "Which of the following is a default permission for the text file in Linux?" Answer: **rw- r-- r--** (that is 644).
>
> Reasoning: files start from base 666 and the standard umask 022 removes write permission from group and others, giving rw-r--r--. The option "rwx r-- r--" is wrong because a plain text file is never executable by default, and "rwx rwx rwx" (777) would be a severe security hole.
>
> Useful chmod forms: `chmod 644 file.txt` (numeric) or `chmod u=rw,go=r file.txt` (symbolic) or `chmod +x script.sh` (add execute for everyone).



### C6.4 Shells


A **shell** is the command interpreter - the program that reads what you type and asks the kernel to do it.


| Shell | Notes |
|---|---|
| sh - Bourne shell | The original UNIX shell by Stephen Bourne |
| bash - Bourne Again SHell | The default on most Linux distributions |
| csh - C shell | Syntax resembling C, by Bill Joy |
| tcsh | Enhanced C shell |
| ksh - Korn shell | By David Korn; combines Bourne and C shell features |
| zsh - Z shell | Feature-rich; default on modern macOS |
| fish | Friendly interactive shell |



> **NOTE: Direct PYQ**
>
> "Which of the following is NOT a shell in Linux?" Options: C shell, Korn shell, Bourne shell, **Alpha cell**. Answer: **Alpha cell**. There is no such shell - the name is invented, and note the deliberate spelling "cell" instead of "shell".



### C6.5 Distributed systems (asked as a benefit/drawback question)


A **distributed system** is a collection of independent computers that appears to its users as a single coherent system.


| Benefits | Drawbacks |
|---|---|
| Resource sharing (files, printers, computation) | Complexity of design and debugging |
| Scalability - add more machines to grow | HIGH COMMUNICATION LATENCY over the network |
| Fault tolerance / reliability - one node failing does not stop the system | Security is harder (data travels over the network) |
| Speed-up through parallelism | Partial failure is difficult to detect and handle |
| Geographic distribution | Lack of a single global clock |



> **NOTE: Direct PYQ**
>
> "Which of the following is NOT a benefit of distributed systems?" Options: Scalability, **High communication latency**, Resource sharing, Fault tolerance. Answer: **High communication latency** - that is a well-known *disadvantage*, because messages must travel over a network instead of within one machine.




---

# PART D - Programming: C, C++, OOP, Java and .NET

> *"What will be the output" questions alone carry 8 to 15 marks. This Part teaches you to trace code like a machine.*



## D1 C Language Foundations



### D1.1 The skeleton of every C program



*The minimum C program*
```
#include <stdio.h>        /* preprocessor directive - brings in library */

int main()                /* execution ALWAYS starts at main() */
{
    printf("Hello");      /* a statement, ends with a semicolon */
    return 0;             /* 0 tells the OS "finished successfully" */
}
```


- **Header file** - A file containing declarations of library functions, brought in with #include.
- **Preprocessor** - Runs BEFORE the compiler. Handles #include, #define, #ifdef. It does pure text substitution.
- **main()** - The entry point. Every C program must have exactly one.
- **Token** - The smallest unit of a program: keyword, identifier, constant, string literal, operator, punctuator.


#### The header files you must memorise


| Header | What it provides |
|---|---|
| stdio.h | Standard Input Output: printf, scanf, sprintf, fopen, fclose, getchar, putchar, gets, puts |
| stdlib.h | malloc, calloc, realloc, free, exit, atoi, rand, abs |
| string.h | strlen, strcpy, strcat, strcmp, strrev, strstr |
| math.h | sqrt, pow, sin, cos, abs, floor, ceil |
| ctype.h | isalpha, isdigit, isupper, tolower, toupper |
| conio.h | clrscr, getch (Turbo C / DOS only, not standard) |
| stdarg.h | va_list, va_start, va_arg - VARIABLE argument lists |
| time.h | time, clock, difftime |
| unistd.h | UNIX system calls: fork, exec, pipe, sleep, getpid |



> **NOTE: Two PYQs on header files**
>
> "scanf() is a predefined function in which of the following header files?" Answer: **stdio.h**. Both printf and scanf live in stdio.h.
>
> "In C, variable list arguments are denoted by the standard header:" The official answer key gave **stdio.h**. Technically the correct header for variable-argument *handling* (va_list, va_start, va_arg) is **stdarg.h**, and that was offered as an option. Be aware of this: the strictly correct computer-science answer is stdarg.h, but this paper's key said stdio.h - probably reasoning that printf itself (a variadic function) is declared in stdio.h. If a similar question appears, prefer **stdarg.h** when the question mentions va_list / variable argument *macros*, and stdio.h only when it mentions printf-style functions.



### D1.2 Data types and their sizes



| Type | Typical size (32/64-bit) | Range | Format specifier |
|---|---|---|---|
| char | 1 byte | -128 to 127 | %c |
| unsigned char | 1 byte | 0 to 255 | %c |
| short int | 2 bytes | -32,768 to 32,767 | %hd |
| int | 4 bytes | -2,147,483,648 to 2,147,483,647 | %d |
| unsigned int | 4 bytes | 0 to 4,294,967,295 | %u |
| long int | 4 or 8 bytes | - | %ld |
| long long int | 8 bytes | - | %lld |
| float | 4 bytes | 6 decimal digits precision | %f |
| double | 8 bytes | 15 decimal digits precision | %lf |
| long double | 10 / 12 / 16 bytes | - | %Lf |
| void | 0 | No value - used for "returns nothing" and generic pointers | - |
| pointer | 4 or 8 bytes | - | %p |


- **Primary / primitive types** - int, char, float, double, void.
- **Derived types** - array, pointer, function.
- **User-defined types** - structure (struct), union, enumeration (enum), typedef.
- **sizeof** - A compile-time **operator** (not a function) that returns the size in bytes.


### D1.3 Operators and - most importantly - precedence



| Category | Operators |  |  |
|---|---|---|---|
| Arithmetic | + - * / % |  |  |
| Relational | == != > < >= <= |  |  |
| Logical | && (AND) , |  | (OR) , ! (NOT) |
| Bitwise | & (AND) , | (OR) , ^ (XOR) , ~ (NOT) , << (left shift) , >> (right shift) |  |
| Assignment | = += -= *= /= %= |  |  |
| Increment / Decrement | ++ -- |  |  |
| Conditional / Ternary | ? : |  |  |
| Special | sizeof , & (address of) , * (dereference) , . (dot) , -> (arrow) , [] , (comma) |  |  |



#### Precedence table (highest at the top)


| Level | Operators | Associativity |  |  |
|---|---|---|---|---|
| 1 | () [] . -> | Left to right |  |  |
| 2 | ! ~ ++ -- + - (unary) * & sizeof (type) | RIGHT to left |  |  |
| 3 | * / % | Left to right |  |  |
| 4 | + - | Left to right |  |  |
| 5 | << >> | Left to right |  |  |
| 6 | < <= > >= | Left to right |  |  |
| 7 | == != | Left to right |  |  |
| 8 | & | Left to right |  |  |
| 9 | ^ | Left to right |  |  |
| 10 |  |  |  | Left to right |
| 11 | && | Left to right |  |  |
| 12 | two-pipe OR | Left to right |  |  |
| 13 | ?: | RIGHT to left |  |  |
| 14 | = += -= etc. | RIGHT to left |  |  |
| 15 | , (comma) | Left to right |  |  |



> **NOTE: PYQ worked out**
>
> "Which arithmetic operator has the highest precedence in C?" Options: -, =, +, **%**. Answer: **%**.
>
> Reasoning: among *arithmetic* operators, the group `* / %` sits at a higher precedence level than `+ -`. Since only `%`, `+` and `-` are offered (and `=` is an assignment operator with the *lowest* precedence of all), the answer is `%`. Note that `*`, `/` and `%` are all at the **same** level - if the question had offered `*`, it would be equally correct.



> **TIP: The two facts that solve most precedence traps**
>
> Only three groups associate **right to left**: unary operators, the ternary `?:`, and assignment. Everything else is left to right. Also remember `&&` binds tighter than `||`, and both are looser than every relational operator.



### D1.4 Control flow



#### if / else, switch


*switch statement rules*
```
switch (expression) {          /* expression must be int or char - NOT float */
    case 1:
        /* statements */
        break;                 /* without break, control FALLS THROUGH */
    case 2:
        break;
    default:                   /* optional, and may appear anywhere */
        break;
}
```


Rules you must know:
- The switch expression must evaluate to an **integer or character** type. A **float is not allowed**, and neither is a string.
- Case labels must be **constant expressions**, all distinct.
- If `break` is omitted, execution **falls through** into the next case.
- `default` is optional; if no case matches and there is no default, nothing happens.
- **Switch statements can be nested** - a switch may appear inside any case of another switch. Inner and outer switches are completely independent, and an inner `break` exits only the inner switch.


> **NOTE: PYQ worked out**
>
> "Which of the following is true about nested switch statements in C?" Answer: **A switch statement can contain another switch statement inside any of its cases.**
>
> Why the others fail: "Both inner and outer switch must have a default case" - default is always optional. "A switch cannot contain another switch" - false, nesting is allowed. "Inner switch cases should not contain break statement" - they may and normally should.



#### Loops


| Loop | Structure | When the test happens | Minimum executions |
|---|---|---|---|
| for | for (init; condition; update) | Before each iteration | 0 |
| while | while (condition) | Before each iteration | 0 |
| do-while | do { } while (condition); | AFTER each iteration | 1 - the body ALWAYS runs at least once |


- **break** - Immediately **terminates** the innermost loop or switch and jumps past it.
- **continue** - Skips the rest of the current iteration and jumps to the next iteration's test/update.
- **goto** - Jumps to a label. Legal but strongly discouraged.
- **Infinite loop** - `while(1){}` , `for(;;){}` , `do{}while(1);`


> **NOTE: Three PYQs on loops**
>
> "Which of the following will terminate the loop immediately in C?" Answer: **When a break statement is encountered**. A `continue` only skips one iteration; the loop keeps running.
>
> "Which of the following causes an infinite loop?" Answer: **while (1) { }**. Check the others: `for(int i=10; i>5; i--)` runs 5 times and stops; `do { } while (0);` runs exactly once; `for(int i=0; i<10; i++)` runs 10 times.
>
> "Which of the following is true about the for loop in C?" Answer: **The condition in a for loop is optional, and it can result in an infinite loop if omitted.** All three parts of a for loop are optional - `for(;;)` is perfectly legal and loops forever. So the claims that a for loop "must always have all three components" and that "increment/decrement is mandatory" are both false, and nesting for loops is certainly allowed.



### D1.5 Tracing output questions - the method


This is the highest-value skill in this Part. Follow a fixed ritual:

1. Write down every variable and its current value in a column.
2. Execute one statement at a time; update the column.
3. Never assume - evaluate operators strictly by precedence.
4. Watch for the classic traps listed below.


#### Trap 1: do-while always runs once


*PYQ*
```
int i = 5;
do {
    printf("%d ", i);
    i--;
} while (i > 5);

TRACE:
  Body runs FIRST (this is do-while, not while).
  printf prints 5.   i becomes 4.
  NOW test: is 4 > 5 ?  NO.  Loop ends.

OUTPUT: 5
```



#### Trap 2: chained relational operators


*PYQ*
```
int a = 5, b = 3, c = 0;
if (a > b > c) { printf("True\n"); } else { printf("False\n"); }

TRACE:
  Relational operators associate LEFT TO RIGHT, so this is  ((a > b) > c).
  Step 1:  a > b   ->  5 > 3  ->  TRUE  ->  the value 1
  Step 2:  1 > c   ->  1 > 0  ->  TRUE  ->  the value 1
  So the condition is true.

OUTPUT: True
```



#### Trap 3: nested ternary operators


*PYQ*
```
int x = -1, y = 0, z = 1;
int result = (x > 0) ? x : (y == 0) ? z : y;

TRACE:
  ?: associates RIGHT to left, so it reads:
      (x > 0) ? x : ( (y == 0) ? z : y )
  Is x > 0 ?  -1 > 0  ->  FALSE.  Take the else branch.
  Else branch is  (y == 0) ? z : y
  Is y == 0 ?  0 == 0  ->  TRUE.  Take z.
  z is 1.

OUTPUT: 1
```



*Simpler ternary PYQ*
```
int a = 10, b = 20;
int max = (a > b) ? a : b;
printf("%d", max);

  10 > 20 is FALSE, so take b = 20.
OUTPUT: 20
```



#### Trap 4: bitwise XOR is not exponentiation


*PYQ*
```
int a = 4, b = 3;
int result = a ^ b;

  ^ in C is bitwise XOR, NOT "to the power of".
      4 = 100
      3 = 011
    XOR = 111  =  7

OUTPUT: 7
```



#### Trap 5: variable shadowing in nested blocks


*PYQ*
```
int x = 10, y = 20;
{
    {
        int y = 40;     /* a NEW y, local to this inner block */
        x++;            /* modifies the OUTER x  -> 11        */
        y++;            /* modifies the INNER y  -> 41        */
    }                   /* the inner y DIES here              */
    printf("x = %d, y = %d\n", x, y);
}

  x was incremented, so x = 11.
  The y printed is the OUTER y, which was never touched, so y = 20.

OUTPUT: x = 11, y = 20
```



#### Trap 6: chained assignment


*PYQ*
```
int a, b, c;
a = b = c = 15;      /* assignment is RIGHT to left: c=15, then b=15, then a=15 */
c = c + 10;          /* c becomes 25 */

  Value of c = 25
```



#### Trap 7: counting nested loop iterations


*PYQ*
```
for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 2; j++) {
        printf("%d ", i);
    }
}

  Outer loop runs 3 times (i = 0,1,2).
  For EACH outer iteration the inner loop runs 2 times.
  Innermost body executions = 3 x 2 = 6

ANSWER: 6 times.  (Printed output would be: 0 0 1 1 2 2)
```



#### Trap 8: array built from a formula


*PYQ*
```
int a[5];
for (int i = 0; i < 5; i++) a[i] = i*i - 2*i + 1;

  Note that i*i - 2i + 1 = (i-1)^2
  i=0 -> (0-1)^2 = 1
  i=1 -> (1-1)^2 = 0
  i=2 -> (2-1)^2 = 1
  i=3 -> (3-1)^2 = 4
  i=4 -> (4-1)^2 = 9

OUTPUT: 1 0 1 4 9
```



#### Trap 9: a pointer that is never advanced


*PYQ*
```
int* func() {
    static int arr[5] = {1,2,3,4,5};   /* static, so it survives the return */
    return arr;
}
int main() {
    int* ptr = func();
    for (int i = 0; i < 5; i++) {
        printf("%d ", *ptr);           /* ptr is NEVER incremented! */
    }
}

  *ptr always dereferences the SAME first element.
  The loop variable i is used only to count, never to index.

OUTPUT: 1 1 1 1 1
```



> **TIP: Why `static` matters here**
>
> Without `static`, `arr` would be a local array destroyed when func() returns, and the returned pointer would be dangling - undefined behaviour. `static` gives it program lifetime, so returning its address is safe. Examiners include `static` deliberately to make the code valid.



#### Trap 10: sprintf returns a character count


*PYQ*
```
char buffer[50];
int n = sprintf(buffer, "Hello, World!");
printf("%d %s", n, buffer);

  sprintf writes the formatted text INTO buffer (it does not print),
  and RETURNS the number of characters written, excluding the '\0'.
  "Hello, World!" -> H e l l o ,  space W o r l d !  = 13 characters.

OUTPUT: 13 Hello, World!
```



#### Trap 11: pointer arithmetic on a string literal


*PYQ (answer key = compilation error)*
```
#include<stdio.h>
main() {
    printf(6 + "Hello World\n");
}

  What the expression MEANS: "Hello World\n" is a char pointer to the
  first character. Adding 6 moves the pointer 6 characters forward:
      H(0) e(1) l(2) l(3) o(4) space(5) W(6)
  so 6 + "Hello World\n" points at "World".

  A modern compiler prints:  World
  The official answer key for this paper, however, said COMPILATION ERROR
  (treating "main()" without a return type and the pointer arithmetic as
  invalid under a strict compiler).

  FOR THE EXAM: remember BOTH. If the options include "World", that is the
  technically correct output. If the key-style option "Compilation error"
  is present alongside, note that this paper chose it.
```



### D1.6 Functions


- **Function declaration / prototype** - Tells the compiler the name, return type and parameter types: `int add(int, int);`
- **Function definition** - The actual body.
- **Formal parameters** - The variables listed in the function DEFINITION - they receive the values.
- **Actual parameters / arguments** - **The values that are passed to a function when it is called.**
- **Return type void** - The function returns nothing.
- **Recursion** - A function calling itself. Needs a base case or it overflows the stack.


| Point | Call by value | Call by reference (address) |
|---|---|---|
| What is passed | A COPY of the value | The ADDRESS of the variable |
| Effect on the original | Cannot be changed | CAN be changed |
| C support | Default behaviour | Simulated using pointers |
| C++ support | Default | True references using & |



> **NOTE: Two PYQs on functions**
>
> "Which of the following techniques can be used to modify the actual variable passed to a function?" Answer: **Pass the address of the actual parameters to function.** Passing a copy cannot affect the original, and the claim that "Standard C has no options for modifying actual variables" is false - that is exactly what pointers are for.
>
> "Which of the following options is correct about the functions in C language?" Answer: **Actual parameters are the values that are passed to a function when it is called.** The distractors describe *formal* parameters (declared in the definition, used to define the signature). Also note actual parameters need not be variables - they can be literals or whole expressions, e.g. `add(3, x+2)`.



### D1.7 Storage classes



| Class | Where stored | Default initial value | Scope | Lifetime |
|---|---|---|---|---|
| auto | Stack | GARBAGE (undefined) | Local to the block in which it is defined | Until the block exits |
| register | CPU REGISTER (a request, not a guarantee) | GARBAGE | Local to the block | Until the block exits |
| static | Data segment | ZERO | Local to the block (or to the file, for a static global) | The WHOLE program |
| extern | Data segment | ZERO | Global - visible across files | The whole program |



> **NOTE: PYQ worked out**
>
> "Which of the following statements is INCORRECT about the storage classes in C?" Answer: **"In Register storage class, the default initial value of the variable is zero."**
>
> That is false - like `auto`, a `register` variable starts with **garbage**. Only `static` and `extern` variables are guaranteed to be initialised to zero.
>
> The other three statements are all correct: auto variables are local to their block; static variables default to zero; a register variable's storage is (ideally) a CPU register. Also note you cannot take the address of a register variable with `&`, because it may not live in memory at all.



### D1.8 Arrays and strings


- **Array** - A collection of elements of the SAME type stored in CONTIGUOUS memory, accessed by an index starting at 0.
- **Array name** - Behaves as a constant pointer to the first element. It **cannot be reassigned**.
- **String in C** - A char array terminated by the null character `'\0'`. So "abc" needs 4 bytes.


*Legal and illegal array declarations*
```
int a[5];                        /* OK - uninitialised, garbage values     */
int b[5] = {1,2,3,4,5};          /* OK - full initialisation               */
int c[5] = {1,2};                /* OK - rest are filled with 0            */
int d[]  = {1,2,3};              /* OK - size inferred as 3                */
char e[] = "consultancy";        /* OK - size inferred as 12 (incl. '\0')  */
char f[6] = {};                  /* OK in C (empty braces) - all zeros     */
char g[6] = {2};                 /* OK - first element 2, rest 0           */

char h[6];
h = "consultancy";               /* ILLEGAL - an array name is not a
                                    modifiable lvalue. Use strcpy(h, ...) */
```



> **NOTE: PYQ worked out**
>
> "Which of the following is NOT a correct way of declaring and initializing array in C?" Answer: **`char arr[6]; arr = "consultancy";`**
>
> Two things are wrong with it: (1) you cannot **assign** to an array name after declaration - assignment is only allowed as part of the declaration; and (2) even if you could, "consultancy" needs 12 bytes and `arr` only has 6. The fix is `strcpy(arr, "...")` with a big enough array.



#### Two-dimensional arrays

`char names[5][20];` means **5 names, each up to 20 characters long**. The FIRST dimension is the number of rows (how many strings), the SECOND is the maximum length of each.


> **NOTE: Direct PYQ**
>
> "What does the first dimension and the second dimension represent in a two-dimensional character array?" Answer: **The first dimension represents the number of names in the array, and the second dimension represents the maximum length of each name.** Think of it as "how many, then how long".



#### String functions


| Function | Purpose |
|---|---|
| strlen(s) | Length, NOT counting the '\0' |
| strcpy(d, s) | Copy s into d |
| strncpy(d, s, n) | Copy at most n characters |
| strcat(d, s) | Append s to d |
| strcmp(a, b) | Returns 0 if equal, negative if a<b, positive if a>b. Never use == on strings |
| strrev(s) | Reverse (not standard C) |
| strstr(a, b) | Find substring b inside a |



### D1.9 Pointers


A **pointer** is a variable that stores the **address** of another variable.


*Pointer basics*
```
int x = 10;
int *p;          /* p is a pointer to int          */
p = &x;          /* & gives the ADDRESS of x       */
printf("%d", *p);   /* * DEREFERENCES: prints 10   */
*p = 20;         /* changes x itself to 20         */
```


- **NULL pointer** - A pointer set to 0 / NULL, pointing to nothing. Dereferencing it crashes the program.
- **Void pointer** - `void *p;` - a generic pointer that can hold any address but must be cast before dereferencing.
- **Dangling pointer** - Points to memory that has been freed or has gone out of scope.
- **Wild pointer** - Never initialised - contains garbage.
- **Pointer arithmetic** - `p+1` moves forward by `sizeof(*p)` bytes, not by 1 byte.
- **Array-pointer duality** - `a[i]` is exactly `*(a + i)`.
- **Double pointer** - `int **pp;` - a pointer to a pointer.


#### Dynamic memory allocation


| Function | Behaviour |
|---|---|
| malloc(n) | Allocates n bytes; contents are UNINITIALISED (garbage). Returns void* |
| calloc(count, size) | Allocates count x size bytes and sets them all to ZERO |
| realloc(p, n) | Resizes an existing block, preserving contents |
| free(p) | Releases the block. Failing to free causes a MEMORY LEAK |



### D1.10 Structures and unions



| Point | Structure (struct) | Union |
|---|---|---|
| Memory | Each member gets its OWN memory. Size = sum of members (plus padding) | ALL members SHARE the same memory. Size = size of the LARGEST member |
| Members active | All at once | Only ONE at a time |
| Use | Group related but independent data | Save memory when only one value is needed at a time |


- **Dot operator** - `s.member` - used with a structure variable.
- **Arrow operator** - `p->member` - used with a pointer to a structure. Same as `(*p).member`.
- **typedef** - Creates an alias for a type: `typedef struct Node Node;`
- **enum** - A user-defined type of named integer constants, numbered from 0 by default.


### D1.11 File handling in C



| Mode | Meaning |
|---|---|
| "r" | Read. File must exist |
| "w" | Write. Creates the file, or ERASES existing contents |
| "a" | Append. Writes at the end; creates if absent |
| "r+" | Read and write, file must exist |
| "w+" | Read and write, truncates or creates |
| "a+" | Read and append |
| Add "b" | Binary mode, e.g. "rb", "wb" |


- **fopen / fclose** - Open and close a file; fopen returns a FILE* or NULL on failure.
- **fprintf / fscanf** - Formatted write / read.
- **fgets / fputs** - String read / write.
- **fread / fwrite** - Block (binary) read / write.
- **fseek / ftell / rewind** - Move the file position, report it, reset to the start.
- **EOF** - End Of File marker, the value -1.


## D2 Object Oriented Programming Concepts



### D2.1 Why OOP exists


Older "procedural" programming separated data from the functions that worked on it. In a big program this got messy - any function could corrupt any data.

**Object Oriented Programming** bundles the data and the functions that operate on that data into a single unit called an **object**. Real-world thinking is mirrored in code.

- **Class** - A **blueprint / template**. It defines what data and behaviour objects of that type will have. A class occupies no memory by itself.
- **Object** - An **instance** of a class - an actual thing created from the blueprint, with its own memory.

Analogy: "Car" is the class (the design drawing). Your neighbour's red Maruti is an object.


### D2.2 The four pillars



#### 1. Encapsulation - wrapping data and methods together

Binding the data and the methods that operate on that data into one single unit, and **hiding the internal details** from the outside world. Access is only through public methods (getters and setters).

Analogy: a **medicine capsule**. The powders inside are wrapped together; you swallow the capsule without touching the contents.

- **Data hiding** - The security benefit of encapsulation - declaring members `private` so outside code cannot corrupt them.


> **NOTE: Direct PYQ**
>
> "What is the objective of encapsulation in object-oriented programming?" Answer: **To combine data and methods that operate on that data within a single unit.**
>
> Note the distractors, which each define a *different* pillar: "create multiple instances of a class" is instantiation, "enable one class to inherit from another" is inheritance, and "allow objects to take multiple forms" is polymorphism. Questions like this test whether you can tell the four pillars apart - so learn one crisp phrase for each.



#### 2. Inheritance - reusing an existing class

A new class (child / derived / sub class) acquires the properties and behaviour of an existing class (parent / base / super class). It gives **code reusability** and models "is-a" relationships.


| Type | Meaning |
|---|---|
| Single | One child, one parent |
| Multilevel | A chain: A to B to C |
| Hierarchical | One parent, many children |
| Multiple | One child, MANY parents. Supported in C++; NOT supported for classes in Java (Java uses interfaces instead) - this avoids the "Diamond Problem" ambiguity |
| Hybrid | A combination of the above |



#### 3. Polymorphism - one name, many forms

The same interface behaves differently depending on the context. "Poly" = many, "morph" = form.


| Kind | Also called | How | When resolved |
|---|---|---|---|
| Compile-time | Static binding / early binding | Function OVERLOADING and OPERATOR OVERLOADING - same name, different parameter lists | At compile time |
| Run-time | Dynamic binding / late binding | Function OVERRIDING using virtual functions and base-class pointers | At run time |


- **Overloading** - Same function name in the SAME class with **different parameters**. Return type alone is not enough to overload.
- **Overriding** - A child class provides its own version of a method that already exists in the parent, with the **same signature**.
- **Operator overloading** - Giving an existing operator (+, -, <<) a new meaning for user-defined types. Supported in C++, **not** in Java.


> **NOTE: PYQ worked out - read this one carefully**
>
> "What feature of OOP allows an instance of a class to take on many forms?" The answer key gave **Operator overloading**.
>
> The concept genuinely being described is **polymorphism**, and since "polymorphism" itself was not an option, the paper expected you to pick the mechanism that *implements* it. Among the four choices - Operator overriding (not a real term), Multiple inheritance, Nested class, Operator overloading - only **operator overloading** is a genuine polymorphism mechanism. Note that "operator overriding" does not exist as a term; operators are overloaded, methods are overridden.



#### 4. Abstraction - showing only what matters

Exposing only the essential features and hiding the complex implementation.

Analogy: when you drive, you use the steering wheel and pedals. You do not need to know how combustion works. The car **abstracts** the engine away.

- **Abstract class** - A class that cannot be instantiated (no objects can be created from it). It exists only to be inherited from. It may contain both abstract (unimplemented) and concrete methods.
- **Interface** - A pure contract - a list of method signatures a class promises to implement.
- **Abstraction vs Encapsulation** - Abstraction hides **complexity** (design level, "what"). Encapsulation hides **data** (implementation level, "how").


### D2.3 Other OOP terms


- **Constructor** - A special method with the same name as the class, called automatically when an object is created, used to initialise it. It has NO return type. Can be overloaded.
- **Destructor** - Called automatically when an object is destroyed, to release resources. In C++ written as ~ClassName(). Cannot be overloaded.
- **Copy constructor** - Creates a new object as a copy of an existing one.
- **this / self pointer** - A reference to the current object.
- **Static member** - Belongs to the CLASS, not to any object. One copy shared by all objects.
- **Friend function (C++)** - A non-member function granted access to private members.
- **Message passing** - Objects communicate by calling each other's methods. `myObject.doActivity();` means **calling the method doActivity on the object myObject**.
- **Association / Aggregation / Composition** - Relationships between objects. Aggregation is a weak "has-a" (a department has professors, who survive independently). Composition is a strong "part-of" (a house has rooms; destroy the house and the rooms go too).


> **NOTE: Direct PYQ**
>
> "What does the below code snippet represent? `myObject.doActivity();`" Answer: **Calling a method named doActivity on the object myObject.**
>
> The distractors misuse terminology: it is not "sending a message to the doActivity class" (doActivity is a method, not a class), it does not create an object (that needs `new`), and nothing is sent to a child class.



## D3 Java



### D3.1 What makes Java special


- **Platform independence** - Java source is compiled into **bytecode** (a .class file), not native machine code. The **JVM** on any machine can run that bytecode. This is the "Write Once, Run Anywhere" idea.
- **JDK** - Java Development Kit - the full toolset: compiler (javac), debugger, JRE.
- **JRE** - Java Runtime Environment - JVM plus the standard libraries. Enough to RUN, not to compile.
- **JVM** - Java Virtual Machine - interprets/JIT-compiles bytecode into native instructions.
- **JIT compiler** - Just In Time compiler inside the JVM; compiles hot bytecode into native code at run time for speed.
- **Garbage collection** - Java automatically frees objects that are no longer reachable. There is no `free()` or `delete`.


#### Java features

Simple, object-oriented, platform independent, secure, robust, multithreaded, architecture-neutral, portable, high performance (JIT), distributed, dynamic.


### D3.2 Class loaders


Java loads classes lazily using a hierarchy of class loaders, each delegating upward to its parent first.


| Loader | Loads from | Position |
|---|---|---|
| Bootstrap (Primordial) ClassLoader | The core Java API (rt.jar, java.lang etc.) | The ROOT - has no parent |
| Extension ClassLoader | The ext directory (jre/lib/ext) | Child of Bootstrap |
| System / Application ClassLoader | The application CLASSPATH | Child of Extension - the LOWEST in the chain |



> **NOTE: PYQ worked out**
>
> "______ does NOT have any child ClassLoaders." Options: BootStrap ClassLoader, Extension ClassLoader, Primordial ClassLoader, **System ClassLoader**. Answer: **System ClassLoader**.
>
> Reasoning: the hierarchy runs Bootstrap to Extension to System. Bootstrap has Extension as its child; Extension has System as its child; **System is at the bottom, so it has no children.** Note the trap: "Primordial ClassLoader" is just another name for the Bootstrap loader, so it does have a child.



### D3.3 Access modifiers - the order matters



| Modifier | Same class | Same package | Subclass (other package) | Everywhere |
|---|---|---|---|---|
| private | Yes | No | No | No |
| default (no keyword) / package-private | Yes | Yes | No | No |
| protected | Yes | Yes | YES | No |
| public | Yes | Yes | Yes | Yes |


Ordered from **most restrictive to least restrictive**: **private, (default/package), protected, public**.


> **NOTE: Two PYQs on access modifiers**
>
> "Identify the descending order of strict access protection." Answer: **Private, protected, package, public.**
>
> Note something important: strictly speaking, `protected` is *less* restrictive than package-default in Java, because protected additionally allows subclasses in other packages. So the textbook descending order is private > default(package) > protected > public. This paper's key placed protected before package. If you meet this question again, look for the option that starts with **Private** and ends with **public** - that will be the intended answer.
>
> "Which access modifier can be used to access members in a deriving class?" Answer: **Protected**. `private` blocks subclasses; `public` works but is not the *specific* modifier designed for inheritance; and `Void` is a return type, not an access modifier at all.



> **NOTE: PYQ worked out - protected across inheritance**
>



*PYQ: what happens when this runs?*
```
class Parent {
    protected void protectedMethod() {
        System.out.println("Protected method in Parent");
    }
}
class Child extends Parent {
    public void childMethod() {
        protectedMethod();          /* legal - inherited protected member */
    }
}
public class Test {
    public static void main(String[] args) {
        Child child = new Child();
        child.childMethod();
    }
}

REASONING:
  Child extends Parent, so Child INHERITS protectedMethod().
  A protected member is fully accessible inside a subclass.
  childMethod() is public, so main() can call it.
  Nothing here is illegal.

OUTPUT: Protected method in Parent
(The code compiles and prints that line.)
```



### D3.4 Keywords: final, static, super, this



| Keyword | On a variable | On a method | On a class |
|---|---|---|---|
| final | Becomes a CONSTANT - value cannot change | CANNOT be OVERRIDDEN | CANNOT be INHERITED (no subclass) |
| static | One copy shared by all objects (class variable) | Belongs to the class; callable without an object | Only for nested classes |
| abstract | - | No body; must be overridden | Cannot be instantiated |


- **super** - **Refers to the parent class.** `super.method()` calls the parent's version; `super()` calls the parent constructor.
- **this** - Refers to the current object. `this()` calls another constructor of the same class.


> **NOTE: Two direct PYQs**
>
> "What does the super keyword in Java do?" Answer: **Refers to the parent class.** (`this` refers to the current object - do not swap them.)
>
> "Which of the following statements is FALSE?" Answer: **"Final methods can be overridden."** A `final` method is precisely one that **cannot** be overridden. The other statements in that question were all true: `static public void main(String... abcd){}` is valid (varargs is allowed and modifier order does not matter); abstract classes cannot be instantiated; and since Java 8 an interface **can** have `default` method definitions with a body.



### D3.5 The main() method



*Valid forms of main*
```
public static void main(String[] args)        /* the standard form        */
static public void main(String[] args)        /* modifier order is free   */
public static void main(String... args)       /* varargs is allowed       */
public static void main(String args[])        /* C-style brackets are ok  */
```


Why each keyword is needed: **public** so the JVM can call it from outside; **static** so no object is needed before the program starts; **void** because it returns nothing to the JVM; **String[]** to receive command-line arguments.


### D3.6 Exception handling


- **Exception** - An abnormal event during execution that disrupts the normal flow, but which the program can recover from.
- **Error** - A serious problem the program should not try to handle (OutOfMemoryError, StackOverflowError).


*The hierarchy*
```
                       Throwable
                      /         \
                 Error           Exception
              (do not catch)    /          \
                   CheckedException      RuntimeException
                   IOException,          (UNCHECKED)
                   SQLException,         ArithmeticException,
                   ClassNotFound         NullPointerException,
                                         ArrayIndexOutOfBounds,
                                         NumberFormatException
```


- **Checked exception** - Detected at COMPILE time. You must either catch it or declare `throws`. Example: IOException.
- **Unchecked exception** - A subclass of RuntimeException; detected at RUN time. The compiler does not force you to handle it.
- **throw** - Actually throws an exception object: `throw new Exception("msg");`
- **throws** - Declares in the method signature that this method may throw something.
- **finally** - A block that **ALWAYS executes**, whether an exception occurred or not, and even if the try block executes `return`. Used for cleanup - closing files and connections.


#### The rules of try-catch-finally

- A try block **may have many catch blocks**, but **only ONE finally block**.
- Catch blocks must be ordered from the most specific subclass to the most general (`ArithmeticException` before `Exception`), otherwise the code will not compile.
- A try block needs at least one catch **or** a finally - it cannot stand alone.
- A try can exist with only finally and no catch.


> **NOTE: Direct PYQ**
>
> "Select the true statement about try-catch blocks." Answer: **A try block can have many catches but only 1 finally block.** The other options - "must have at least 1 catch to have a finally", "must have only 1 finally for each catch block", "many catches and many finally blocks" - are all wrong.



*PYQ traced: nested try with re-thrown exception*
```
public class ExceptionTest {
  public static void main(String[] args) {
    try {
      System.out.println("Result: " + calculate(10, 0));
    } catch (ArithmeticException e) {
      System.out.println("ArithmeticException caught: " + e.getMessage());
    } catch (Exception e) {
      System.out.println("General exception caught: " + e.getMessage());
    } finally {
      System.out.println("In finally block.");
    }
  }
  public static int calculate(int a, int b) throws Exception {
    try {
      return a / b;
    } catch (ArithmeticException e) {
      throw new Exception("Division by zero not allowed");
    } finally {
      System.out.println("Inner finally block executed.");
    }
  }
}

STEP-BY-STEP:
 1. main calls calculate(10, 0).
 2. 10 / 0 throws ArithmeticException ("/ by zero").
 3. The INNER catch grabs it and throws a NEW plain Exception whose
    message is "Division by zero not allowed".
 4. But before control leaves calculate(), the INNER FINALLY must run.
       -> prints "Inner finally block executed."
 5. The new Exception travels to main. Its actual type is Exception,
    NOT ArithmeticException, so the FIRST catch does NOT match.
    The second catch (Exception e) matches.
       -> prints "General exception caught: Division by zero not allowed"
 6. main's finally always runs.
       -> prints "In finally block."

OUTPUT:
Inner finally block executed.
General exception caught: Division by zero not allowed
In finally block.
```



> **TIP: The two lessons from that question**
>
> (1) **finally runs even when the try block contains `return` or throws.**
> (2) Once you wrap an exception in a new type, only catch blocks matching the **new** type will fire. The original ArithmeticException message "/ by zero" is lost and replaced by your own message.



*PYQ traced: custom exception*
```
class CustomException extends Exception {
    public CustomException(String message) { super(message); }
}
public class TestCustomException {
    public static void main(String[] args) {
        try { validateAge(15); }
        catch (CustomException e) {
            System.out.println("Caught Exception: " + e.getMessage());
        } finally {
            System.out.println("Execution finished.");
        }
    }
    public static void validateAge(int age) throws CustomException {
        if (age < 18) throw new CustomException("Age must be 18 or above.");
        System.out.println("Age is valid.");
    }
}

REASONING:
  age = 15, and 15 < 18, so the exception IS thrown.
  Therefore "Age is valid." is NEVER printed.
  super(message) passes the text to Throwable, so getMessage()
  returns "Age must be 18 or above." - not null.
  finally always runs.

OUTPUT:
Caught Exception: Age must be 18 or above.
Execution finished.
```



### D3.7 Java output traps



*PYQ: printing an int then a char*
```
int Integer = 24;         /* "Integer" used as a variable name - legal!  */
char String = 'I';        /* "String" used as a variable name - legal!   */
System.out.print(Integer);
System.out.print(String);

  Integer and String are not reserved keywords in Java, only class names,
  so they may be used as identifiers. print() does not add a newline.

OUTPUT: 24I
```



### D3.8 Packages


- **Package** - A named grouping of related classes and interfaces - effectively a folder.
- **Benefits** - Prevents **naming conflicts** (two classes may share a name in different packages); provides **controlled access** through the default and protected modifiers; considered a form of **data encapsulation**; makes classes easier to locate and reuse.
- **import** - Brings a class or a whole package into scope.


> **NOTE: PYQ worked out**
>
> "Which of the following is FALSE about packages?" Answer: **"Packages cannot provide controlled access."**
>
> That is false - packages **do** provide controlled access, because `default` (package-private) and `protected` members are visible only within the same package. The other statements are all true: packages prevent naming conflicts, and packages are considered a form of data encapsulation.



### D3.9 Java collections



| Interface / Class | Key property |
|---|---|
| Collection | The root interface for groups of objects |
| List | ORDERED, allows duplicates, index-based. Implementations: ArrayList, LinkedList, Vector |
| Set | NO duplicates. Implementations: HashSet (unordered), LinkedHashSet (insertion order), TreeSet (sorted) |
| Map | Key to value pairs, keys unique. NOT a Collection subinterface. Implementations: HashMap, LinkedHashMap, TreeMap, Hashtable |
| Queue | FIFO. PriorityQueue, ArrayDeque |
| ArrayList | Dynamic array. Fast random access, slow insert/delete in the middle. NOT synchronised |
| LinkedList | Doubly linked list. Fast insert/delete, slow random access |
| Vector | Like ArrayList but SYNCHRONISED (thread-safe), legacy |
| HashMap | Allows ONE null key and many null values. Not synchronised. Faster |
| Hashtable | No null key or value. Synchronised. Legacy |



> **NOTE: Direct PYQ**
>
> "What is the name of the .NET collection class that enables an element to be accessed using a unique key?" Answer: **Hashtable**.
>
> A Hashtable stores key-value pairs and retrieves a value directly from its unique key using a hash function, giving average O(1) access. A Linked list, Double linked list and Array list are all accessed by position or by traversal, not by key.



## D4 C++ Specifics and the .NET Framework



### D4.1 C++ points that get asked


- **cin / cout** - Input and output stream objects from `<iostream>`. Used with the extraction operator `>>` and insertion operator `<<`.
- **Reference variable** - An alias: `int &r = x;` Must be initialised at declaration and cannot be reseated.
- **Inline function** - A request to the compiler to substitute the function body at the call site, avoiding call overhead.
- **Virtual function** - A member function declared `virtual` in the base class so that calls through a base pointer are resolved at RUN time (dynamic dispatch).
- **Pure virtual function** - `virtual void f() = 0;` It has no body. A class containing one becomes an **abstract class** and cannot be instantiated.
- **Namespace** - Prevents name clashes: `using namespace std;`
- **Template** - Generic programming - one definition works for many types.
- **Default arguments** - Parameters with default values, which must be the rightmost ones.


> **NOTE: PYQ worked out - cin.ignore()**
>
> "In C++ language, the instruction `ignore(x, y);` ______." Answer: **skips the first x characters and stops if character y is encountered.**
>
> Explanation: `cin.ignore(n, delim)` discards characters from the input buffer. It stops as soon as **either** it has discarded n characters **or** it has read and discarded the delimiter character. Its usual use is `cin.ignore(1000, '\n')` to throw away the leftover newline before a `getline()`.
>
> Note the ordering trap in the options: x is the COUNT (first argument) and y is the DELIMITER (second argument). Options that swap them, or that say "last x characters", are wrong.



### D4.2 The .NET Framework



| Component | Full form | Role |
|---|---|---|
| CLR | Common Language Runtime | The EXECUTION ENGINE for .NET applications and servers; the interface between .NET applications and the operating system. Handles memory management, garbage collection, security, exception handling, thread management |
| CTS | Common Type System | Defines how types are declared and used, so all .NET languages agree on what an "int" is |
| CLS | Common Language Specification | A subset of rules every .NET language must follow so the languages can interoperate |
| FCL / BCL | Framework Class Library / Base Class Library | The huge library of reusable classes |
| MSIL / CIL / IL | Microsoft Intermediate Language | A CPU-INDEPENDENT and PLATFORM-INDEPENDENT set of instructions produced by the compiler, which the CLR later converts into native code |
| JIT | Just In Time compiler | Converts MSIL into native machine code at run time |
| Assembly | - | The compiled unit (.dll or .exe) containing MSIL plus a manifest |
| CLI | Common Language Infrastructure | The overall specification standardised as ECMA-335 |



> **NOTE: Two direct PYQs on .NET**
>
> "______ is a code that consists of CPU and platform-independent set of instructions, which can be easily converted to the native code." Answer: **MSIL** (Microsoft Intermediate Language). Not DLL (a compiled library file), not FCL (a class library), not JIT (the converter, not the code).
>
> "Which of the following is the execution engine for .NET applications and servers as the interface between .NET applications and the operating system?" Answer: **Common Language Runtime (CLR)**. FCL is a library, CTS is a type specification, CLS is a language-rules specification - none of them *execute* anything.



#### ADO.NET

ADO.NET is the .NET data-access technology used to connect to databases.

- **Key features** - Interoperability, Maintainability, Programmability, Performance, Scalability.
- **Main objects** - Connection, Command, DataReader (fast, forward-only, connected), DataAdapter and DataSet (disconnected in-memory copy of data).


> **NOTE: Direct PYQ**
>
> "Which of the following is NOT a feature of ADO.net?" Options: Maintainability, Interoperability, **Reachability**, Scalability. Answer: **Reachability**. The genuine ADO.NET feature list is interoperability, maintainability, programmability, performance and scalability. "Reachability" is a graph-theory / garbage-collection term, not an ADO.NET feature.



#### ASP.NET server controls


*The correct syntax for a .NET server control*
```
<asp:controlType ID="ControlID" runat="server" Property1=value1 [Property2=value2] />

The mandatory attribute is  runat="server"
Common wrong spellings offered in exams: runin, runas, run
```



> **NOTE: Direct PYQ**
>
> "How to write the dot net server control?" Answer: the option using **`runat="server"`**. Every ASP.NET server control must carry `runat="server"` - that attribute is what tells the framework to process the tag on the server rather than send it to the browser as plain HTML. Memorise the exact spelling: r-u-n-a-t.




---

# PART E - Data Structures and Algorithms

> *Learn every complexity in the tables by heart. Roughly one question in ten comes from this Part, and most are pure recall.*



## E1 Complexity Analysis



### E1.1 What "complexity" means


Suppose two students must find a name in a phone book of 1000 pages.
- Student A reads page 1, then page 2, then page 3... In the worst case he reads all 1000 pages.
- Student B opens the middle, decides "before or after", and throws away half. He needs about 10 steps.

Both get the right answer. B's **method** is fundamentally better. Complexity is the language we use to say that precisely, **without** worrying about which computer we run on.

- **Time complexity** - How the number of basic operations grows as the input size n grows.
- **Space complexity** - How much extra memory the algorithm needs as n grows.
- **Auxiliary space** - Extra space **excluding** the input itself. In-place algorithms use O(1) auxiliary space.


### E1.2 The three cases



| Case | Meaning |
|---|---|
| Best case | The most favourable input. Gives a lower bound on running time |
| Average case | The expected time over all possible inputs. Hardest to compute |
| Worst case | The most unfavourable input. THE MOST IMPORTANT in practice, because it gives a guarantee |



> **NOTE: Direct PYQ**
>
> "Which of the following cases DOES NOT exist when one computes the time complexity of an algorithm?" Options: Average case, Worst case, **Test Case**, Best Case. Answer: **Test Case**.
>
> A "test case" belongs to **software testing**, not to complexity analysis. Only three cases exist for complexity: best, average and worst.



### E1.3 Asymptotic notations



| Notation | Name | Bounds | Plain meaning |
|---|---|---|---|
| O(f) | Big Oh | Asymptotically TIGHT UPPER bound | "grows no faster than" - the worst case |
| Omega | Big Omega | Asymptotically TIGHT LOWER bound | "grows at least as fast as" - the best case |
| Theta | Big Theta | BOTH tight upper AND tight lower bound | "grows exactly like" - the exact order |
| small o | Little oh | Loose (non-tight) upper bound | "grows strictly slower than" |
| small omega | Little omega | Loose lower bound | "grows strictly faster than" |



> **NOTE: Direct PYQ**
>
> "Which of the following asymptotic notation gives asymptotically tight upper bound as well as asymptotically tight lower bound?" Answer: **Theta**.
>
> The trigger words are "**as well as**" - meaning both bounds at once. Big Oh alone gives only the upper bound; Omega alone gives only the lower bound; small omega is not even a tight bound. Theta is the one notation that sandwiches the function from both sides.



### E1.4 The order of growth - memorise this sequence


From slowest-growing (best) to fastest-growing (worst):


*The growth hierarchy*
```
O(1)  <  O(log n)  <  O(sqrt n)  <  O(n)  <  O(n log n)  <  O(n^2)
      <  O(n^2 log n)  <  O(n^3)  <  O(2^n)  <  O(n!)  <  O(n^n)

  constant < logarithmic < linear < linearithmic < quadratic
          < cubic < exponential < factorial
```



> **NOTE: PYQ worked out - arrange in order of growth**
>
> "Arrange the following in the order of growth: O(n), O(n^2), O(2^n), O(log n), O(n log n), O(n^2 log n)"
>
> Answer: **O(log n), O(n), O(n log n), O(n^2), O(n^2 log n), O(2^n)**
>
> How to be sure. Plug in a reasonably large n, say n = 1024 (so log n = 10):



| Function | Value at n = 1024 | Rank |
|---|---|---|
| O(log n) | 10 | 1 (smallest) |
| O(n) | 1,024 | 2 |
| O(n log n) | 10,240 | 3 |
| O(n^2) | 1,048,576 | 4 |
| O(n^2 log n) | 10,485,760 | 5 |
| O(2^n) | 2^1024 - astronomically large | 6 (largest) |



> **TIP: The single rule that resolves any ordering question**
>
> **Polynomials always beat exponentials.** No matter how large the power, n^100 eventually loses to 2^n. And any log factor is weaker than one extra power of n, so n^2 < n^2 log n < n^3.



### E1.5 Recurrence relations and the Master Theorem


Divide-and-conquer algorithms are described by recurrences.


| Recurrence | Solution | Algorithm |
|---|---|---|
| T(n) = T(n/2) + O(1) | O(log n) | BINARY SEARCH |
| T(n) = 2T(n/2) + O(1) | O(n) | Tree traversal |
| T(n) = 2T(n/2) + O(n) | O(n log n) | MERGE SORT, best-case quick sort |
| T(n) = T(n-1) + O(1) | O(n) | Linear search (recursive) |
| T(n) = T(n-1) + O(n) | O(n^2) | WORST-case quick sort, selection sort |
| T(n) = 2T(n-1) + O(1) | O(2^n) | Tower of Hanoi |
| T(n) = 7T(n/2) + O(n^2) | O(n^2.81) | STRASSEN'S matrix multiplication |



> **NOTE: PYQ worked out - the binary search recurrence trap**
>
> "Which of the following statements is correct about the divide and conquer approach of binary search technique?"
>
> The correct answer is: **The worst-case time complexity of binary search is O(log n).**
>
> Now examine the tempting wrong option: "The recurrence relation of binary search is written as T(n) = 2T(n/2) + O(1)". This is **wrong** because binary search discards half the array and searches only **ONE** half - so the coefficient is 1, not 2. The correct recurrence is **T(n) = T(n/2) + O(1)**.
>
> Also wrong: "The best-case time complexity of binary search is O(log n)" - the **best** case is **O(1)**, when the middle element is the target on the very first comparison. And "the average-case time complexity is O(n)" is wrong; the average case is also O(log n).



*Binary search complexities - lock these in*
```
Best case    : O(1)        (target is the middle element immediately)
Average case : O(log n)
Worst case   : O(log n)
Space        : O(1) iterative,  O(log n) recursive (call stack)
PRECONDITION : the array MUST already be sorted
```



## E2 Linear Data Structures



### E2.1 The big classification



| Category | Structures |
|---|---|
| LINEAR - elements in a sequence, one after another | Array, Linked list, Stack, Queue |
| NON-LINEAR - an element may connect to many others | Tree, Graph, Heap |
| Static - size fixed at compile time | Array |
| Dynamic - size grows and shrinks at run time | Linked list, dynamic array, tree, graph |



> **NOTE: PYQ worked out**
>
> "What are the data structures categorised as a linear list?" Options: Binary tree, Graphs, Circular queue, **Array**. Answer: **Array**.
>
> Reasoning: a **linear list** means elements are arranged in a strict sequence with each element having exactly one predecessor and one successor. Binary trees and graphs are clearly non-linear. A circular queue is linear in a loose sense but it is a *queue* (an abstract data type with restricted access), not a "linear list" in the classic sense - and more importantly, its last element links back to the first, breaking the plain sequence. The textbook answer for "linear list" is the **array**.



### E2.2 Arrays


- **Array** - A fixed-size collection of elements of the same type in CONTIGUOUS memory locations, accessed by index.
- **Address formula (1-D)** - Address of a[i] = Base + w x (i - lower bound), where w is the size of each element.
- **Row-major order** - Elements stored row by row (C, C++, Java, Python).
- **Column-major order** - Elements stored column by column (FORTRAN, MATLAB, R).


| Operation | Complexity | Reason |
|---|---|---|
| Access a[i] | O(1) | Direct address calculation - the great strength of arrays |
| Search (unsorted) | O(n) | Must scan |
| Search (sorted) | O(log n) | Binary search |
| Insert at end (space available) | O(1) | - |
| Insert at beginning / middle | O(n) | Every later element must SHIFT right |
| Delete from beginning / middle | O(n) | Every later element must SHIFT left |
| Delete from end | O(1) | - |



> **NOTE: Direct PYQ**
>
> "Calculate the time complexity of deleting an element from the beginning of a dynamic array." Answer: **O(n)**.
>
> Reason: after removing a[0], every one of the remaining n-1 elements must be moved one position to the left to keep the memory contiguous. That is n-1 moves, which is O(n). Only deletion at the **end** is O(1).



### E2.3 Linked lists


A **linked list** is a chain of **nodes**. Each node holds the data plus the address (link) of the next node. Nodes may sit anywhere in memory.

Analogy: a **treasure hunt**. Each clue slip contains a prize and the location of the next slip. To reach the fifth slip you must walk through the first four - you cannot jump straight to it.


*Node structures*
```
SINGLY LINKED LIST node:
    +--------+--------+
    |  DATA  |  NEXT  | ----> next node ... last node's NEXT = NULL
    +--------+--------+

DOUBLY LINKED LIST node:
    +--------+--------+--------+
    |  PREV  |  DATA  |  NEXT  |
    +--------+--------+--------+

CIRCULAR LINKED LIST: the last node's NEXT points back to the HEAD
```



| Type | Structure |
|---|---|
| Singly linked | Each node has DATA and the address of the NEXT node. One-way traversal only |
| Doubly linked | Each node has the address of both the previous AND the next node. Two-way traversal; needs one extra pointer per node |
| Circular singly | The last node points back to the first |
| Circular doubly | Last points to first and first points back to last |
| Header linked list | A special first node holding information about the list |



> **NOTE: Direct PYQ**
>
> "In singly linked list, each node of the list consists of ______." Answer: **data value and address of next node.**
>
> Eliminate the rest: "NULL and address of the next node" - only the *last* node contains NULL; "address of the previous node" describes a **doubly** linked list.



#### Array vs Linked list - the comparison table


| Point | Array | Linked list |
|---|---|---|
| Memory | Contiguous | Scattered, connected by pointers |
| Size | Fixed (static) | Grows and shrinks at run time |
| Access to the i-th element | O(1) - direct, by index | O(n) - must TRAVERSE from the head. This is its main disadvantage |
| Insert / delete at the beginning | O(n) - shifting needed | O(1) - just change a pointer |
| Memory overhead | None | Extra space for each pointer |
| Memory utilisation | May waste allocated space or run out | Allocates exactly what is needed |
| Cache performance | Good (locality of reference) | Poor (nodes are scattered) |
| Binary search | Possible | Not practical |



> **NOTE: Direct PYQ**
>
> "Which of the following is a disadvantage of singly linked list?" Answer: **Accessing an element in a singly linked list requires traversal from the head, making it slower than arrays.**
>
> The other three options are all **advantages**, deliberately dressed up as answers: insertion at the beginning in O(1), deletion at the beginning in O(1), and having a variable size are all reasons to *prefer* a linked list.



### E2.4 Stack - Last In First Out


A **stack** allows insert and delete at **one end only**, called the **top**.

Analogy: a **pile of plates**. You add a plate on top and you take a plate from the top. The plate placed last is removed first.

- **LIFO** - Last In, First Out.
- **push** - Insert an element on top. Increments top.
- **pop** - Remove the top element.
- **peek / top** - Read the top element without removing it.
- **Overflow** - Pushing onto a full stack.
- **Underflow** - Popping from an empty stack.
- **Complexity** - push, pop, peek are all **O(1)**. Search is O(n).


#### Applications of a stack (asked as a list)

- Function call management - the **call stack** holds return addresses and local variables. This is why deep recursion causes StackOverflow.
- **Recursion** implementation.
- Expression conversion: infix to postfix / prefix.
- Expression **evaluation** of postfix and prefix.
- Checking balanced parentheses.
- Undo / Redo in editors.
- Browser back button history.
- **Depth First Search (DFS)** in graphs.
- Backtracking algorithms.
- Reversing a string or a list.


#### Notations


| Notation | Form | Example for a+b |
|---|---|---|
| Infix | operand operator operand | a + b |
| Prefix (Polish) | operator operand operand | + a b |
| Postfix (Reverse Polish) | operand operand operator | a b + |


Computers prefer postfix because it needs no parentheses and no precedence rules - it can be evaluated in a single left-to-right pass using one stack.


### E2.5 Queue - First In First Out


A **queue** inserts at one end (the **rear**) and deletes from the other end (the **front**).

Analogy: a **line at a ticket counter**. The first person to join is the first served.

- **FIFO** - First In, First Out.
- **enqueue** - Insert at the rear.
- **dequeue** - Remove from the front.
- **Complexity** - enqueue and dequeue are O(1).


| Type | Description |
|---|---|
| Simple / Linear queue | Insert at rear, delete at front. Problem: after several deletions the front space is wasted even though the queue looks full |
| Circular queue | The rear wraps around to position 0, reusing the freed space. Solves the wastage problem |
| Deque (Double Ended Queue) | Insertion and deletion allowed at BOTH ends |
| Priority queue | Each element has a priority; the highest-priority element is dequeued first, regardless of arrival order. Usually implemented with a HEAP |



#### Applications of a queue

CPU scheduling (ready queue), disk scheduling, printer spooling, **Breadth First Search (BFS)**, buffering in networks, call-centre hold systems, handling interrupts.


## E3 Non-Linear Data Structures



### E3.1 Trees - the vocabulary


A **tree** is a hierarchical structure with one special node called the **root**, where every other node has exactly one parent and no cycles exist.


| Term | Meaning |
|---|---|
| Root | The topmost node; it has no parent |
| Parent / Child | Directly connected nodes, one level apart |
| Siblings | Nodes sharing the same parent |
| Leaf / Terminal node | A node with NO children |
| Internal node | A node with at least one child |
| Degree of a node | The number of its children |
| Level | Root is at level 0 (some books say 1); children are one level deeper |
| Height / Depth of a tree | The number of edges on the longest path from root to a leaf |
| Subtree | Any node together with all its descendants |
| Forest | A collection of disjoint trees |



### E3.2 Binary trees


A **binary tree** is a tree where every node has **at most two** children (left and right).


| Type | Definition |
|---|---|
| Full / Strictly binary | Every node has either 0 or 2 children - never exactly 1 |
| Complete binary tree | All levels filled except possibly the last, which is filled from LEFT to right |
| Perfect binary tree | All internal nodes have 2 children and all leaves are at the same level |
| Skewed binary tree | Every node has only one child - degenerates into a linked list |
| Balanced tree | The heights of the left and right subtrees differ by at most 1 (AVL condition) |



#### Formulas for binary trees

- **Maximum nodes at level l** - 2^l (with root at level 0).
- **Maximum nodes in a tree of height h** - 2^(h+1) - 1.
- **Minimum height for n nodes** - floor(log2 n).
- **In a full binary tree with n leaves** - there are n - 1 internal nodes, so 2n - 1 nodes in total.
- **Number of edges** - Always n - 1 for a tree with n nodes.


### E3.3 Tree traversals



*The three depth-first traversals*
```
              A
            /   \
           B     C
          / \
         D   E

INORDER    (Left, ROOT, Right)  :  D  B  E  A  C
PREORDER   (ROOT, Left, Right)  :  A  B  D  E  C
POSTORDER  (Left, Right, ROOT)  :  D  E  B  C  A
LEVEL ORDER (breadth first)     :  A  B  C  D  E
```



> **TIP: How to never mix them up**
>
> The word tells you where the **ROOT** goes.
> **PRE**order - root comes **before** the children (first).
> **IN**order - root comes **in between** the two subtrees.
> **POST**order - root comes **after** the children (last).
> In every case, LEFT is always visited before RIGHT.


- **Key fact** - **Inorder traversal of a Binary Search Tree gives the elements in sorted ascending order.** This is asked often.
- **Level order** - Uses a QUEUE. All depth-first traversals use a STACK (or recursion).


### E3.4 Binary Search Tree (BST)


A BST is a binary tree with an ordering rule: for every node, **everything in the left subtree is smaller** and **everything in the right subtree is larger**.


| Operation | Average | Worst |
|---|---|---|
| Search | O(log n) | O(n) - when the tree is skewed |
| Insert | O(log n) | O(n) |
| Delete | O(log n) | O(n) |


The worst case O(n) happens when keys are inserted in sorted order, making the tree a straight line. **Self-balancing trees** fix this.


| Balanced tree | Balancing rule |
|---|---|
| AVL tree | For every node, the balance factor (height of left minus height of right) must be -1, 0 or +1. Rebalanced by rotations (LL, RR, LR, RL). Strictly balanced, so lookups are fastest |
| Red-Black tree | Nodes coloured red or black with rules on paths. Less strictly balanced than AVL, so insert/delete are faster. Used in Java TreeMap and C++ std::map |
| B-tree | A multi-way balanced search tree where a node can hold many keys. Designed for DISK storage - minimises disk reads. Used in databases and file systems |
| B+ tree | A B-tree where all actual data sits in the leaves and the leaves are linked - excellent for range queries. THE standard database index structure |



### E3.5 Heaps


A **heap** is a complete binary tree satisfying the heap property.

- **Max heap** - Every parent is greater than or equal to its children. The **largest** element is at the root.
- **Min heap** - Every parent is less than or equal to its children. The **smallest** element is at the root.
- **Array representation** - For a node at index i (0-based): left child = 2i+1, right child = 2i+2, parent = (i-1)/2.


| Operation | Complexity |
|---|---|
| Find min / max (the root) | O(1) |
| Insert | O(log n) |
| Delete the root (extract min/max) | O(log n) |
| Build a heap from n elements | O(n) |
| Heap sort | O(n log n) |


Heaps are used to implement **priority queues**, for **heap sort**, and for finding the k largest/smallest elements.


### E3.6 Graphs


A **graph** G = (V, E) is a set of **vertices** V connected by **edges** E. Unlike a tree, a graph may have cycles and need not be connected.


| Term | Meaning |
|---|---|
| Directed graph (digraph) | Edges have a direction (one-way streets) |
| Undirected graph | Edges have no direction |
| Weighted graph | Each edge carries a cost or distance |
| Degree | Number of edges touching a vertex. In a digraph: in-degree and out-degree |
| Path | A sequence of vertices connected by edges |
| Cycle | A path that starts and ends at the same vertex |
| Connected graph | Every vertex is reachable from every other |
| Complete graph | Every pair of vertices is joined. It has n(n-1)/2 edges |
| Tree | A connected ACYCLIC graph with n-1 edges |
| DAG | Directed Acyclic Graph - a digraph with no cycles. Used for task scheduling and topological sorting |
| Bipartite graph | Vertices split into two sets with edges only between the sets |
| Articulation point (cut vertex) | A vertex whose REMOVAL disconnects the graph or increases the number of connected components |
| Bridge (cut edge) | An edge whose removal disconnects the graph |



#### Graph representations


| Representation | Space | Check if edge (u,v) exists | Find all neighbours of u |
|---|---|---|---|
| Adjacency matrix | O(V^2) | O(1) - fast | O(V) |
| Adjacency list | O(V + E) | O(degree) | O(degree) - fast |


Use an adjacency **matrix** for dense graphs, an adjacency **list** for sparse graphs.


#### Graph traversals


| Traversal | Data structure used | Complexity | Notes |
|---|---|---|---|
| BFS (Breadth First Search) | QUEUE | O(V + E) | Explores level by level. Finds the SHORTEST PATH in an unweighted graph |
| DFS (Depth First Search) | STACK (or recursion) | O(V + E) | Goes as deep as possible before backtracking. Used for cycle detection, topological sort, finding connected components and articulation points |



> **NOTE: PYQ worked out - articulation points**
>
> One paper showed a graph and asked "What are the articulation points in the above graph?" The answer was **2, 3 and 5**.
>
> Method to solve such a question by hand: **remove one vertex at a time and see whether the graph falls apart.**
>
> In that figure the structure was roughly: 4 and 1 attach to 3 and 2; 10 and 9 hang off 3; 2 links to 3 and to 5; 5 links to 6 and to 7/8.
>
> - Remove **3**: vertices 10 and 9 lose their only connection - they become isolated. So 3 IS an articulation point.
> - Remove **2**: the left cluster (1, 3, 4, 9, 10) gets cut off from the right cluster (5, 6, 7, 8). So 2 IS an articulation point.
> - Remove **5**: vertex 6 loses its only link. So 5 IS an articulation point.
> - Remove **1** or **4**: the rest of the graph stays connected through 2 and 3, so they are NOT articulation points.
>
> Shortcut intuition: **a leaf can never be an articulation point**, and a vertex that is the *only* gateway to some part of the graph always is.



> **NOTE: PYQ worked out - degrees in a path graph**
>
> "In a path-graph having n vertices, where n > 2, ______ is the number of vertices with degree 2." Answer: **n - 2**.
>
> Reasoning. A path graph is a simple straight line: v1 - v2 - v3 - ... - vn.
> The **two end vertices** (v1 and vn) each touch only one edge, so their degree is **1**.
> **Every other vertex** in the middle touches two edges - one on each side - so its degree is **2**.
> Number of middle vertices = n - 2.
>
> Check with n = 5: v1-v2-v3-v4-v5. Degrees are 1, 2, 2, 2, 1. Vertices with degree 2 = 3 = 5 - 2. Correct.



#### Important graph algorithms


| Algorithm | Purpose | Technique | Complexity |
|---|---|---|---|
| Dijkstra | Single-source shortest path, NO negative weights | Greedy | O(V^2) or O(E log V) with a heap |
| Bellman-Ford | Single-source shortest path, HANDLES negative weights, detects negative cycles | Dynamic programming | O(VE) |
| Floyd-Warshall | ALL PAIRS shortest path | DYNAMIC PROGRAMMING (not divide and conquer) | O(V^3) |
| Prim | Minimum Spanning Tree, grows one tree | Greedy | O(E log V) |
| Kruskal | Minimum Spanning Tree, picks cheapest edges globally, uses Union-Find | Greedy | O(E log E) |
| Topological sort | Linear ordering of a DAG | DFS or Kahn's algorithm | O(V + E) |


- **Minimum Spanning Tree (MST)** - A subset of edges connecting all vertices with the minimum total weight and no cycles. It always has exactly V - 1 edges.


## E4 Searching and Sorting



### E4.1 Searching



| Algorithm | Requirement | Best | Average | Worst |
|---|---|---|---|---|
| Linear / Sequential search | None | O(1) | O(n) | O(n) |
| Binary search | Array must be SORTED | O(1) | O(log n) | O(log n) |
| Jump search | Sorted | - | O(sqrt n) | O(sqrt n) |
| Interpolation search | Sorted AND uniformly distributed | O(1) | O(log log n) | O(n) |
| Hashing | Good hash function | O(1) | O(1) | O(n) |



### E4.2 Sorting - the master table



| Algorithm | Best | Average | Worst | Space | Stable? | In place? |
|---|---|---|---|---|---|---|
| Bubble sort | O(n) with a swap-flag | O(n^2) | O(n^2) | O(1) | Yes | Yes |
| Selection sort | O(n^2) | O(n^2) | O(n^2) | O(1) | No | Yes |
| Insertion sort | O(n) | O(n^2) | O(n^2) | O(1) | Yes | Yes |
| Merge sort | O(n log n) | O(n log n) | O(n log n) | O(n) | Yes | No |
| Quick sort | O(n log n) | O(n log n) | O(n^2) | O(log n) | No | Yes |
| Heap sort | O(n log n) | O(n log n) | O(n log n) | O(1) | No | Yes |
| Counting sort | O(n + k) | O(n + k) | O(n + k) | O(k) | Yes | No |
| Radix sort | O(d(n + k)) | O(d(n + k)) | O(d(n + k)) | O(n + k) | Yes | No |
| Bucket sort | O(n + k) | O(n + k) | O(n^2) | O(n) | Yes | No |
| Shell sort | O(n log n) | depends on gap | O(n^2) | O(1) | No | Yes |


- **Stable sort** - Equal elements keep their original relative order. Stable: bubble, insertion, merge, counting, radix. Unstable: selection, quick, heap.
- **In-place sort** - Uses only O(1) or O(log n) extra memory.
- **Comparison-based lower bound** - No comparison sort can do better than **O(n log n)** in the worst case. Counting/radix/bucket beat this only because they do not compare - they use the values themselves.


> **NOTE: PYQ worked out - selection sort**
>
> "What is the best case and worst-case complexity of selection sort?" Answer: **O(n^2)** for both.
>
> Why selection sort has no good case: it works by scanning the entire unsorted portion to find the minimum, then swapping it into place. That scan happens regardless of whether the data is already sorted. The comparisons are always (n-1) + (n-2) + ... + 1 = n(n-1)/2, which is O(n^2) no matter what the input looks like.
>
> Contrast with **bubble sort** and **insertion sort**, which DO have a best case of O(n) on already-sorted data, because they can detect that no swaps are needed.



> **NOTE: PYQ worked out - merge sort average case**
>
> "What is the average case time complexity of merge sort?" Answer: **O(n log n)**.
>
> Merge sort is beautifully predictable: best, average and worst are **all O(n log n)**, because it always splits exactly in half regardless of the data. The `log n` comes from the number of times you can halve n; the `n` comes from the merging work at each level.
>
> Its one weakness is **space**: it needs O(n) extra memory for the temporary arrays, so it is **not in-place**.



> **NOTE: PYQ worked out - sorting a linked list**
>
> "Which sorting technique is best for sorting a linked list with n elements?" Answer: **Merge sort**.
>
> This is a genuinely important insight. Quick sort is usually the fastest sort for arrays, but it depends on **random access** to pick and reach the pivot - and a linked list has no random access (reaching the middle costs O(n)). Merge sort, by contrast, only ever needs to **traverse sequentially and relink pointers**. Two extra bonuses for linked lists: merge sort needs no extra array (you just rearrange the existing pointers, so it becomes O(1) auxiliary space), and it is stable.
>
> Insertion, bubble and selection sort are all O(n^2) and therefore worse for large n.



### E4.3 How each sort actually works


- **Bubble sort** - Repeatedly compare adjacent pairs and swap if out of order. After each pass the largest remaining element "bubbles" to the end.
- **Selection sort** - Find the smallest element in the unsorted part and swap it into the front. Makes the **fewest swaps** (n-1) of any algorithm.
- **Insertion sort** - Take the next element and insert it into its correct place among the already-sorted elements on the left. Excellent for **small or nearly sorted** data. This is how people sort playing cards in their hand.
- **Merge sort** - Divide the array into halves recursively until single elements remain, then **merge** sorted halves together.
- **Quick sort** - Pick a **pivot**, partition the array so smaller elements go left and larger go right, then recurse on both sides. Worst case O(n^2) happens when the pivot is always the smallest or largest element (e.g. already-sorted data with a first-element pivot). Cured by choosing a random or median pivot.
- **Heap sort** - Build a max heap, then repeatedly swap the root to the end and re-heapify.


## E5 Algorithm Design Techniques



### E5.1 Divide and Conquer


Three steps: **Divide** the problem into smaller independent subproblems, **Conquer** each recursively, **Combine** the results.


#### Applications of divide and conquer

- **Binary search**
- **Merge sort**
- **Quick sort**
- **Strassen's matrix multiplication**
- Closest pair of points
- Maximum subarray
- Karatsuba fast multiplication
- Tower of Hanoi
- Finding maximum and minimum together


> **NOTE: Two PYQs on divide and conquer**
>
> "Which of the following algorithm design techniques is used in the merge sort algorithm?" Answer: **Divide and conquer**. Merge sort literally divides the array in half, sorts each half, and combines.
>
> "Which of the following is NOT the application of Divide and Conquer?" Options: Binary Search, **All Pairs Shortest Path Problem**, Quick Sort, Strassen's Matrix Multiplication. Answer: **All Pairs Shortest Path Problem**.
>
> Why: all-pairs shortest path is solved by the **Floyd-Warshall** algorithm, which is **dynamic programming** - it builds up a table of solutions where subproblems **overlap** and are reused. Divide and conquer requires **independent** subproblems. That overlap is the exact dividing line between the two techniques.



### E5.2 The five techniques compared



| Technique | Core idea | Classic examples |
|---|---|---|
| Divide and Conquer | Split into INDEPENDENT subproblems, solve recursively, combine | Merge sort, quick sort, binary search, Strassen |
| Greedy | At each step take the choice that looks best RIGHT NOW, never reconsider | Dijkstra, Prim, Kruskal, Huffman coding, fractional knapsack, activity selection, job sequencing |
| Dynamic Programming | Subproblems OVERLAP; store each answer once (memoisation / tabulation) and reuse | Floyd-Warshall, Bellman-Ford, 0/1 knapsack, longest common subsequence, matrix chain multiplication, Fibonacci |
| Backtracking | Build a solution incrementally and ABANDON a partial solution as soon as it cannot work | N-Queens, Sudoku, SUM OF SUBSETS, graph colouring, Hamiltonian cycle, maze solving |
| Branch and Bound | Like backtracking but for OPTIMISATION, using bounds to prune | Travelling Salesman, 0/1 knapsack (optimisation version) |



> **TIP: Greedy vs Dynamic Programming - the one-line test**
>
> Greedy makes **one** choice and never looks back, so it is fast but not always optimal. Dynamic programming **tries all** relevant choices and keeps the best, so it is slower but guaranteed optimal when the problem has optimal substructure.
>
> Classic exam contrast: the **fractional** knapsack is solved greedily; the **0/1** knapsack needs dynamic programming.



### E5.3 Backtracking - the sum of subsets problem



> **NOTE: PYQ worked out**
>
> "What are the solutions for the following sum of a subset problem? w[1:5] = {2, 7, 8, 9, 15}; Sum required = 17. 1 means the item is included, 0 means excluded."
>
> Answer: **11100; 10001; 00110**
>
> Verify each candidate by mapping the bits onto the weights {2, 7, 8, 9, 15}:
>
> **11100** to include 2, 7, 8 to 2 + 7 + 8 = **17** - correct
> **10001** to include 2 and 15 to 2 + 15 = **17** - correct
> **00110** to include 8 and 9 to 8 + 9 = **17** - correct
>
> Now check the wrong options. **10101** would be 2 + 8 + 15 = 25 (not 17). **11000** would be 2 + 7 = 9. **00111** would be 8 + 9 + 15 = 32.
>
> Method for the exam: do not try to run the backtracking tree. Just **add up the weights indicated by each bit string** and keep the option where every string totals the target.



## E6 Hashing



### E6.1 The idea


Searching an array takes O(n); searching a sorted array takes O(log n). **Hashing** aims for **O(1)** - go straight to the item with no searching at all.

A **hash function** converts a key into an array index.


*Simple division-method hash*
```
   index = key MOD table_size

   key = 127, table_size = 10  ->  index = 127 % 10 = 7
   Store the record at position 7. To find it later, recompute 7. Done - O(1).
```


- **Hash table** - The array that holds the records.
- **Hash function** - The mapping from key to index. A good one distributes keys uniformly and is fast to compute.
- **Collision** - Two different keys hash to the same index. Unavoidable in general (pigeonhole principle).
- **Load factor** - Number of stored elements divided by table size. Performance degrades as it approaches 1.


### E6.2 Collision resolution



| Method | How it works |
|---|---|
| Separate chaining (open hashing) | Each slot holds a LINKED LIST of all keys hashing there. Simple; the table never "fills up" |
| Open addressing (closed hashing) | All records live inside the table itself; on collision, probe for another free slot |
| -- Linear probing | Try index+1, index+2, ... Suffers PRIMARY CLUSTERING (long runs form) |
| -- Quadratic probing | Try index+1^2, index+2^2, ... Reduces primary clustering; suffers secondary clustering |
| -- Double hashing | Use a second hash function to decide the step size. Best distribution |



| Operation | Average case | Worst case |
|---|---|---|
| Search | O(1) | O(n) - when all keys collide into one slot |
| Insert | O(1) | O(n) |
| Delete | O(1) | O(n) |



### E6.3 Where hashing appears in the syllabus

- **Hashtable / HashMap** collection classes (accessing an element by a unique key).
- Database **indexing** and hash joins.
- **Cache** tag lookup and TLBs.
- Password storage (with cryptographic hashes such as SHA-256 - see Part G).
- Compiler **symbol tables**.
- Removing duplicates and counting frequencies.



---

# PART F - Database Management Systems and SQL

> *Definitions, keys, normalisation, SQL syntax and transactions. Five to eight marks every year, and almost all of it is memorisable.*



## F1 Database Fundamentals



### F1.1 Why databases replaced files


Imagine a school storing student records in separate notebooks - one with the admissions clerk, one with the fee counter, one with the class teacher. Change a student's address and you must find and correct three notebooks. Miss one and the school now holds two different addresses for the same child.

That is exactly what happened with file-based systems, and it is why databases exist.

- **Data** - Raw facts.
- **Database** - An **organised collection of related data**, stored so it can be easily accessed, managed and updated.
- **DBMS** - **Database Management System** - the software that lets users define, create, store, retrieve, update and control access to a database. Examples: MySQL, Oracle, PostgreSQL, SQL Server, MS Access, MongoDB.
- **Database system** - The database plus the DBMS plus the application programs.


#### Problems with the old file system


| Problem | Meaning |
|---|---|
| Data redundancy | The same data stored in many places |
| Data inconsistency | Copies disagree with each other after an update |
| Difficulty of access | A new query needs a new program to be written |
| Data isolation | Data scattered in different files and formats |
| Integrity problems | Rules (like "marks must be 0-100") get buried inside program code |
| Atomicity problems | A half-finished update can leave the data corrupted |
| Concurrent access anomalies | Two users updating at once corrupt each other's work |
| Security problems | Hard to give each user access to only part of the data |



#### Advantages of a DBMS

Controls redundancy, enforces consistency and integrity constraints, allows data sharing, provides security and authorisation, supports backup and recovery, provides multiple views of the same data, enforces standards, and gives **data independence**.

- **Data independence** - The ability to change one level of the schema without disturbing the level above. **Logical data independence** - change the logical schema without changing applications. **Physical data independence** - change how data is stored without changing the logical schema. Physical independence is easier to achieve.


### F1.2 The three-schema architecture



*Three levels of abstraction*
```
   +------------------------------------------------+
   |  EXTERNAL / VIEW LEVEL                         |  What each USER sees
   |  Many different views for different users       |  (subschemas, views)
   +------------------------------------------------+
                        |  logical data independence
   +------------------------------------------------+
   |  CONCEPTUAL / LOGICAL LEVEL                    |  WHAT data is stored
   |  The whole database structure, tables,          |  and what the
   |  relationships, constraints                     |  relationships are
   +------------------------------------------------+
                        |  physical data independence
   +------------------------------------------------+
   |  INTERNAL / PHYSICAL LEVEL                     |  HOW the data is
   |  Files, indexes, blocks, compression            |  actually stored
   +------------------------------------------------+
```



### F1.3 Schema vs instance - a favourite question


- **Schema** - The **overall DESIGN / structure** of the database - the tables, their columns and their data types. It is defined once and rarely changes. Think of it as the empty printed form.
- **Instance** - The **actual data** in the database at a particular moment. It changes constantly with every insert, update and delete. Think of it as one filled-in form.
- **Metadata** - Data about the data - the schema itself, stored in the **data dictionary / system catalog**.


> **NOTE: Direct PYQ**
>
> "What is the overall design of a database called?" Options: **Database Schema**, Database Instance, Database Table, Database Model. Answer: **Database Schema**.
>
> Learn the analogy: **schema is to instance as a class is to an object**, or as a variable's *type* is to its *value*. A "Database Model" is the general approach (relational, hierarchical); a "Table" is just one component.



### F1.4 Database models



| Model | Structure | Notes |
|---|---|---|
| Hierarchical | A tree; each child has exactly ONE parent | Oldest. IBM IMS. Cannot represent many-to-many naturally |
| Network | A graph; a child may have MANY parents | More flexible than hierarchical; complex pointers |
| RELATIONAL | Data stored in TABLES (relations) of rows and columns | Proposed by E. F. CODD in 1970. The dominant model. Uses SQL |
| Object-oriented | Data stored as objects with methods | Good for complex data |
| Object-relational | Relational plus object features | Oracle, PostgreSQL |
| NoSQL: document / key-value / column / graph | Schema-flexible, horizontally scalable | MongoDB, Redis, Cassandra, Neo4j |



> **NOTE: Direct PYQ**
>
> "What makes a database relational?" Options: **Tables**, Field, Records, Tuple. Answer: **Tables**.
>
> The defining feature of the relational model is that all data is organised into **tables (relations)**. Fields, records and tuples are the *parts* of a table, not the thing that makes the database relational. In fact "record" and "tuple" both mean a row - so they cannot be the distinguishing answer.



### F1.5 Relational model terminology



| Formal term | Everyday term | Meaning |
|---|---|---|
| Relation | Table | A two-dimensional structure of rows and columns |
| Tuple | Row / Record | One entity occurrence |
| Attribute | Column / Field | One property of the entity |
| Degree | - | The NUMBER OF COLUMNS (attributes) in a relation |
| Cardinality | - | The NUMBER OF ROWS (tuples) in a relation |
| Domain | - | The set of permitted values for an attribute |
| Relation schema | - | The table name plus its attribute list |
| NULL | - | An unknown, missing or inapplicable value. NOT the same as zero or an empty string |



> **TIP: Degree vs Cardinality**
>
> **Degree = columns. Cardinality = rows.** A memory hook: "**D**egree for **D**escriptions (columns describe), **C**ardinality for **C**ount of records."



### F1.6 Keys



| Key | Definition |
|---|---|
| Super key | ANY set of attributes that uniquely identifies a tuple. May contain extra useless attributes |
| Candidate key | A MINIMAL super key - remove any attribute and it stops being unique. A table may have several candidate keys |
| PRIMARY key | The one candidate key chosen by the designer to identify rows. It CANNOT be NULL and must be unique. Only one per table |
| Alternate key | The candidate keys that were not chosen as primary |
| Composite key | A key made of TWO OR MORE attributes together |
| FOREIGN key | An attribute in one table that refers to the PRIMARY key of another table. It enforces referential integrity and MAY be NULL |
| Surrogate key | An artificial key with no business meaning, e.g. an auto-increment ID |
| Secondary key | A non-unique attribute used only for retrieval, e.g. city |



#### Integrity constraints

- **Domain constraint** - Every value must come from the attribute's declared domain / data type.
- **Entity integrity** - The primary key can never be NULL and must be unique.
- **Referential integrity** - A foreign key value must either match an existing primary key value in the referenced table, or be NULL.
- **Key constraint** - No two tuples may have the same primary key value.
- **NOT NULL, UNIQUE, CHECK, DEFAULT** - Column-level constraints enforced by the DBMS.

- **ON DELETE CASCADE** - If the referenced row is deleted, the referring rows are deleted too.
- **ON DELETE SET NULL** - The foreign key is set to NULL instead.
- **ON DELETE RESTRICT / NO ACTION** - The deletion is refused.


## F2 The ER Model



### F2.1 Building blocks


The **Entity Relationship model** is a diagram used to design a database before any tables are created. It was introduced by **Peter Chen**.


| Element | Symbol | Meaning |
|---|---|---|
| Entity | RECTANGLE | A real-world thing about which we store data: Student, Course |
| Weak entity | DOUBLE rectangle | An entity that cannot be identified without a related "owner" entity. It has no primary key of its own, only a partial key |
| Attribute | ELLIPSE / oval | A property of an entity |
| Key attribute | Ellipse with the name UNDERLINED | The primary key |
| Multivalued attribute | DOUBLE ellipse | Can hold several values, e.g. phone numbers |
| Derived attribute | DASHED ellipse | Computed from other attributes, e.g. Age from DOB |
| Composite attribute | Ellipse connected to sub-ellipses | Made of smaller parts, e.g. Name to First + Last |
| Relationship | DIAMOND | An association between entities: "Student ENROLS IN Course" |
| Identifying relationship | DOUBLE diamond | Links a weak entity to its owner |
| Total participation | DOUBLE line | Every instance MUST participate |
| Partial participation | Single line | Participation is optional |



### F2.2 Cardinality of relationships



| Type | Meaning | Example |
|---|---|---|
| One-to-One (1:1) | One instance relates to at most one | One person has one passport |
| One-to-Many (1:N) | One instance relates to many | One department has many employees |
| Many-to-One (N:1) | The reverse of 1:N | - |
| Many-to-Many (M:N) | Many relate to many. Needs a separate JUNCTION table when converted to relations | Students and Courses |



### F2.3 Descriptive attributes


- **Descriptive attribute** - An attribute attached to a **RELATIONSHIP** rather than to an entity. It **records information about the relationship itself**.

Example: in "Student ENROLS IN Course", the attributes *date of enrolment* and *grade* belong to neither the Student nor the Course - they describe the enrolment. So they are descriptive attributes on the relationship.


> **NOTE: Direct PYQ**
>
> "Descriptive attributes are used to:" Answer: **record the information about relationships.**
>
> Distinguish carefully from the distractors: recording information about *attributes* is meaningless; recording information about *participating entities* is what ordinary entity attributes do. Only descriptive attributes describe the **relationship**.



### F2.4 Generalisation, specialisation, aggregation


- **Generalisation** - BOTTOM-UP. Several similar entities are combined into a higher-level general entity. Car and Truck become Vehicle.
- **Specialisation** - TOP-DOWN. A general entity is split into specialised sub-entities. Employee becomes Engineer, Manager, Clerk.
- **Aggregation** - Treating a whole relationship as a single higher-level entity so it can participate in another relationship.
- **ISA relationship** - The inheritance link between a superclass and a subclass entity, drawn as a triangle.


## F3 Relational Algebra and Normalisation



### F3.1 Relational algebra operators



| Operator | Symbol name | What it does |
|---|---|---|
| SELECT | sigma | Picks ROWS that satisfy a condition (a horizontal subset) |
| PROJECT | pi | Picks COLUMNS (a vertical subset) and removes duplicates |
| UNION | - | All tuples in either relation; duplicates removed. Needs UNION COMPATIBILITY |
| SET DIFFERENCE | minus | Tuples in the first but not the second |
| CARTESIAN PRODUCT | cross | Every row of A paired with every row of B. Result has degree(A)+degree(B) columns and cardinality(A) x cardinality(B) rows |
| RENAME | rho | Renames a relation or attribute |
| JOIN | bowtie | Cartesian product followed by a selection condition |
| INTERSECTION | - | Tuples present in both (derivable from difference) |
| DIVISION | - | Used for "for all" queries |


- **Union compatible** - Two relations have the same number of attributes and matching domains. Required for UNION, INTERSECTION and DIFFERENCE.
- **Basic (primitive) operators** - SELECT, PROJECT, UNION, SET DIFFERENCE, CARTESIAN PRODUCT, RENAME. All others can be derived from these six.


### F3.2 Functional dependencies


- **Functional dependency (FD)** - Written X to Y, it means "X determines Y" - if two tuples agree on X they must agree on Y. Example: RollNo to StudentName.
- **Determinant** - The left side, X.
- **Trivial FD** - X to Y where Y is a subset of X. Always true.
- **Full functional dependency** - Y depends on the whole of X, not on any part of it.
- **Partial dependency** - A non-key attribute depends on only PART of a composite primary key. Removed in 2NF.
- **Transitive dependency** - A to B and B to C, so A to C indirectly. Removed in 3NF.
- **Closure of an attribute set** - Written X+, it is the set of all attributes that can be determined from X.


### F3.3 Armstrong's axioms


These are the **sound and complete** inference rules for functional dependencies.


#### The three primary (fundamental) axioms


| Axiom | Rule |
|---|---|
| Reflexivity | If Y is a subset of X, then X to Y |
| Augmentation | If X to Y, then XZ to YZ (add the same attribute to both sides) |
| Transitivity | If X to Y and Y to Z, then X to Z |



#### The derived (secondary) rules


| Rule | Statement |
|---|---|
| Union / Additivity | If X to Y and X to Z, then X to YZ |
| Decomposition / Projectivity | If X to YZ, then X to Y and X to Z |
| PSEUDO-TRANSITIVITY | If X to Y and WY to Z, then WX to Z |
| Composition | If X to Y and Z to W, then XZ to YW |



> **NOTE: PYQ worked out - a subtle question**
>
> "Which of the following DBMS scenarios will NOT really follow Armstrong's Axiom?" Options: Reflexivity rule, **Pseudo transitivity rule**, Transitivity rule, Armstrong's axioms. Answer: **Pseudo transitivity rule**.
>
> The reasoning: Armstrong's axioms **proper** are exactly three - **Reflexivity, Augmentation and Transitivity**. Union, decomposition, pseudo-transitivity and composition are *derived* rules; they follow FROM the axioms but are not themselves axioms. So among the options, pseudo-transitivity is the one that is not one of Armstrong's axioms.
>
> Remember the three-word list: **Reflexivity, Augmentation, Transitivity.** Anything else named in a question is a derived rule.



### F3.4 Finding a closure - solved



> **NOTE: PYQ worked out**
>
> "Consider the relation R(PQRSTU) with F = {P to RT, Q to S, R to PS, QS to TU}. Find the closure of PQ."
>
> Answer: **PQRSTU** (the whole relation, so PQ is a superkey).
>
> Work it step by step, starting with what you are given and repeatedly applying any FD whose left side you already have:
>
> **Start:** PQ+ = {P, Q}
>
> **Apply P to RT** (we have P) - add R and T. Now {P, Q, R, T}
> **Apply Q to S** (we have Q) - add S. Now {P, Q, R, S, T}
> **Apply R to PS** (we have R) - P and S are already there. No change.
> **Apply QS to TU** (we have both Q and S) - add T (already there) and **U**. Now {P, Q, R, S, T, U}
>
> No further FD adds anything new, so **PQ+ = PQRSTU**.
>
> Method to remember: keep looping through the FD list until one full pass adds nothing.



### F3.5 Normalisation


**Normalisation** is the process of organising tables to reduce redundancy and eliminate update, insert and delete anomalies, by decomposing large tables into smaller related ones.

- **Insertion anomaly** - Cannot add a fact without knowing another unrelated fact.
- **Deletion anomaly** - Deleting one row accidentally destroys other useful information.
- **Update anomaly** - The same fact stored many times must be changed in many places.


| Normal form | Requirement | Removes |
|---|---|---|
| 1NF | Every attribute must be ATOMIC (single valued). No repeating groups, no arrays inside a cell | Multivalued attributes |
| 2NF | Must be in 1NF AND every non-key attribute must depend on the WHOLE primary key | PARTIAL dependencies |
| 3NF | Must be in 2NF AND no non-key attribute may depend on another non-key attribute | TRANSITIVE dependencies |
| BCNF (Boyce-Codd) | For every non-trivial FD X to Y, X must be a SUPER KEY | Anomalies from candidate-key overlaps. Stricter than 3NF |
| 4NF | Must be in BCNF and have no MULTIVALUED dependencies | Multivalued dependencies |
| 5NF (PJNF) | No JOIN dependency other than through candidate keys | Join dependencies |



> **TIP: Remembering the first three forms**
>
> 1NF - **atomic** values.
> 2NF - remove **partial** dependency (only relevant when the key is composite).
> 3NF - remove **transitive** dependency.
> BCNF - every determinant must be a **super key**.
>
> A quick nursery-rhyme style hook: "One is Atomic, Two is Partial, Three is Transitive, BC is Super."


- **Lossless decomposition** - You can rejoin the pieces and get exactly the original table back. Essential.
- **Dependency preserving** - Every original FD can still be checked in one of the decomposed tables. 3NF decomposition can always be both lossless and dependency preserving; **BCNF decomposition may lose dependency preservation.**
- **Denormalisation** - Deliberately reintroducing redundancy to make reads faster - common in data warehouses.


## F4 SQL



### F4.1 The five sub-languages of SQL



| Category | Full form | Commands | Purpose |
|---|---|---|---|
| DDL | Data Definition Language | CREATE, ALTER, DROP, TRUNCATE, RENAME | Defines and changes the STRUCTURE (schema) of tables. Used to define the structure of a relation, delete relations and relate schemas. Auto-committed |
| DML | Data Manipulation Language | SELECT, INSERT, UPDATE, DELETE | Works with the DATA inside tables. (Some books place SELECT in a separate DQL) |
| DCL | Data Control Language | GRANT, REVOKE | Controls permissions |
| TCL | Transaction Control Language | COMMIT, ROLLBACK, SAVEPOINT | Manages transactions |
| DQL | Data Query Language | SELECT | Retrieves data |



> **NOTE: PYQ worked out**
>
> "Which of the following is used to define the structure of a relation as well as delete relations and relate schemas?" Options: Integrity constraint, View, DML, **DDL**. Answer: **DDL (Data Definition Language)**.
>
> Every verb in the question - "define the structure", "delete relations", "relate schemas" - is a **structural** operation, and structure is DDL's job. DML only touches the rows inside an existing structure.



> **TIP: DROP vs DELETE vs TRUNCATE - a guaranteed question somewhere**
>



| Point | DELETE | TRUNCATE | DROP |
|---|---|---|---|
| Type | DML | DDL | DDL |
| Removes | Selected rows (with WHERE) or all rows | ALL rows | The ENTIRE table, structure included |
| WHERE clause | Allowed | Not allowed | Not applicable |
| Rollback | Possible | Not normally possible | Not possible |
| Speed | Slower (logs each row) | Very fast | Fast |
| Structure after | Table remains | Table remains, empty | Table is gone |



### F4.2 Core SQL syntax



*CREATE, INSERT, SELECT, UPDATE, DELETE*
```
CREATE TABLE Student (
    RollNo   INT PRIMARY KEY,
    Name     VARCHAR(50) NOT NULL,
    Marks    INT CHECK (Marks BETWEEN 0 AND 100),
    City     VARCHAR(30) DEFAULT 'Delhi',
    DeptID   INT,
    FOREIGN KEY (DeptID) REFERENCES Department(DeptID)
);

/* full-row insert - values must match column order exactly */
INSERT INTO Student VALUES (1, 'Asha', 88, 'Delhi', 10);

/* column-specific insert - the SAFE and recommended form */
INSERT INTO Student (RollNo, Name, Marks) VALUES (2, 'Ravi', 91);

SELECT Name, Marks FROM Student WHERE Marks > 80 ORDER BY Marks DESC;

UPDATE Student SET Marks = 95 WHERE RollNo = 2;

DELETE FROM Student WHERE Marks < 33;
```



> **NOTE: PYQ worked out - the correct INSERT form**
>
> "Select the correct SQL statement which will correctly insert a new row into the Customer table with only the CustomerID, Name, and Product columns specified, assuming the table allows NULLs for other columns."
>
> Answer: **INSERT INTO Customer (CustomerID, Name, Product) VALUES (101, 'Alice', 'Pen');**
>
> Why each wrong option fails:
> `INSERT Customer SET CustomerID=101, ...` - the SET form is MySQL-specific and is not standard SQL; also "INSERT" without "INTO" is non-standard.
> `INSERT INTO Customer VALUES (101, 'Alice', 'Pen');` - syntactically legal, but this form supplies values for **all** columns in order. Since the table has more columns, it would fail or fill the wrong ones. The question explicitly says only three columns are being specified.
> `INSERT INTO Customer (101, 'Alice', 'Pen');` - completely invalid: the `VALUES` keyword is missing, and a column list cannot contain literal values.
>
> **Rule to memorise:** when inserting into a subset of columns you MUST name the columns and use VALUES.



> **NOTE: Direct PYQ**
>
> "Which SQL statement is used to update data in a table?" Answer: **UPDATE**. `CHANGE` and `MODIFY` are clause keywords used *inside* `ALTER TABLE` (to rename or retype a column), not standalone statements. `SET` is a clause *within* the UPDATE statement, not the statement itself.



### F4.3 Clause execution order



*Written order vs actual execution order*
```
YOU WRITE:                    THE DATABASE EXECUTES:
   SELECT                        1. FROM  /  JOIN
   FROM                          2. WHERE
   WHERE                         3. GROUP BY
   GROUP BY                      4. HAVING
   HAVING                        5. SELECT
   ORDER BY                      6. ORDER BY
   LIMIT                         7. LIMIT
```


- **WHERE vs HAVING** - **WHERE filters individual ROWS before grouping**; it cannot use aggregate functions. **HAVING filters GROUPS after grouping**; it can use aggregate functions. This distinction is asked frequently.


### F4.4 Aggregate functions and NULL



| Function | Purpose | NULL behaviour |
|---|---|---|
| COUNT(*) | Counts all rows | INCLUDES rows with NULLs |
| COUNT(column) | Counts non-NULL values in that column | IGNORES NULLs |
| SUM(col) | Total | Ignores NULLs |
| AVG(col) | Average | Ignores NULLs - so AVG is not SUM/COUNT(*) |
| MAX / MIN | Largest / smallest | Ignores NULLs |



#### NULL handling - the three-valued logic

SQL logic has **three** values: TRUE, FALSE and **UNKNOWN**.


| Expression | Result |
|---|---|
| NULL = NULL | UNKNOWN (not TRUE!) |
| NULL <> NULL | UNKNOWN |
| NULL > 5 , NULL <= NULL | UNKNOWN |
| NULL + 10 | NULL |
| NULL IS NULL | TRUE |
| NULL IS NOT NULL | FALSE |



> **NOTE: PYQ worked out**
>
> "Which of the following SQL expressions evaluates to TRUE, according to SQL-99?"
>
> Answer: **NULL IS NULL returns TRUE.**
>
> Why the others are wrong:
> "NULL <= NULL returns UNKNOWN" - this statement is actually **true as a fact**, but read the question: it asks which *expression evaluates to TRUE*. The expression `NULL <= NULL` evaluates to UNKNOWN, not TRUE.
> "NULL >= NULL returns UNKNOWN" - same situation.
> "NULL IS NULL returns FALSE" - factually wrong; it returns TRUE.
>
> The golden rule: **you can never test a NULL with = or <>. You must use `IS NULL` or `IS NOT NULL`.** That is precisely why the IS NULL operator exists.


- **COALESCE(a, b, c)** - Returns the first non-NULL argument. Used to substitute a default for missing data.
- **IFNULL / NVL** - Two-argument versions of the same idea.


### F4.5 Joins



| Join | What it returns |
|---|---|
| INNER JOIN | Only rows where the condition matches in BOTH tables |
| LEFT (OUTER) JOIN | All rows from the LEFT table plus matches from the right; unmatched right columns are NULL |
| RIGHT (OUTER) JOIN | All rows from the RIGHT table plus matches from the left |
| FULL (OUTER) JOIN | All rows from both tables; NULLs where there is no match |
| CROSS JOIN | Cartesian product - every combination |
| SELF JOIN | A table joined to itself, using aliases. Used for hierarchies like employee-manager |
| NATURAL JOIN | Automatically joins on all columns with the SAME NAME and shows each such column once |
| EQUI JOIN | A join whose condition uses only equality (=) |
| THETA JOIN | A join using any comparison operator (<, >, <=) |



*Join example*
```
SELECT s.Name, d.DeptName
FROM   Student s
INNER JOIN Department d ON s.DeptID = d.DeptID;
```



### F4.6 Views


A **view** is a **virtual table** - a stored SELECT query that behaves like a table. It holds no data of its own; the rows are produced when you query it.


*Creating a view*
```
CREATE VIEW TopStudents AS
    SELECT RollNo, Name, Marks FROM Student WHERE Marks > 80;
```



#### Why views are used

- **Security**: expose only certain columns or rows to certain users, hiding salary or personal data.
- **Simplicity**: hide a complicated multi-table join behind a simple name.
- **Logical data independence**: the underlying tables can change while the view's interface stays the same.


#### Restrictions on views

- **Materialised view** - A view whose result IS physically stored and periodically refreshed. Faster to read, but can be stale.
- **Updatable view** - A view you may INSERT/UPDATE through. Generally it must be based on a single table, include the primary key, and contain no DISTINCT, GROUP BY, aggregate functions, or set operations.


> **NOTE: PYQ worked out**
>
> "__________ is NOT allowed in a SQL:1999 view definition." Options: Use of subqueries, Use of nested queries, Use of aggregate formulas, **Use of ORDER BY clause**. Answer: **Use of ORDER BY clause**.
>
> The reasoning is conceptual and worth understanding. A view is defined to be a **relation**, and a relation is by definition an **unordered set of tuples**. Ordering is a property of a *result presented to a user*, not of a stored relation. So the standard forbids ORDER BY inside a view definition - you apply ORDER BY when you SELECT *from* the view instead.
>
> Subqueries, nested queries and aggregate functions are all perfectly legal in a view definition (they merely make the view read-only).



### F4.7 Indexing


- **Index** - An auxiliary data structure (usually a **B+ tree** or a hash table) that speeds up retrieval on a column, at the cost of extra storage and slower INSERT/UPDATE/DELETE.
- **Primary / Clustered index** - Determines the PHYSICAL ORDER of rows in the table. Only **one** per table. Usually built on the primary key.
- **Secondary / Non-clustered index** - A separate structure pointing to the rows. Many are allowed per table.
- **Dense index** - An index entry for EVERY search-key value.
- **Sparse index** - An index entry for only some values (only possible on a clustered/ordered file).
- **Multilevel index** - An index on the index, to keep lookups shallow.


## F5 Transactions and Concurrency Control



### F5.1 What a transaction is


A **transaction** is a single logical unit of work - a group of operations that must **all** succeed or **all** fail.

The classic example is a bank transfer: debit Rs. 1000 from A, credit Rs. 1000 to B. If the power fails between the two steps, the money has vanished. A transaction guarantees that cannot happen.


### F5.2 ACID properties - the most asked definition set



| Property | Meaning | Ensured by |
|---|---|---|
| Atomicity | ALL or NOTHING. Either every operation completes or none of them do; a partial transaction is rolled back | Transaction manager / recovery manager |
| Consistency | The database moves from one valid state to another valid state; all integrity constraints hold before and after | Application programmer + DBMS constraints |
| Isolation | Concurrent transactions must not interfere; each behaves as if it ran alone | Concurrency control manager |
| Durability | Once a transaction COMMITS, its changes survive permanently, even after a crash or power failure | Recovery manager, write-ahead logging |



### F5.3 Transaction states



*Transaction state diagram*
```
   Active  ---->  Partially Committed  ---->  Committed
     |                    |
     v                    v
   Failed  -------->  Aborted / Terminated  (rolled back)
```


- **COMMIT** - Makes all changes permanent.
- **ROLLBACK** - Undoes all changes since the transaction began (or since a savepoint).
- **SAVEPOINT** - A marker you can roll back to partially.


### F5.4 Concurrency problems


When transactions interleave badly, four classic problems appear.


| Problem | What happens |
|---|---|
| Lost update (Write-Write conflict) | T1 and T2 both read a value and both write it; T2's write overwrites T1's, so T1's update is lost |
| Dirty read (Read-Uncommitted / WR conflict) | T2 reads a value that T1 wrote but has not committed. If T1 then rolls back, T2 has used data that never officially existed |
| Unrepeatable read (RW conflict) | T1 reads the same row twice and gets different values because T2 changed it in between |
| Phantom read | T1 runs the same range query twice and the second time extra rows appear, because T2 inserted them |



### F5.5 Schedules and serialisability


- **Serial schedule** - Transactions run one completely after another. Always correct, but slow.
- **Concurrent schedule** - Operations from different transactions are interleaved. Fast, but may be incorrect.
- **Serialisable schedule** - A concurrent schedule whose final effect is **equivalent to some serial schedule**. This is the correctness criterion.
- **Conflicting operations** - Two operations conflict if they belong to **different transactions**, act on the **same data item**, and **at least one of them is a WRITE**. So read-read never conflicts.
- **Conflict serialisable** - A schedule that can be converted into a serial schedule by swapping only NON-conflicting adjacent operations.
- **Precedence (serialisability) graph** - Draw a node per transaction; draw an edge Ti to Tj for every conflicting pair where Ti's operation comes first. The schedule is **conflict serialisable if and only if this graph has NO CYCLE.**
- **View serialisable** - A weaker, more permissive notion. Every conflict-serialisable schedule is view serialisable, but not the reverse.


> **NOTE: PYQ worked out - testing conflict serialisability**
>
> "Which of the following is a conflict serializable schedule?
> S1: R1(A); R1(B); R2(A); R2(B); W2(B); W1(A)
> S2: R1(A); R2(A); R2(B); W2(B); R1(B); W1(A)"
>
> Answer: **S1 is not conflict serializable but S2 is conflict serializable.**
>
> Method - build the precedence graph. Look only at pairs on the SAME data item from DIFFERENT transactions where at least one is a write.
>
> **Schedule S1.**
> On item A: R1(A) comes before W1(A) - same transaction, ignore. R2(A) appears before W1(A), and R2(A) vs W1(A) is a read-write conflict on A, so we get an edge **T2 to T1**.
> On item B: R1(B) appears before W2(B), a read-write conflict on B, so we get an edge **T1 to T2**.
> We now have T1 to T2 **and** T2 to T1 - a **cycle**. Therefore S1 is **NOT** conflict serialisable.
>
> **Schedule S2.**
> On item A: R2(A) comes before W1(A), giving edge **T2 to T1**.
> On item B: W2(B) comes before R1(B), a write-read conflict, giving edge **T2 to T1** again.
> Every edge points the same way, T2 to T1. **No cycle**, so S2 **IS** conflict serialisable, and it is equivalent to running T2 then T1.
>
> Lesson: draw the graph, then simply look for a cycle. If a cycle exists in either direction, that schedule fails.



### F5.6 Concurrency control protocols



| Lock-based | A transaction must acquire a lock before accessing data. SHARED lock (S) for reading - several allowed at once. EXCLUSIVE lock (X) for writing - only one, and no shared locks alongside |
|---|---|
| Two-Phase Locking (2PL) | GROWING phase: only acquire locks. SHRINKING phase: only release locks. Once you release one lock you may never acquire another. Guarantees serialisability but can deadlock |
| Strict 2PL | All EXCLUSIVE locks are held until commit. Prevents cascading rollbacks |
| Rigorous 2PL | ALL locks held until commit |
| Conservative / Static 2PL | Acquire every lock up front before starting. DEADLOCK FREE, but poor concurrency |
| Timestamp ordering | Each transaction gets a timestamp; conflicts are resolved by timestamp order rather than locks. Deadlock free |
| Optimistic concurrency control | Let transactions run freely, then VALIDATE before commit and abort if there was a conflict. Good when conflicts are rare |
| Multiversion (MVCC) | Keeps multiple versions of each item so readers never block writers. Used by PostgreSQL and Oracle |



### F5.7 Recovery


- **Write-Ahead Logging (WAL)** - The log record must be written to stable storage **before** the actual data change. This is what makes recovery possible.
- **UNDO** - Reverse the changes of uncommitted transactions.
- **REDO** - Reapply the changes of committed transactions whose data had not reached disk.
- **Checkpoint** - A periodic marker recording that everything before it is safely on disk. Recovery need only examine the log after the last checkpoint.
- **Deferred update (NO-UNDO/REDO)** - Changes are written to the database only after commit, so no UNDO is ever needed.
- **Immediate update (UNDO/REDO)** - Changes may be written before commit, so both UNDO and REDO may be needed.
- **Shadow paging** - Keeps a shadow copy of the page table so the old state can be restored instantly.


## F6 Data Warehousing and Big Data Basics



### F6.1 OLTP vs OLAP



| Point | OLTP (Online Transaction Processing) | OLAP (Online Analytical Processing) |
|---|---|---|
| Purpose | Day-to-day operations | Analysis and decision support |
| Operations | Many short INSERT/UPDATE/DELETE | Few complex read-only queries |
| Data | Current, detailed | Historical, summarised |
| Normalisation | Highly normalised (3NF) | Denormalised (star / snowflake schema) |
| Users | Clerks, customers | Analysts, managers |
| Example | Booking a train ticket | "Compare quarterly sales by region for five years" |



### F6.2 Data warehouse terms


- **Data warehouse** - A **subject-oriented, integrated, time-variant and non-volatile** collection of data used to support management decisions (Bill Inmon's definition - learn those four adjectives).
- **Data mart** - A smaller, department-specific subset of a data warehouse.
- **ETL** - **Extract, Transform, Load** - the process of moving data from sources into the warehouse.
- **Fact table** - The central table holding measurable numeric values (sales amount, quantity).
- **Dimension table** - Descriptive context around the facts (time, product, region).
- **Star schema** - One fact table joined to several denormalised dimension tables. Simple and fast.
- **Snowflake schema** - Dimension tables are further normalised into sub-dimensions. Saves space, more joins.
- **Data mining** - Discovering previously unknown patterns and relationships in large data sets. Techniques: classification, clustering, regression, association rule mining (market-basket analysis).
- **Big Data 5 Vs** - **Volume, Velocity, Variety, Veracity, Value.**



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




---

# PART H - Web Technologies, XML, PHP and E-Commerce

> *HTML, CSS, JavaScript, AJAX, XML and e-commerce models. Four to eight marks, and almost entirely syntax recall.*



## H1 How the Web Works



### H1.1 The client-server story


When you type an address in your browser, this is what happens:


*A web request from start to finish*
```
1. You type  www.example.com/page.html  in the BROWSER (the CLIENT).
2. DNS translates "www.example.com" into an IP address.
3. The browser opens a TCP connection to that IP on port 80 (or 443).
4. It sends an HTTP request:   GET /page.html HTTP/1.1
5. The WEB SERVER (Apache, Nginx, IIS) receives the request.
6. If the page is STATIC, the server just returns the file.
   If it is DYNAMIC, the server runs a program (PHP, ASP.NET, servlet),
   which may query a DATABASE, and returns the generated HTML.
7. The server sends an HTTP response:  200 OK  + the HTML.
8. The browser PARSES the HTML, fetches CSS/JS/images, and RENDERS the page.
```


- **Web browser** - The CLIENT program whose primary function is **to display and navigate web pages**. It also acts as the **universal front end** for database applications reached over the internet. Examples: Chrome, Firefox, Edge, Safari.
- **Web server** - Software that stores web content and serves it in response to HTTP requests. Apache, Nginx, IIS, Tomcat.
- **Rendering engine** - The part of the browser that turns HTML and CSS into pixels: Blink (Chrome), Gecko (Firefox), WebKit (Safari).
- **Static web page** - Same content for everyone; a plain file.
- **Dynamic web page** - Content generated at request time, often personalised.
- **Client-side scripting** - Runs in the browser: JavaScript. Fast, no server round trip, but visible to the user.
- **Server-side scripting** - Runs on the server: PHP, ASP.NET, JSP, Node.js, Python. Code is hidden, can access databases.


> **NOTE: Two direct PYQs**
>
> "What is the primary function of a web browser?" Answer: **To display and navigate web pages.** It does not create websites (that needs an editor), does not primarily store data, and does not send email (that needs a mail client).
>
> "______ are a database applications' universal front end that connects to the back end via the internet." Answer: **Web browsers**. The reasoning: whatever the database or platform, the *same* browser can act as the user interface - that universality is the point. A "web server" is the middle tier, and a "web application" is what runs *inside* the browser.



### H1.2 HTTP


- **HTTP** - **HyperText Transfer Protocol** - the application-layer protocol defining how clients and servers exchange web resources. It is **stateless**: each request is independent and the server remembers nothing between requests.


| HTTP method | Purpose |
|---|---|
| GET | Retrieve a resource. Parameters appear in the URL, so they are visible and length-limited. Should not change server state |
| POST | Submit data in the request BODY. Hidden from the URL, no length limit. Used for forms and file uploads |
| PUT | Create or replace a resource |
| DELETE | Remove a resource |
| HEAD | Like GET but returns only the headers |
| PATCH | Partially update a resource |



| Status code | Meaning |
|---|---|
| 1xx | Informational |
| 2xx | Success. 200 OK, 201 Created |
| 3xx | Redirection. 301 Moved Permanently, 304 Not Modified |
| 4xx | CLIENT error. 400 Bad Request, 401 Unauthorised, 403 Forbidden, 404 NOT FOUND |
| 5xx | SERVER error. 500 Internal Server Error, 502 Bad Gateway, 503 Service Unavailable |


- **Cookie** - A small text file the server asks the browser to store, sent back on later requests. This is how a stateless protocol can "remember" a logged-in user.
- **Session** - Server-side storage of user state, usually keyed by a session ID held in a cookie.
- **CGI** - **Common Gateway Interface** - the original standard defining how a web server passes a request to an external program and receives its output. Largely replaced by faster approaches (FastCGI, modules, servlets).


> **NOTE: PYQ worked out - note the answer-key discrepancy**
>
> "________ is the standard that defines how web servers and application programs communicate." Options: JDBC, ODBC, CGI, HTTP. The official key gave **HTTP**.
>
> Strictly speaking, the standard that defines how a **web server** hands a request to an **external application program** is **CGI (Common Gateway Interface)** - that is CGI's textbook definition, word for word. **HTTP** defines how a **browser and a web server** communicate.
>
> For the exam: if the question mentions "web server and application program", the theoretically correct answer is **CGI**; if it mentions "client/browser and web server", it is **HTTP**. This paper chose HTTP, so be alert - read whether the pairing is browser-to-server (HTTP) or server-to-program (CGI).



### H1.3 Database connectivity from applications



| Standard | Full form | Used by |
|---|---|---|
| ODBC | Open Database Connectivity | A language-independent, largely Microsoft/C-based API for connecting to any database through a driver |
| JDBC | Java Database Connectivity | The Java-specific API for the same purpose |
| ADO.NET | - | The .NET data access technology |



> **NOTE: Direct PYQ**
>
> "Communication between an application program and a database server occur via:" Answer: **ODBC OR JDBC**.
>
> Why not the others: an "API" is too general a term; a "web server" serves web pages, not database queries; and "HTTP" is a web transfer protocol, not a database interface. ODBC and JDBC are the actual **driver-based standards** that let application code issue SQL to a database engine.



## H2 HTML



### H2.1 Structure of an HTML document


- **HTML** - **HyperText Markup Language** - the markup language that describes the *structure* of a web page using tags. It is not a programming language.


*The basic skeleton*
```
<!DOCTYPE html>
<html>
  <head>
    <title>Page title shown on the browser tab</title>
    <meta charset="UTF-8">
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>
  <body>
    <h1>A heading</h1>
    <p>A paragraph of text.</p>
  </body>
</html>
```


- **Tag** - A keyword in angle brackets: `<p>`. Most tags come in pairs with a closing tag `</p>`.
- **Empty / void tag** - Has no closing tag: `<br>`, `<hr>`, `<img>`, `<input>`, `<meta>`, `<link>`.
- **Attribute** - Extra information inside the opening tag: `<img src="a.jpg" alt="text">`.
- **Element** - The opening tag, the content and the closing tag together.


### H2.2 Essential tags



| Tag | Purpose |
|---|---|
| h1 to h6 | Headings, h1 largest |
| p | Paragraph |
| br | Line break |
| hr | Horizontal rule |
| b / strong | Bold / semantically important |
| i / em | Italic / emphasis |
| u | Underline |
| sub / sup | Subscript / superscript |
| a | ANCHOR - creates a hyperlink |
| img | Image |
| ul / ol / li | Unordered list / ordered list / list item |
| dl / dt / dd | Definition list, term, description |
| table / tr / th / td | Table, row, header cell, data cell |
| form / input / select / textarea / button | Form controls |
| div | A block-level generic container |
| span | An inline generic container |
| iframe | Embeds another document |



### H2.3 Hyperlinks - the anchor tag



*Creating a link*
```
<a href="https://example.com" target="_blank">Visit Example</a>

  href   = Hypertext REFerence - the DESTINATION URL. This is the
           attribute that actually creates the hyperlink.
  target = where to open it
```



> **NOTE: Direct PYQ**
>
> "Which of the following parameters is used to create a hyperlink in HTML?" Options: Link, url, Path, **Href**. Answer: **Href**.
>
> The `<a>` tag by itself does nothing without `href`. There is no `link`, `url` or `path` attribute on an anchor tag. `href` stands for **Hypertext REFerence**.



#### Values of the target attribute


| Value | Where the linked document opens |
|---|---|
| _self | In the SAME frame / tab (this is the default) |
| _blank | In a NEW window or tab |
| _parent | In the PARENT frame |
| _top | In the FULL BODY of the window - it breaks out of ALL frames and uses the entire window |
| framename | In the named frame |



> **NOTE: PYQ worked out**
>
> "Which of the following opens the linked document in the windows full body among the target values?" Answer: **_top**.
>
> The phrase "**full body of the window**" is the definition of `_top` - it escapes every enclosing frameset and takes over the whole window. Distinguish it from `_parent`, which climbs only ONE level up, and `_blank`, which opens a brand-new window rather than reusing the current one.



### H2.4 Forms



*A simple form*
```
<form action="/submit.php" method="post">
  <input type="text"     name="username" placeholder="Name">
  <input type="password" name="pwd">
  <input type="radio"    name="gender" value="M">     <!-- pick ONE      -->
  <input type="checkbox" name="hobby"  value="music"> <!-- pick MANY     -->
  <select name="city"><option value="dl">Delhi</option></select>
  <textarea name="msg" rows="4"></textarea>
  <input type="submit" value="Send">
</form>
```


- **action** - The URL that will process the submitted data.
- **method** - GET (data in the URL) or POST (data in the body).
- **name** - The key under which each field's value is sent.
- **Radio button vs checkbox** - Radio buttons sharing a name allow only **one** selection; checkboxes allow **many**.


### H2.5 HTML5 additions


- **Semantic tags** - `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`, `figure` - they describe *meaning*, which helps search engines and screen readers.
- **Media tags** - `audio`, `video` - native playback without plugins.
- **canvas** - A drawing surface scripted with JavaScript.
- **svg** - Scalable Vector Graphics.
- **New input types** - email, url, number, range, date, color, search - with built-in validation.
- **Storage** - localStorage (persists) and sessionStorage (cleared when the tab closes).
- **Others** - Geolocation API, Web Workers, WebSockets, Drag and Drop.


## H3 CSS



### H3.1 What CSS does


- **CSS** - **Cascading Style Sheets** - describes how HTML elements should be *presented*: colour, font, spacing, layout. It separates presentation from structure.


*Anatomy of a CSS rule*
```
   selector  {  property : value ;  }

   h1 { color: blue; font-size: 24px; }
   |    |      |
   |    |      +-- declaration
   |    +--------- property and value
   +-------------- selector: which elements this applies to
```



### H3.2 The three ways to apply CSS



| Method | How | Priority |
|---|---|---|
| Inline | A `style` attribute on the element itself: `<p style="color:red">` | HIGHEST |
| Internal / Embedded | A `<style>` block inside `<head>` | Medium |
| EXTERNAL | A separate .css file linked with `<link>` in `<head>` | Lowest, but BEST PRACTICE - one file styles the whole site |



*The correct syntax for external CSS*
```
<link rel="stylesheet" type="text/css" href="style.css">

Break it down:
   <link>     the tag used inside <head> to attach an external resource
   rel        the RELATIONSHIP - here "stylesheet"
   type       the MIME type - "text/css"
   href       the path to the file

COMMON WRONG FORMS SEEN IN EXAMS:
   <style rel="stylesheet" ... >     WRONG - <style> is for INTERNAL CSS
   <style href="style.css"></style>  WRONG - <style> has no href attribute
   <a href="style.css" rel="...">    WRONG - <a> creates a hyperlink
```



> **NOTE: Direct PYQ**
>
> "Which of the following is the syntax to write an external CSS?" Answer: **`<link rel="stylesheet" type="text/css" href="style.css">`**.
>
> The single distinguishing point is the **`<link>`** tag. Anything using `<style>` is internal CSS; anything using `<a>` is a hyperlink. Memorise the full line exactly as written above.



### H3.3 Selectors



| Selector | Syntax | Selects |
|---|---|---|
| Element / Type | `p { }` | All p elements |
| Class | `.warning { }` | All elements with class="warning". Reusable, many per page |
| ID | `#header { }` | The single element with id="header". Must be UNIQUE |
| Universal | `* { }` | Everything |
| Descendant | `div p { }` | Any p inside a div |
| Child | `div > p { }` | Only direct children |
| Grouping | `h1, h2 { }` | Several selectors sharing one rule |
| Attribute | `input[type="text"] { }` | By attribute value |
| Pseudo-class | `a:hover { }` | A state: hover, active, visited, focus, first-child, nth-child |
| Pseudo-element | `p::first-line { }` | A part of an element: first-line, first-letter, before, after |



#### Specificity - which rule wins

From strongest to weakest: **inline style > ID > class / attribute / pseudo-class > element**. The `!important` flag overrides everything. When two rules have equal specificity, the **later** one wins - that is the "cascading" in CSS.


### H3.4 The box model



*Every element is a box*
```
   +-------------------------------------------+
   |               MARGIN                      |  space OUTSIDE the border
   |   +-----------------------------------+   |
   |   |            BORDER                 |   |
   |   |   +---------------------------+   |   |
   |   |   |         PADDING           |   |   |  space INSIDE the border
   |   |   |   +-------------------+   |   |   |
   |   |   |   |     CONTENT       |   |   |   |  width x height
   |   |   |   +-------------------+   |   |   |
   |   |   +---------------------------+   |   |
   |   +-----------------------------------+   |
   +-------------------------------------------+
```


- **Total width** - content width + left/right padding + left/right border + left/right margin (in the default `content-box` model).
- **box-sizing: border-box** - Makes the declared width include padding and border - much easier to reason about.


### H3.5 Display, position and filters



| Property | Values and meaning |
|---|---|
| display | block (full width, new line), inline (flows in text, ignores width/height), inline-block (flows but accepts size), none (removed entirely), flex, grid |
| position | static (default), relative (offset from its normal place), absolute (positioned relative to the nearest positioned ancestor), fixed (relative to the viewport, stays on scroll), sticky |
| float | left, right - takes the element out of normal flow |
| z-index | Stacking order for overlapping positioned elements |



#### CSS filters


*PYQ: making all images black and white*
```
img { filter: grayscale(100%); }

Points to notice:
  - the property is  filter
  - the function is  grayscale  (American spelling, NOT "graycolor")
  - the value is NOT quoted

WRONG FORMS OFFERED IN THE EXAM:
  img { filter: graycolor(100%); }      -> no such function
  img { graycolor(100%); }              -> not a property at all
  img { filter: "grayscale(100%)"; }    -> quotes are invalid here
```



> **NOTE: Direct PYQ**
>
> "How to change all images to black and white (100% grey)?" Answer: **`img { filter: grayscale(100%);}`**
>
> Other useful filter functions worth knowing: `blur(5px)`, `brightness(150%)`, `contrast(200%)`, `invert(100%)`, `opacity(50%)`, `sepia(100%)`, `saturate(0%)`.



## H4 JavaScript, DHTML and AJAX



### H4.1 JavaScript basics


- **JavaScript** - A **client-side** (and now also server-side) scripting language that makes web pages interactive. It is interpreted, dynamically typed and case-sensitive. It has nothing to do with Java despite the name.


*Variables, types and output*
```
var  x = 10;      // function-scoped, old style
let  y = 20;      // block-scoped, modern
const z = 30;     // block-scoped constant

// Data types: Number, String, Boolean, Undefined, Null, Object, Symbol, BigInt

console.log("message");        // writes to the developer console
document.write("text");        // writes directly into the document
alert("popup");                // modal popup box
```



*PYQ traced: a simple if-else*
```
let x = 10;
if (x > 5) {
    console.log("Greater");
} else {
    console.log("Smaller");
}

  x is 10, and 10 > 5 is true, so the if branch runs.
OUTPUT: "Greater"
```



### H4.2 document.write and escape sequences



> **NOTE: PYQ worked out - a genuinely tricky one**
>



*PYQ*
```
<script>
document.write("Hello")
document.write("\nIndia")
</script>

WHAT THE ANSWER KEY SAYS: Hello India

THE REASONING THE EXAMINER WANTS:
  document.write outputs into the HTML document. In HTML, a newline
  character (\n) is NOT rendered as a line break - HTML COLLAPSES all
  whitespace (newlines, tabs, multiple spaces) into a SINGLE SPACE.

  So the \n does not start a new line, but it does not vanish either -
  it becomes one space. Result:  Hello India

  To get a real line break in HTML you must write <br>:
      document.write("Hello<br>India")

REMEMBER THE PRINCIPLE:
  \n works in a console, in an alert box, and in a plain text file.
  \n does NOT create a visible line break in rendered HTML.
```



### H4.3 The DOM and DHTML


- **DOM** - **Document Object Model** - a tree representation of the page that JavaScript can read and modify. Every tag becomes a node.
- **DHTML** - **Dynamic HTML** - not a language, but the *combination* of HTML + CSS + JavaScript + DOM used to change a page after it has loaded, without fetching a new page.


| Task | Code |
|---|---|
| Find an element by id | `document.getElementById("myDiv")` |
| Find by class | `document.getElementsByClassName("box")` |
| Find by tag | `document.getElementsByTagName("p")` |
| Modern query | `document.querySelector(".box")` , `querySelectorAll()` |
| Change the content | `element.innerHTML = "new text"` |
| Change a style | `element.style.backgroundColor = "red"` |
| Change an attribute | `element.setAttribute("src", "b.jpg")` |
| Create an element | `document.createElement("div")` |
| Add to the page | `parent.appendChild(child)` |
| Attach an event | `element.addEventListener("click", myFunction)` |
| Resize the window | `window.resizeTo(800, 600)` |
| Open a new window | `window.open("url")` |
| Redirect | `window.location.href = "url"` |



> **NOTE: Two direct PYQs on DHTML methods**
>
> "Which of the following DHTML methods is used to change the style of an HTML element using CSS dynamically?" Answer: **`element.style.backgroundColor = "red"`**.
>
> Explanation: every DOM element exposes a `style` object whose properties correspond to CSS properties. Note the naming rule - CSS `background-color` (with a hyphen) becomes JavaScript `backgroundColor` (camelCase), because hyphens are not legal in JavaScript identifiers. The distractors are invented: there is no `setCSS()` method; `createElement("style")` makes a new style tag rather than changing an element; and `addEventListener("resize")` merely listens for an event.
>
> "Which of the following DHTML methods is used to control the browser window size, such as resizing it dynamically via JavaScript?" Answer: **`window.resizeTo()`**. There is no `window.setSize()`, `window.changeSize()` or `document.resizeWindow()`. Related genuine methods: `window.resizeBy()` (resize by a relative amount), `window.moveTo()`, `window.scrollTo()`.



#### Common JavaScript events

onclick, ondblclick, onmouseover, onmouseout, onkeydown, onkeyup, onchange, onsubmit, onfocus, onblur, onload, onunload, onresize.


### H4.4 AJAX


- **AJAX** - **Asynchronous JavaScript And XML**. A technique for exchanging small amounts of data with the server **in the background**, so a page can update part of itself **without reloading the whole page**.


#### Why AJAX matters

- **Reduced bandwidth consumption** - it sends and retrieves only the small piece of data that is actually needed, instead of the entire page with all its HTML, CSS and images.
- **Faster, smoother user experience** - no full-page flash.
- **Asynchronous** - the user can keep interacting while the request is in flight.


*How AJAX works*
```
1. A user action fires a JavaScript function.
2. The script creates an XMLHttpRequest (or calls fetch()).
3. The request goes to the server IN THE BACKGROUND.
4. The server responds with a small payload - today usually JSON,
   originally XML.
5. A JavaScript callback updates just the relevant part of the DOM.

The page never reloads. Examples: Google search suggestions, live
cricket scores, infinite scrolling, form validation as you type.
```



> **NOTE: Direct PYQ**
>
> "Which advantage of AJAX helps in reducing bandwidth consumption?" Answer: **AJAX sends and retrieves only small amounts of data from the server.**
>
> The other options are simply false: AJAX does not "use less JavaScript" (it uses more), it does not "only load images", and it certainly does not "increase data transfer" - the whole point is to *decrease* it.


- **Drawbacks of AJAX** - The browser back button and bookmarking break unless handled; content may not be indexed by search engines; it depends on JavaScript being enabled.
- **JSON** - **JavaScript Object Notation** - a lightweight, human-readable data format of key-value pairs. It has largely replaced XML in AJAX because it is smaller and parses natively in JavaScript.


### H4.5 jQuery


- **jQuery** - A JavaScript library that simplifies DOM traversal, event handling, animation and AJAX. Its slogan is "write less, do more". The `$` symbol is the jQuery function.


| jQuery method | Effect |
|---|---|
| $("#id") , $(".class") | Select elements (CSS-style selectors) |
| .hide() , .show() , .toggle() | Visibility |
| .fadeIn() , .fadeOut() , .fadeToggle() | Fading effects |
| .slideDown() , .slideUp() , .slideToggle() | SLIDING effects - slideDown reveals an element by sliding it down |
| .html() , .text() , .val() | Get or set content |
| .css() | Get or set styles |
| .addClass() , .removeClass() | Class manipulation |
| .append() , .prepend() | Insert content |
| .click() , .on() | Event binding |
| $.ajax() , $.get() , $.post() | AJAX requests |



> **NOTE: Direct PYQ**
>
> "Which of the following methods is used to slide down an element?" Options: **slideDown()**, moveBelow(), moveDown(), slideBelow(). Answer: **slideDown()**.
>
> The jQuery sliding family is exactly three methods: `slideDown()`, `slideUp()` and `slideToggle()`. There is no `moveBelow`, `moveDown` or `slideBelow` in jQuery. When in doubt, remember that jQuery effect names come in **Down / Up / Toggle** and **In / Out / Toggle** triplets.



### H4.6 AngularJS directives


- **Directive** - A special attribute starting with `ng-` that tells AngularJS to attach behaviour to a DOM element.


| Directive | Purpose |
|---|---|
| ng-app | Marks the root element of the application |
| ng-init | Initialises application data |
| ng-MODEL | BINDS the value of an HTML control (input, select, textarea) to a property on the application data - two-way DATA BINDING between MODEL and VIEW |
| ng-bind | One-way binding of data into the element's text |
| ng-repeat | Repeats an element once per item in a collection |
| ng-if , ng-show , ng-hide | Conditional rendering / visibility |
| ng-click | Click handler |
| ng-controller | Attaches a controller to the view |



> **NOTE: Direct PYQ**
>
> "Which directive is used for binding the model data to the view?" Options: ng-model-view, ng-model-app, **ng-model**, ng-app-model. Answer: **ng-model**.
>
> `ng-model` provides **two-way data binding**: type in the input and the model updates; change the model in code and the input updates. The other three options are invented names - AngularJS has no `ng-model-view`, `ng-model-app` or `ng-app-model`.



## H5 XML



### H5.1 What XML is and how it differs from HTML


- **XML** - **eXtensible Markup Language** - a language for **storing and transporting data** in a self-describing, platform-independent, text-based format. It does not display anything.


| Point | HTML | XML |
|---|---|---|
| Purpose | To DISPLAY data | To STORE and TRANSPORT data |
| Tags | A fixed, predefined set | You DEFINE YOUR OWN tags - it is extensible |
| Case sensitive | No | YES |
| Closing tags | Some are optional | MANDATORY for every element |
| Attribute quotes | Optional | MANDATORY |
| Whitespace | Collapsed | PRESERVED |
| Root element | Implicit | Exactly ONE root element is required |
| Well-formedness | Browsers tolerate errors | Errors cause a parse failure |



*A well-formed XML document*
```
<?xml version="1.0" encoding="UTF-8"?>
<school>
  <student id="1">
    <name>Asha</name>
    <marks>88</marks>
  </student>
  <student id="2">
    <name>Ravi</name>
    <marks>91</marks>
  </student>
</school>
```


- **Well-formed XML** - Obeys all syntax rules: one root, every tag closed, correct nesting, quoted attributes, case-matched tags.
- **Valid XML** - Well-formed **and** conforms to a DTD or XML Schema.
- **CDATA section** - `<![CDATA[ ... ]]>` - text the parser should not interpret as markup.
- **Entity references** - `&lt;` for <, `&gt;` for >, `&amp;` for &, `&quot;` for ", `&apos;` for '.
- **Namespace** - `xmlns:prefix="URI"` - prevents element-name clashes between vocabularies.


### H5.2 The XML processor and parsers


- **XML processor (XML parser)** - The software component that **READS an XML document and provides access to its content and structure** to an application. It also checks well-formedness.


> **NOTE: Direct PYQ**
>
> "______ reads XML documents and provides access to their content and structure." Options: XML schema, XML pre-processor, **XML processor**, XML codes. Answer: **XML processor**.
>
> Note the distinction: an **XML schema** *describes* what a valid document looks like; it does not read anything. "XML pre-processor" and "XML codes" are not real terms.



| Parser | Type | Characteristics |
|---|---|---|
| DOM | Tree-based | Loads the WHOLE document into memory as a tree. Random access, can modify and write back. Memory-hungry for large files |
| SAX | Event-based | Streams through the document firing events (startElement, endElement, characters). Very memory-efficient, but READ-ONLY and forward-only |
| StAX | Pull-based | The application pulls events as needed |
| JDOM / dom4j | Java tree APIs | Easier Java-friendly alternatives to DOM |



> **NOTE: Direct PYQ**
>
> "Which of the following is NOT an XML Parser?" Options: **Shell**, JDOM, DOM, SAX. Answer: **Shell**.
>
> A **shell** is a command-line interpreter in an operating system (bash, csh, ksh) - it has nothing to do with XML. DOM, SAX and JDOM are all genuine XML parsers/APIs.



### H5.3 DTD and XML Schema


- **DTD** - **Document Type Definition** - the older way to declare the legal structure of an XML document: which elements exist, their order, and their attributes. Written in its own non-XML syntax and has no data types.
- **XSD (XML Schema Definition)** - The modern replacement. Written **in XML itself**, supports **data types** (integer, date, decimal), namespaces, and much richer constraints.


*Internal vs external DTD*
```
INTERNAL DTD - declared inside the document:
   <!DOCTYPE note [
     <!ELEMENT note (to, from, body)>
     <!ELEMENT to   (#PCDATA)>
   ]>

EXTERNAL DTD - kept in a separate file:
   <!DOCTYPE root-element SYSTEM "file-name">

   Break down the external form:
     <!DOCTYPE      the declaration keyword
     root-element   the name of the document's ROOT element - comes FIRST
     SYSTEM         keyword meaning "a private, local file follows"
     "file-name"    the path to the .dtd file, in quotes

   PUBLIC is used instead of SYSTEM for a widely published, standard DTD.
```



> **NOTE: Direct PYQ**
>
> "How to write the external DTD?" Answer: **`<!DOCTYPE root-element SYSTEM "file-name">`**
>
> The **order** is what is being tested. The root element name must come immediately after `<!DOCTYPE`, then `SYSTEM`, then the quoted filename. Every wrong option scrambles that order: `<!DOCTYPE SYSTEM "file-name">` omits the root element; `<!DOCTYPE element ROOT "file-name">` invents a ROOT keyword; `<!DOCTYPE SYSTEM "file-name" root-element>` puts the root element last.



#### Related XML technologies

- **XSL / XSLT** - eXtensible Stylesheet Language Transformations - transforms XML into HTML, text or other XML.
- **XPath** - A syntax for navigating to nodes in an XML document.
- **XQuery** - A query language for XML data.
- **XLink / XPointer** - Linking within and between XML documents.
- **SOAP** - Simple Object Access Protocol - an XML-based messaging protocol for web services.
- **WSDL** - Web Services Description Language - describes a web service in XML.
- **RSS** - An XML format for publishing frequently updated content.


## H6 PHP



### H6.1 PHP basics


- **PHP** - **PHP: Hypertext Preprocessor** (originally Personal Home Page) - an open-source **server-side** scripting language embedded in HTML. The code runs on the server and only the resulting HTML reaches the browser.


*PHP essentials*
```
<?php
  $name = "Asha";              // variables ALWAYS start with $
  $marks = 88;                 // loosely typed - no declaration needed
  echo "Hello $name";          // double quotes INTERPOLATE variables
  echo 'Hello $name';          // single quotes do NOT - prints literally
  $total = $marks + 10;
  echo "<br>" . $total;        // dot (.) is the STRING CONCATENATION operator
?>
```


- **echo vs print** - `echo` can take several arguments and returns nothing; `print` takes one argument and returns 1. `echo` is marginally faster.
- **Superglobals** - `$_GET`, `$_POST`, `$_REQUEST`, `$_SESSION`, `$_COOKIE`, `$_FILES`, `$_SERVER`.
- **include vs require** - Both insert another file. `include` gives a **warning** and continues if the file is missing; `require` gives a **fatal error** and stops. The `_once` variants prevent double inclusion.


### H6.2 PHP arrays and sorting functions



| Array type | Example |
|---|---|
| Indexed | `$a = array("x", "y");` keys are 0, 1 |
| Associative | `$a = array("name" => "Asha", "marks" => 88);` |
| Multidimensional | Arrays inside arrays |


This sorting table is asked directly, so learn the two dimensions: **what is sorted (values or keys)** and **whether the key association survives**.


| Function | Sorts by | Order | Preserves key-value association? |
|---|---|---|---|
| sort() | VALUE | Ascending | NO - keys are reindexed 0,1,2... |
| rsort() | VALUE | Descending | NO - keys are reindexed |
| ASORT() | VALUE | ASCENDING | YES - keys stay attached to their values |
| arsort() | VALUE | Descending | YES |
| ksort() | KEY | Ascending | YES |
| krsort() | KEY | Descending | YES |
| usort() | VALUE, via a user function | Custom | NO |
| uasort() | VALUE, via a user function | Custom | YES |



> **NOTE: Direct PYQ**
>
> "Which of the following PHP functions is used to sort an array in ascending order without affecting the keys?" Options: ksort(), array_sort(), **asort()**, sort(). Answer: **asort()**.
>
> Decode the names and you never need to memorise the table:
> - plain **sort** - sorts values, throws keys away
> - prefix **a** (associative) - keeps the key-value pairing
> - prefix **k** - sorts by key instead of value
> - prefix **r** (reverse) - descending
> - prefix **u** - user-defined comparison
>
> So "ascending, values, keys preserved" = a + sort = **asort()**. Note that `array_sort()` does not exist in PHP at all, and `ksort()` would sort by key rather than value.



#### Other useful PHP functions

count(), array_push(), array_pop(), array_merge(), in_array(), array_keys(), array_values(), implode(), explode(), strlen(), strtoupper(), str_replace(), trim(), substr(), date(), isset(), empty(), unset().


## H7 E-Commerce



### H7.1 What e-commerce is


- **E-commerce** - **Electronic commerce** - buying and selling goods, services and information over electronic networks, principally the internet.
- **E-business** - A broader term including all electronic business processes - supply chain, CRM, internal operations - not just buying and selling.
- **Commerce** - The activity that **primarily deals with buying and selling, particularly on a large scale.** (Distinguish from *trade*, which is narrower, and from *distribution* or *supply chain*, which are logistics functions.)


> **NOTE: Direct PYQ**
>
> "______ primarily deals with buying and selling, particularly on a large scale." Options: **Commerce**, Finance, Supply chain, Distribution. Answer: **Commerce**. Finance deals with money and capital; supply chain and distribution deal with moving goods; only *commerce* is defined by the act of buying and selling at scale.



### H7.2 E-commerce business models



| Model | Meaning | Example |
|---|---|---|
| B2B - Business to Business | One business sells to another | IndiaMART, Alibaba, a manufacturer selling to a wholesaler |
| B2C - Business to Consumer | A business sells directly to the end consumer | Amazon, Flipkart, Myntra |
| C2C - Consumer to Consumer | CONSUMERS SELL TO OTHER CONSUMERS through a third-party platform | OLX, Quikr, eBay, Facebook Marketplace |
| C2B - Consumer to Business | Individuals offer products/services to businesses | Freelancers on Upwork, stock photo contributors, influencers |
| B2G / B2A - Business to Government | Businesses sell to government bodies | GeM (Government e-Marketplace), e-tenders |
| G2C - Government to Citizen | Government provides services to citizens | Income tax e-filing, Passport Seva, DigiLocker |



> **NOTE: Direct PYQ**
>
> "The ______ E-commerce segment(s) is/are represented by OLX." Options: C2C, B2C and B2B / B2B / **C2C** / B2C. Answer: **C2C**.
>
> Reasoning: on OLX an **individual** lists a used phone or a sofa and **another individual** buys it. OLX itself does not own or sell the goods - it merely provides the platform. That is the textbook definition of Consumer-to-Consumer. Compare Amazon, which is primarily B2C because Amazon (or a business seller) sells to consumers.



### H7.3 Revenue models



| Revenue model | How money is made |
|---|---|
| Advertising | Free content funded by ads. Google, Facebook, YouTube |
| SUBSCRIPTION | A FIXED SUM PAID BY CUSTOMERS FOR A SERVICE, typically on a MONTHLY, QUARTERLY OR ANNUAL basis. Netflix, Spotify, newspapers |
| Transaction fee | A commission on each transaction. eBay, Uber, payment gateways |
| Sales | Direct sale of goods or services |
| Affiliate | Earning a referral commission for sending buyers to another site |
| Licensing | Charging for the right to use software or content |
| Freemium | A free basic tier with paid premium features |



> **NOTE: Direct PYQ**
>
> "A fixed sum that is paid by customers for a service, typically on a monthly, quarterly or annual basis, is called ______ in electronic commerce." Options: licensing, affiliate, marketing, **subscription**. Answer: **subscription**.
>
> The trigger words are "**fixed sum**" and "**monthly/quarterly/annual**" - recurring payment for continued access is the definition of a subscription. *Licensing* is a one-time or per-seat right to use; *affiliate* is commission for referrals; *marketing* is not a revenue model at all.



### H7.4 E-commerce infrastructure and payments


- **Payment gateway** - A service that authorises and processes online card/UPI payments securely. Razorpay, PayU, Stripe.
- **Digital wallet / e-wallet** - Stored value on a phone or website. Paytm, PhonePe, Google Pay.
- **UPI** - Unified Payments Interface - India's instant real-time bank-to-bank payment system, built by NPCI.
- **Electronic Data Interchange (EDI)** - The structured, computer-to-computer exchange of standard business documents (purchase orders, invoices) between organisations - a pre-internet forerunner of B2B e-commerce.
- **SSL / HTTPS** - Encrypts the connection so card details cannot be intercepted. The padlock in the address bar.
- **Digital signature and certificate** - Authenticate the parties in an online transaction (see Part G).
- **Cash on Delivery (COD)** - Payment collected at the door - very important in the Indian market.
- **M-commerce** - Commerce conducted through mobile devices.
- **Web surfing** - **The process of visiting different web sites on the internet** hosted by various companies, organisations, educational institutions, magazines and individuals. (Distinguish from *searching*, which is looking for something specific, and *chatting*.)


> **NOTE: Two more direct PYQs**
>
> "______ is the process of visiting different web sites on the internet hosted by various companies, organisations, educational institutions, magazines, individuals, etc." Answer: **Web surfing**. "Webbing" is not a term; "searching" implies a specific query; "chatting" is real-time messaging.
>
> "Who is the father of e-commerce in India?" Answer: **K Vaitheeswaran** - founder of Fabmart/Indiaplaza, India's first e-commerce venture (1999). Note for contrast: **Michael Aldrich** (a distractor in the same question) is credited with inventing **online shopping / teleshopping worldwide** in 1979 - so he is the father of e-commerce *globally*, not in India. Examiners like to swap these two.



### H7.5 Advantages, limitations and security concerns



| Advantages | Limitations |
|---|---|
| Open 24 x 7, no geographic limits | Cannot physically inspect the product before buying |
| Lower operating cost, no showroom needed | Requires internet access and digital literacy |
| Wider customer reach, global market | Security and privacy fears |
| Easy price comparison for buyers | Delivery delays and shipping costs |
| Personalisation and recommendations | Difficult returns and after-sales service |
| Faster transactions, digital records | Lack of personal touch; trust issues with unknown sellers |


- **Main security requirements** - Confidentiality, integrity, authentication, non-repudiation, availability - exactly the goals covered in Part G.
- **IT Act 2000** - The Indian law giving legal recognition to electronic records and digital signatures, and defining cybercrimes.



---

# PART I - Software Engineering, Computer Graphics and Management Information Systems

> *Three medium-weight topics grouped together. Together they contribute six to twelve marks.*



## I1 Software Engineering Fundamentals



### I1.1 Why software engineering exists


One person can build a doghouse with a hammer and no plan. A hundred people cannot build a skyscraper that way - they need drawings, schedules, inspections and standards.

Software is the same. A 200-line program needs no process. A 200,000-line banking system does. **Software engineering** is the application of a systematic, disciplined, measurable approach to the development, operation and maintenance of software.

- **Software crisis** - The historical realisation that projects were routinely late, over budget, unreliable and unmaintainable - which gave birth to software engineering as a discipline.
- **Software** - Computer programs plus the associated documentation and configuration data.


#### Software characteristics

Software is **developed / engineered**, not manufactured. It does not **wear out**, but it does **deteriorate** through repeated modification. It is **flexible** and largely **custom-built** rather than assembled from existing components.


### I1.2 Functional vs non-functional requirements


- **Functional requirement** - **WHAT the system must DO** - a specific behaviour or feature. "The system shall allow a user to log in with an email and password." These describe the **core work tasks** the system must perform - they are **mandatory**.
- **Non-functional requirement** - **HOW WELL** the system must do it - a quality attribute. Performance, security, usability, reliability, portability, scalability, maintainability, availability. Often called "quality requirements" or "constraints".


> **NOTE: PYQ worked out**
>
> "______ activities are at the very core of project completion work tasks, whereas ______ activities are not mandatory." Answer: **Functional, non-functional**.
>
> The logic: functional requirements define the actual work the software must do - without them the project is not complete at all. Non-functional requirements describe desirable qualities; a system can technically function (though badly) without meeting them, so in this framing they are "not mandatory".
>
> Note the distractor "Framework, umbrella". In Pressman's model, **umbrella activities** are the ones that run *across* the whole process - project tracking, risk management, quality assurance, configuration management, measurement - while **framework activities** are the main phases (communication, planning, modelling, construction, deployment). Do not confuse the two pairs.



### I1.3 Levels of design



| Design level | Abstraction | What it produces |
|---|---|---|
| SYSTEM design | HIGHEST abstraction | A high-level view of the complete system as a whole - the overall concept, inputs, outputs and major components |
| ARCHITECTURAL design | Middle | Breaks the concept into LESS-ABSTRACTED sub-systems and defines the relationships between them |
| DETAILED design | LOWEST abstraction | Shows the IMPLEMENTATION at MODULE LEVEL - algorithms, data structures, interfaces of each module |



> **NOTE: PYQ worked out**
>
> "The ______ design is high-abstraction version of a system that is followed by ______ design that breaks the concept into less-abstracted view of sub-systems and later the ______ design showcases the implementation at module-level."
>
> Answer: **system, architectural, detailed.**
>
> The sequence always runs from most abstract to most concrete: **System to Architectural to Detailed**. A memory hook: you first picture the whole *system*, then draw its *architecture*, then fill in the *details*.



### I1.4 Coupling and cohesion - a guaranteed question


These two words are the heart of good software design, and examiners love them because students mix them up.

- **Coupling** - The degree of **interdependence BETWEEN different modules**. How much one module needs to know about another.
- **Cohesion** - The degree to which the elements **INSIDE a single module** belong together and work toward one single purpose.

**The design rule: coupling should be LOW, cohesion should be HIGH.**

Analogy: think of school departments. **Low coupling** means the science department can change its lab timetable without the music department needing to be informed. **High cohesion** means everything inside the science department genuinely relates to science - not a random mix of science, accounts and sports.


> **NOTE: PYQ worked out**
>
> "In building software, ______ should preferably be lower and ______ is preferred to be on the higher side." Answer: **coupling among components, cohesion in bonding components**.
>
> Why low coupling and high cohesion are good: low coupling means a change in one module does not ripple through the system, so maintenance is easier and modules can be tested and reused independently. High cohesion means each module has a single, clear responsibility, which makes it understandable and reliable.
>
> Watch the distractors in that question - "inheritance from parent class" and "aggregation with peer components" are OOP relationship terms, not the design-quality pair the question is asking for.



| Coupling type (worst to best) | Description |
|---|---|
| Content coupling (worst) | One module directly modifies or relies on the internal contents of another |
| Common coupling | Modules share global data |
| External coupling | Modules share an externally imposed format or protocol |
| Control coupling | One module passes a flag that controls the other's logic |
| Stamp coupling | A whole data structure is passed when only part is needed |
| Data coupling (best) | Only the simple parameters actually needed are passed |
| Message coupling | Communication only through public interfaces / messages - loosest of all |



| Cohesion type (best to worst) | Description |
|---|---|
| Functional cohesion (best) | Every element contributes to one single well-defined task |
| Sequential cohesion | Output of one element is input to the next |
| Communicational cohesion | Elements operate on the same data |
| Procedural cohesion | Elements follow a certain sequence of execution |
| Temporal cohesion | Elements are grouped because they happen at the same time (e.g. all start-up code) |
| Logical cohesion | Elements do similar kinds of things, selected by a flag |
| Coincidental cohesion (worst) | Elements are grouped for no meaningful reason at all |



## I2 Software Development Life Cycle Models



### I2.1 The phases common to all models



*The generic SDLC*
```
1. REQUIREMENT gathering and analysis  ->  produces the SRS document
2. SYSTEM DESIGN                       ->  architecture and detailed design
3. IMPLEMENTATION / CODING             ->  source code
4. TESTING                             ->  test reports, defect logs
5. DEPLOYMENT                          ->  the software in live use
6. MAINTENANCE                         ->  fixes and enhancements
```


- **SRS** - **Software Requirement Specification** - the formal document recording all functional and non-functional requirements. It is the contract between customer and developer. A good SRS is correct, complete, consistent, unambiguous, verifiable and traceable.
- **Feasibility study** - Checks technical, economic, legal, operational and schedule viability before committing.


### I2.2 The Waterfall model


The oldest and simplest model. Each phase must be **fully completed** before the next begins, and the flow is strictly downward - like water falling over steps.


| Advantages | Disadvantages |
|---|---|
| Simple, easy to understand and manage | VERY RIGID - you cannot go back to a previous phase |
| Clear, well-documented phases with defined deliverables | Requirement changes cannot be accommodated. UNSUITABLE when requirements alter during development |
| Works well when requirements are fixed and clearly understood | Working software appears only very LATE |
| LOW COST for small, well-understood projects | HIGH RISK because problems surface only at the testing stage |
| Easy to schedule and assign responsibilities | No customer feedback until the end; LONG DURATION for large projects |



> **NOTE: PYQ worked out**
>
> "Which of the following is NOT true about the Waterfall model?" Options: Long duration, **High cost**, High-risk involvement, Low cost. Answer: **High cost**.
>
> Reasoning: the waterfall model is generally described as a **low-cost** model - it needs no repeated prototyping, no elaborate risk analysis and minimal customer interaction, so its process overhead is small. Its genuine drawbacks are long duration and high risk. The trap is that the option list contains **both** "High cost" and "Low cost"; you must pick the one that is NOT true, which is High cost.



### I2.3 All the SDLC models compared



| Model | Core idea | Best suited when |
|---|---|---|
| Waterfall (Linear sequential) | Strictly sequential phases, no going back | Requirements are FIXED and fully known upfront |
| V-Model (Verification and Validation) | Each development phase has a matching testing phase, forming a V shape. Testing is planned in parallel with development | Requirements are clear and the system is safety-critical |
| Incremental | The product is built and delivered in successive increments, each adding functionality | The core requirements are clear but the full feature set can evolve |
| Iterative | A rough version is built, then repeatedly refined through cycles | Requirements are expected to be refined over time |
| PROTOTYPE model | A working mock-up is built quickly, shown to the user, and refined based on feedback before real development | Requirements are UNCLEAR or the user cannot articulate them |
| SPIRAL model | Iterative development combined with explicit RISK ANALYSIS in every loop. Four quadrants: planning, risk analysis, engineering, evaluation | LARGE, EXPENSIVE, HIGH-RISK projects |
| RAD (Rapid Application Development) | Very fast development using component reuse, powerful tools and parallel teams | Small-to-medium projects with a tight deadline, modular design and available components |
| AGILE | Short iterations (sprints), continuous customer collaboration, working software over documentation, welcomes changing requirements | Requirements are VOLATILE and the customer is available for continuous feedback |
| Big Bang | Little planning; just start coding | Tiny projects or academic exercises |



> **NOTE: PYQ worked out - which model cannot handle change**
>
> "Within software engineering, which prescriptive model is INCOMPATIBLE with circumstances in which the requirements alter throughout development?" Options: **Linear models**, Evolutionary models, Agile models, Incremental models. Answer: **Linear models**.
>
> Reasoning: "Linear model" is another name for the **Waterfall** approach - each phase is frozen once complete, so a requirement change discovered during coding cannot be fed back into the design. By contrast, evolutionary, agile and incremental models are all specifically designed to absorb changing requirements through repeated cycles and customer feedback.



### I2.4 RAD model phases



| RAD phase | What happens |
|---|---|
| Business modelling | What information flows between business functions |
| Data modelling | The information flow is refined into a set of data objects and their attributes |
| Process modelling | Data objects are transformed to implement the business functions - the processing descriptions |
| Application generation | Automated tools and reusable components build the working software |
| Testing and turnover | New components are tested; already-reused components need less testing |



> **NOTE: PYQ worked out**
>
> "Which of the following is NOT a phase of the RAD model?" Options: **Development modelling**, Business modelling, Process modelling, Data modelling. Answer: **Development modelling**.
>
> The four genuine "modelling" phases in RAD are **Business, Data, Process** and then **Application Generation** followed by **Testing and Turnover**. "Development modelling" is not one of them - it is an invented name. Memory hook: **B**usiness, **D**ata, **P**rocess, **A**pplication, **T**esting.



### I2.5 Agile


- **Agile Manifesto values** - Individuals and interactions over processes and tools; **working software over comprehensive documentation**; customer collaboration over contract negotiation; **responding to change over following a plan**.
- **Sprint** - A short fixed-length iteration, typically 2 to 4 weeks, producing a potentially shippable increment.
- **Scrum** - The most popular agile framework. Roles: **Product Owner** (owns the backlog and priorities), **Scrum Master** (facilitator, removes impediments), **Development Team**.
- **Artefacts** - Product backlog, sprint backlog, increment, burndown chart.
- **Ceremonies** - Sprint planning, daily stand-up (15 minutes), sprint review, sprint retrospective.
- **Extreme Programming (XP)** - Agile practices including pair programming, test-driven development, continuous integration, small releases and refactoring.
- **User story** - A requirement written from the user's point of view: "As a student, I want to see my marks so that I can track my progress."
- **Kanban** - Visualising work on a board and limiting work-in-progress.


### I2.6 Software testing



| Type | Description |
|---|---|
| Unit testing | Testing the smallest individual module in isolation. Usually done by the developer |
| Integration testing | Testing how modules work together. Approaches: big-bang, top-down (needs STUBS), bottom-up (needs DRIVERS), sandwich |
| System testing | Testing the complete integrated system against the requirements |
| Acceptance testing | Testing by the customer to decide whether to accept the product. ALPHA testing is done at the developer's site by internal staff; BETA testing is done at the customer's site by real users |
| Regression testing | Re-running old tests after a change, to make sure nothing that used to work has broken |
| Smoke / Sanity testing | A quick check that the build is stable enough to test properly |
| Performance / Load / Stress testing | Behaviour under expected load, heavy load and beyond breaking point |
| Security testing | Looks for vulnerabilities |
| Usability testing | How easy the software is to use |



| Approach | Also called | Tester knows the internal code? | Focus |
|---|---|---|---|
| Black box testing | Functional testing | NO | Inputs and outputs only. Techniques: equivalence partitioning, boundary value analysis, decision tables, state transition |
| White box testing | Structural / glass box testing | YES | Internal logic, paths, branches. Techniques: statement coverage, branch coverage, path coverage, cyclomatic complexity |
| Grey box testing | - | Partially | A mixture of both |


- **Verification** - "Are we building the product **right**?" Checks conformance to the specification, without executing the code - reviews, walkthroughs, inspections.
- **Validation** - "Are we building the **right** product?" Checks that the software actually meets the user's needs, usually by executing it.
- **Error, Fault, Failure** - An **error** is a human mistake; it introduces a **fault (defect/bug)** into the code; when executed, the fault causes a **failure** - incorrect behaviour.
- **Test case** - A set of inputs, execution conditions and expected results.
- **Cyclomatic complexity** - McCabe's metric: V(G) = E - N + 2, where E is edges and N is nodes of the control flow graph. It equals the number of independent paths, and hence the minimum number of test cases for branch coverage. Also equal to (number of decision points + 1).


### I2.7 CMM - Capability Maturity Model


- **CMM** - **Capability Maturity Model** - a framework developed by the Software Engineering Institute (SEI) at Carnegie Mellon to assess and improve the maturity of an organisation's software process. Its successor is **CMMI** (Capability Maturity Model Integration).


| Level | Name | Characteristics |
|---|---|---|
| 1 | INITIAL | Ad hoc, chaotic. Success depends on individual heroics. No defined process |
| 2 | REPEATABLE (Managed) | Basic project management exists. Costs and schedules are tracked. Earlier successes on similar projects can be repeated |
| 3 | DEFINED | The process is documented and standardised organisation-wide, and tailored per project |
| 4 | MANAGED (Quantitatively Managed) | The process and product quality are MEASURED quantitatively and controlled statistically |
| 5 | OPTIMISING | CONTINUOUS process improvement driven by quantitative feedback and innovation. Defect prevention |



> **NOTE: Direct PYQ**
>
> "CMM stands for:" Options: Cognitive Modularity Model, Capability Modularity Model, Cognitive Measurable Model, **Capability Maturity Model**. Answer: **Capability Maturity Model**.
>
> Both words matter: **Capability** (what the organisation is able to do) and **Maturity** (how disciplined and repeatable its process is). Memory hook for the five levels: **I**nitial, **R**epeatable, **D**efined, **M**anaged, **O**ptimising - "**I R**eally **D**o **M**y **O**wn work."



### I2.8 Project management and estimation


- **COCOMO** - **COnstructive COst MOdel** by Barry Boehm - estimates effort in person-months from the size in KLOC. Three modes: **Organic** (small team, familiar problem), **Semi-detached** (medium), **Embedded** (tight constraints, complex).
- **Function Point analysis** - Estimates size from functionality (inputs, outputs, enquiries, files, interfaces) rather than lines of code, so it is language-independent.
- **LOC / KLOC** - Lines of code / thousands of lines of code.
- **Gantt chart** - A bar chart showing tasks against a calendar timeline.
- **PERT chart** - **Program Evaluation and Review Technique** - a network diagram showing task dependencies, used to compute the **critical path** (the longest path, which determines the minimum project duration).
- **Risk management** - Identify risks, analyse their probability and impact, plan responses, and monitor. Response strategies: **avoid, accept, transfer, mitigate**.
- **Software Configuration Management (SCM)** - Controlling change: version control, baselines, change control board, build management.
- **Software maintenance types** - **Corrective** (fixing faults), **Adaptive** (adjusting to a new environment), **Perfective** (improving performance or maintainability), **Preventive** (reducing future deterioration).


### I2.9 Pseudo-code, algorithms and flowcharts


- **Algorithm** - A finite, ordered set of unambiguous steps to solve a problem. Language-independent, written in plain English.
- **Pseudo-code** - A semi-formal notation that mixes natural language with programming-language structures (IF, WHILE, FOR). Because its structure already mirrors code, it is the **easiest to transform into an actual computer program**.
- **Flowchart** - A **diagrammatic** representation of an algorithm using standard symbols.


> **NOTE: Direct PYQ**
>
> "Which of the following is the easiest to be transformed into a computer program?" Options: **Pseudo-code**, Algorithm, Flowchart, None of the above. Answer: **Pseudo-code**.
>
> Reasoning: pseudo-code already uses programming constructs - loops, conditionals, assignment - written in a code-like layout. Converting it to C or Java is nearly a line-by-line translation. A plain-English algorithm is more abstract, and a flowchart is graphical, so both need more interpretation.



#### Flowchart symbols - asked directly


| Symbol | Meaning |
|---|---|
| Oval / Rounded rectangle (Terminal) | START or STOP |
| Parallelogram | INPUT or OUTPUT (read / print) |
| RECTANGLE | PROCESSING - a computation or assignment step |
| DIAMOND / Rhombus | DECISION - a yes/no or true/false branch |
| CIRCLE | CONNECTOR - joins parts of the program / flowchart, especially across pages |
| Arrow / Flow line | Direction of flow |
| Hexagon | Preparation or loop initialisation |
| Cylinder | Storage / database |



> **NOTE: PYQ worked out**
>
> "Program links with other parts of the program in a flowchart are represented by ______." Options: rectangles, **circles**, trapezoids, rhombuses. Answer: **circles**.
>
> Reasoning: the **connector** symbol is a small circle, used to link one part of a flowchart to another - typically when the diagram must break across pages or when several flow lines converge. Rectangles are processing steps, rhombuses (diamonds) are decisions, and trapezoids are sometimes used for manual operations.



## I3 Computer Graphics



### I3.1 Basic concepts


- **Computer graphics** - The creation, storage and manipulation of pictures and drawings using a computer.
- **Pixel** - **Picture element** - the smallest addressable dot on a screen.
- **Resolution** - The number of pixels, e.g. 1920 x 1080.
- **Frame buffer / Refresh buffer** - The area of memory holding the intensity value of every pixel on the screen.
- **Bit depth / Colour depth** - Bits used per pixel. 1 bit = monochrome, 8 bits = 256 colours, 24 bits = true colour.
- **Aspect ratio** - Width divided by height.
- **Raster / Bitmap graphics** - The image is stored as a grid of pixels. Loses quality when enlarged. Formats: BMP, JPEG, PNG, GIF.
- **Vector graphics** - The image is stored as mathematical descriptions of lines and curves. Scales to any size with no quality loss. Formats: SVG, AI, EPS.
- **Rasterisation** - The process of converting vector shapes into pixels for display.
- **Aliasing** - The jagged "staircase" appearance of a diagonal line drawn on a pixel grid. **Anti-aliasing** smooths it by varying pixel intensity.


### I3.2 Line and circle drawing algorithms



| Algorithm | Description |
|---|---|
| DDA (Digital Differential Analyser) | Computes each next point by adding a constant increment. Uses FLOATING POINT arithmetic and rounding, so it is slower and accumulates round-off error |
| BRESENHAM's line algorithm | Uses only INTEGER arithmetic (addition, subtraction and bit shifting) with a decision parameter. Faster and more accurate than DDA. The standard line algorithm |
| Mid-point circle algorithm | Draws a circle using a decision parameter and eight-way symmetry |
| Bresenham's circle algorithm | Integer-only circle drawing |
| Scan-line polygon fill | Fills a polygon by finding the intersections of each horizontal scan line with the polygon edges |
| Boundary fill / Flood fill | Recursively fills an area from a seed point outward |



### I3.3 Clipping


- **Clipping** - Discarding the parts of a picture that lie **outside** a specified region (the clipping window), so only the visible portion is drawn.


| Algorithm | Clips |
|---|---|
| Cohen-Sutherland | LINES. Assigns a 4-bit region code (outcode) to each endpoint and uses bitwise tests to trivially accept or reject |
| LIANG-BARSKY | LINES. Uses a parametric representation of the line and computes entry/exit parameters. More efficient than Cohen-Sutherland because it does fewer intersection calculations |
| Cyrus-Beck | Lines, against any convex polygon window |
| Nicholl-Lee-Nicholl | Lines, fewest intersections of all |
| Sutherland-Hodgman | POLYGONS, against each window edge in turn |
| Weiler-Atherton | Concave polygons |



> **NOTE: Direct PYQ**
>
> "Which of the following is a clipping algorithm?" Options: Simple DDA, **Liang Barsky's algorithm**, Bresenham's algorithm, Mid-point Algorithm. Answer: **Liang Barsky's algorithm**.
>
> The others are all **drawing** (scan-conversion) algorithms: DDA and Bresenham draw lines, and the mid-point algorithm draws circles. Only Liang-Barsky is a clipping algorithm. If Cohen-Sutherland ever appears as an option, it is also a clipping algorithm.



### I3.4 Two-dimensional transformations


**Transformations** change the position, size or orientation of an object. This is exactly the machinery that produces animation.


| Transformation | Effect | Matrix note |
|---|---|---|
| Translation | Moves an object by (tx, ty) without changing its shape | Addition, or a matrix with tx, ty in the last column using homogeneous coordinates |
| Scaling | Changes the size by factors (sx, sy). Uniform if sx = sy | Multiplication by a diagonal matrix |
| Rotation | Rotates by an angle about a point | Uses sin and cos |
| Reflection | Produces a mirror image about an axis or line | Scaling with negative factors |
| Shearing | Slants the shape; a rectangle becomes a parallelogram | Off-diagonal terms |


- **Homogeneous coordinates** - A point (x, y) is written as (x, y, 1) so that **translation also becomes a matrix multiplication**. This lets several transformations be combined into ONE matrix by multiplying them - called **composite transformation** or **concatenation**.
- **Rigid body transformation** - Preserves shape and size: translation, rotation, reflection.
- **Animation** - Achieved by applying a sequence of transformations to objects over successive frames.


> **NOTE: PYQ worked out**
>
> "In order to move objects in computer graphics that generate animation effects which of the following is necessary?" Answer: **Various transformation operations**.
>
> Reasoning: motion is nothing more than repeatedly changing an object's position, orientation or size between frames - that is, applying **translation, rotation and scaling**. The distractors belong elsewhere: "line rasterisation sequencing" is about drawing a single line onto pixels, the "Phong model of lighting" is about shading and illumination, and "eigen value computations" belong to linear algebra generally (used in some simulations, but not the mechanism of animation).



### I3.5 Three-dimensional viewing and projections


**Projection** maps a 3D object onto a 2D viewing plane.


| Projection | Description |
|---|---|
| PARALLEL projection | Projectors are PARALLEL to each other. Preserves relative dimensions and parallel lines, but looks less realistic. Used in engineering drawings |
| -- Orthographic | Projectors are PERPENDICULAR to the view plane. Gives the standard front, top and side views |
| -- Oblique | Projectors meet the plane at an angle. Cavalier and Cabinet projections |
| PERSPECTIVE projection | Projectors converge at a single point (the centre of projection / eye). Distant objects appear SMALLER - realistic, like the human eye or a camera. Introduces vanishing points |


- **Isometric projection** - An orthographic projection where all three axes are equally foreshortened.
- **Vanishing point** - The point at which parallel lines appear to converge in perspective projection. One-point, two-point and three-point perspective.
- **Standard orthographic views** - Front view, top view (plan) and side view (elevation) - together they fully describe an object.


> **NOTE: PYQ worked out**
>
> "______ and ______ views cannot be framed together for rendering a computer visual appropriately." Answer key: **Orthogonal projection, horizontal view**.
>
> The reasoning behind this style of question: certain view pairs are mutually incompatible in a single rendering because they use different projection geometry or would show the same information redundantly. An **orthographic (orthogonal)** projection uses parallel projectors perpendicular to the plane, so it cannot simultaneously present a **horizontal** viewing direction in the same frame - the two definitions conflict.
>
> Note that the tempting option "Parallel projection, perspective projection" is a genuinely incompatible pair in principle (you cannot use both projection types for one image), so if you meet a similar question with slightly different options, reason from **which two views define contradictory projector geometry**.



### I3.6 Lighting, shading and hidden surface removal


- **Illumination model** - Computes the colour of a point on a surface from the light sources and surface properties.
- **Ambient light** - Uniform background light with no direction.
- **Diffuse reflection** - Light scattered equally in all directions from a dull surface. Depends on the angle between the light and the surface normal (Lambert's law).
- **Specular reflection** - The shiny highlight from a glossy surface. Depends on the viewer's position.
- **PHONG lighting model** - Combines ambient + diffuse + specular components. The specular term uses a shininess exponent.


#### Parameters that influence lighting

The appearance of a lit surface depends on: the **light source** (position, colour, intensity), the **surface** (material, colour, normal direction, roughness), and the **position of the observer** (needed for specular highlights).


> **NOTE: PYQ worked out**
>
> "Which of these is NOT a parameter upon which the influence of lighting is based?" Options: Light Source, Position of Observer, **Rendering Algorithm**, Surface. Answer: **Rendering Algorithm**.
>
> Reasoning: the physical inputs to an illumination calculation are the light source, the surface properties and the observer's position. The **rendering algorithm** is the *method used to compute* the image - it is the process, not a parameter of the lighting itself. This is the same kind of distinction as "the recipe is not an ingredient".



| Shading method | Description |
|---|---|
| Flat / Constant shading | One colour for an entire polygon. Fastest, shows faceting |
| Gouraud shading | Intensity is computed at the vertices and INTERPOLATED across the polygon. Smooth, but can miss specular highlights inside a polygon |
| Phong shading | The surface NORMAL is interpolated and lighting is computed per pixel. Slower but much better highlights |



| Hidden surface removal | Method |
|---|---|
| Z-buffer (depth buffer) | Stores a depth value per pixel; the nearest surface wins. Simple and very widely used |
| Back-face detection | Discards polygons facing away from the viewer |
| Painter's algorithm (depth sort) | Draws polygons from farthest to nearest |
| Scan-line method | Resolves visibility one scan line at a time |
| Ray tracing | Traces rays from the eye through each pixel into the scene. Very realistic (reflections, refractions, shadows) but computationally expensive |



### I3.7 Virtual reality and image editing


- **Virtual Reality (VR)** - **The construction of computer-generated simulations that simulate real-world activities using interactive graphics software and hardware.** The user is immersed in and can interact with a synthetic 3D environment, usually via a head-mounted display, motion tracking and haptic gloves.
- **Augmented Reality (AR)** - Overlays computer-generated content onto the real world rather than replacing it.
- **Immersion, interaction, imagination** - The "three I's" of virtual reality.


> **NOTE: Direct PYQ**
>
> "The construction of computer-generated simulations that simulate real-world activities using interactive graphics software and hardware is called:" Answer: **virtual reality systems**.
>
> The other options belong to Artificial Intelligence: **genetic algorithms** are optimisation techniques modelled on natural selection; **fuzzy neural networks** combine fuzzy logic with neural networks; **hybrid systems** combine two or more AI techniques. Only virtual reality involves *simulating real-world activity with interactive graphics*.



#### Image editing (Photoshop-style) terms asked in the papers


| Term | Meaning |
|---|---|
| Adjustments panel | The Photoshop panel used to alter BRIGHTNESS, CONTRAST, levels, curves, hue and saturation - the standard place for tonal correction |
| Healing brush tool | Repairs blemishes by blending in nearby pixels |
| Paint bucket tool | Fills an area with a colour |
| Selection tools | Marquee, lasso, magic wand - define the area to work on |
| Cutting / Crop tool | REMOVES PARTS OF THE IMAGE |
| Layers | Stacked transparent sheets that can be edited independently |
| Resolution | Pixels per inch; changing it resizes or resamples |
| Filters | Effects applied to pixels: blur, sharpen, distort |



| Format | Best used for |
|---|---|
| PNG | LOSSLESS compression with TRANSPARENCY support. The standard choice for EXPORTING IMAGES FOR THE WEB, especially logos and graphics with sharp edges |
| JPEG / JPG | Lossy compression, small files, ideal for photographs on the web. No transparency |
| GIF | 256 colours, supports simple animation and transparency |
| SVG | Vector, infinitely scalable, ideal for icons and logos on the web |
| WebP | Modern web format, better compression than JPEG/PNG |
| PSD | Adobe Photoshop's NATIVE working file - keeps layers, but is huge and not viewable in browsers |
| TIFF | High-quality lossless format for printing and archiving. Very large files, not for the web |
| BMP | Uncompressed Windows bitmap. Enormous files, not for the web |



> **NOTE: Two direct PYQs on image editing**
>
> "Which tool is used to adjust the brightness and contrast of an image in Adobe Photoshop?" Answer: **Adjustments panel**.
>
> "Which of the following formats is commonly used for exporting images for the web?" Options: **PNG**, PSD, BMP, TIFF. Answer: **PNG**. PSD is Photoshop's editable working format, while BMP and TIFF produce very large files - none of the three is suitable for web delivery, where small size matters.
>
> "What is the main function of the 'cutting' tool in image editing?" Answer: **To remove parts of the image.** It does not change resolution, apply colour effects or resize.



## I4 Management Information Systems and Knowledge Management



### I4.1 Data, information, knowledge


- **Data** - Raw unprocessed facts. "45".
- **Information** - Processed, organised data that has meaning in a context. "The student scored 45 out of 100."
- **Knowledge** - Information combined with experience, judgement and understanding, enabling action. "A score of 45 in this subject usually means the student needs remedial help in fractions."
- **Wisdom** - Knowing which knowledge to apply and why.


### I4.2 What an information system is


- **Information system** - **A set of interrelated components that collect (or retrieve), process, store and distribute information to support decision-making and control in an organisation.**
- **Information technology** - The hardware, software and networks - the *tools*. An information *system* is broader: it includes the people and the procedures too.


> **NOTE: Direct PYQ**
>
> "______ is a set of interrelated components that collect (or retrieve), process, store and distribute information to support decision-making and control in an organisation." Answer: **An information system**.
>
> The distractor "An information technology" is deliberately close. Remember: **IT is the technology; an IS is technology + people + processes working together toward an organisational purpose.** The other options ("mini model / max model of a processed system") are not real terms.



#### The components of an information system

- **Hardware, Software, Data, People, Procedures, Networks** - The six classic components.
- **Organisation, Management, Technology** - The three dimensions of an information system in Laudon's framework. The **ORGANISATION** is the **formal social unit devoted to attaining specified goals**.


> **NOTE: Direct PYQ**
>
> "In a management information system, what is/are the formal social unit that is/are devoted to attaining specified goals?" Options: Organisation, management and marketing / **Organisation** / Management / Marketing. Answer: **Organisation**.
>
> Definition to memorise: an **organisation** is a stable, formal social structure that takes resources from the environment and processes them to produce outputs, coordinated toward specified goals. **Management** is the *function* of planning and directing; **marketing** is a business *activity*. Only "organisation" is the social *unit*.



### I4.3 Types of information system by management level



| System | Full form | Users | Purpose |
|---|---|---|---|
| TPS | Transaction Processing System | Operational staff | Records day-to-day routine transactions - payroll, order entry, billing |
| OAS | OFFICE AUTOMATION SYSTEM | All office workers | Supports clerical and communication work: WORD PROCESSING, ELECTRONIC FILING, ELECTRONIC MAIL, MESSAGE SWITCHING, DATA STORAGE, DATA AND VOICE COMMUNICATION, desktop publishing, scheduling |
| KWS | Knowledge Work System | Engineers, designers, analysts | Supports the creation of new knowledge - CAD, simulation |
| MIS | Management Information System | Middle management | Produces routine summary and exception REPORTS from TPS data, for monitoring and control |
| DSS | DECISION SUPPORT SYSTEM | Middle and senior management | A computer program application used to IMPROVE A COMPANY'S DECISION-MAKING CAPABILITIES. Analyses semi-structured problems using models, what-if analysis and simulation |
| ESS / EIS | Executive Support / Information System | Top executives | Highly summarised, graphical, strategic view with drill-down. Handles unstructured decisions |
| CRM | Customer Relationship Management | Sales and marketing | Manages all customer interactions |
| ERP | Enterprise Resource Planning | Whole organisation | One integrated system across finance, HR, manufacturing, supply chain |
| SCM | Supply Chain Management | Logistics | Manages suppliers, inventory and distribution |



> **NOTE: Two direct PYQs on system types**
>
> "DSS is a computer program application used to improve a company's ______ capabilities." Answer: **decision-making capabilities**. The name says it: **D**ecision **S**upport **S**ystem.
>
> "Which of the following systems comprises word processing, electronic filing, electronic mail, message switching, data storage and data and voice communication?" Answer: **Office Automation Systems**.
>
> Every item in that list is a routine *office* function - documents, filing, mail, messaging. An ESS gives executives strategic dashboards, a DSS runs analytical models, and CRM manages customers. Only OAS is about general office productivity and communication.



> **TIP: MIS vs DSS - the distinction examiners test**
>
> **MIS** answers "**what happened?**" with fixed, routine reports on structured data. **DSS** answers "**what if?**" and "**what is best?**" with flexible, interactive models on semi-structured problems. **ESS** answers "**what should we do strategically?**" with highly summarised external and internal data.



### I4.4 Knowledge management


- **Knowledge Management (KM)** - **The set of processes developed in an organisation to create, gather, store, transfer and apply knowledge.**


#### Purposes of a KM system

Driving strategy, integration of knowledge across the organisation, sharing of knowledge, capturing and codifying expertise, improving decisions, reducing duplicated effort, and retaining knowledge when employees leave.

Note that **portability** is *not* a purpose of a knowledge management system - it is a software quality attribute.


> **NOTE: Two direct PYQs on KM**
>
> "The set of processes developed in an organisation to create, gather, store, transfer and apply knowledge best describes:" Answer: **knowledge management**. ("Knowledge asset" is the *thing* being managed; "organisational memory" is the *store*; "organisational learning" is the *outcome*.)
>
> "Which of the following is NOT the purpose of knowledge management system?" Options: Driving strategy, Integration, Sharing of knowledge, **Portability**. Answer: **Portability**. Portability means software running on different platforms - a technical quality, unrelated to the goals of KM.



### I4.5 Tacit and explicit knowledge



| Type | Description | Example |
|---|---|---|
| TACIT knowledge | Personal, EXPERIENCE-BASED knowledge that is difficult to write down or formalise. It resides in a person's head and is acquired through practice. It **results from an individual's shared experience** | Knowing how to ride a bicycle; a master craftsman's feel for the material; an experienced teacher's classroom instinct |
| Explicit knowledge | Codified, documented knowledge that can easily be written, stored and transmitted | A manual, a textbook, a database, a written procedure |


- **SECI model (Nonaka and Takeuchi)** - The four modes of knowledge conversion: **Socialisation** (tacit to tacit), **Externalisation** (tacit to explicit), **Combination** (explicit to explicit), **Internalisation** (explicit to tacit).


> **NOTE: Direct PYQ**
>
> "An individual's shared experience results in ______." Options: systematic knowledge, shared knowledge, **tacit knowledge**, all three. Answer: **tacit knowledge**.
>
> The key phrase is "**individual's experience**". Knowledge gained personally through doing and experiencing, which is hard to articulate, is by definition **tacit**. Systematic and explicit knowledge is what you get from documents and formal training.



### I4.6 Other KM terms


- **Best practices** - **A particular organisation's or industry's most successful solutions or problem-solving methods** - the proven approaches worth reusing. (Note: one DSSSB paper asked this and the official key gave "knowledge management" rather than "best practices". Strictly, the phrase describes **best practices**; be alert if both options appear.)
- **Knowledge asset** - The intellectual resources an organisation owns - patents, documented processes, employee expertise.
- **Knowledge warehouse** - A repository storing organisational knowledge.
- **Organisational learning** - The process by which an organisation as a whole adapts and improves from experience.
- **Organisational memory** - The accumulated stored knowledge of an organisation.
- **Communities of practice** - Informal groups sharing a professional interest, used to spread tacit knowledge.


#### Building a KM system - cost


> **NOTE: Direct PYQ**
>
> "The lowest cost solution to developing a KM system is:" Options: **in-house development**, outsourcing, development by end users, off-the-shelf solution. Answer: **in-house development**.
>
> The reasoning the examiner expects: building it internally uses existing staff and existing infrastructure, avoiding vendor fees, licence costs and consultancy charges. Outsourcing and buying a packaged product both involve paying an external party.



### I4.7 Qualitative and quantitative measures


- **Quantitative** - Measurable in numbers: revenue, response time, number of users, infrastructure count.
- **Qualitative** - Descriptive, subjective, hard to put a number on: **value**, satisfaction, morale, brand reputation, culture, trust.


> **NOTE: Direct PYQ**
>
> "Which qualitative statistic is difficult to quantify precisely?" Options: Model, Infrastructure, **Value**, Decision making. Answer: **Value**.
>
> Reasoning: "value" is inherently subjective - the value a knowledge system delivers depends on perception, context and long-term effects, so it resists precise measurement. Infrastructure can be counted, models can be specified, and decision-making can be measured through outcomes and cycle times.




---

# PART J - Mathematics, Statistics, Physics and Commerce for the Discipline Sections

> *The DSSSB Discipline papers mix in graduate-level Maths, Physics, Accounting and Economics. This Part covers only what actually appeared - not whole textbooks.*



## J1 Why This Part Exists



### J1.1 Read this before you panic


If you looked at the papers and saw questions on lasers, optical fibres, gross profit and differential equations, you were right to be surprised. These are not Computer Science topics.

DSSSB builds the "Discipline" question bank from the wider graduate syllabus of the subject stream, so Physics, Mathematics, Statistics, Accountancy and Business Economics questions appear alongside the computing ones. Counting across the three papers you shared, they make up roughly **15 to 25 questions**.


> **TIP: The right strategy for this Part**
>
> Do **not** try to master these subjects. You will lose weeks and gain little.
>
> Instead: learn the **specific formulas and definitions** in this Part. Nearly every non-CS question in those papers was a one-step application of a standard formula or a plain definition. Master these pages and you will convert most of those marks without opening a Physics textbook.
>
> If a question in the exam needs more than one step of unfamiliar mathematics, **skip it**. With negative marking, a skipped question costs you nothing; a guessed one costs 0.25.



## J2 Numerical Methods



### J2.1 Interpolation - the core idea


You know the value of a function at a few points. **Interpolation** estimates its value at a point **in between** those known points. **Extrapolation** estimates a value **outside** the known range and is much less reliable.

- **Interpolation** - Constructing new data points within the range of a discrete set of known data points. It is carried out using **curve fitting and linear analysis** - you fit a curve through the known points and read off the value you need.
- **Interpolant** - The function produced by interpolation.


> **NOTE: Direct PYQ**
>
> "Interpolation is carried out using data from:" Options: regression analysis / curve fitting and regression analysis / linear interpolation / **curve fitting and linear analysis**. Answer: **curve fitting and linear analysis**.
>
> The distinction that matters: **interpolation** passes *exactly through* every known data point, whereas **regression** finds a best-fit line that need not pass through any point. So options mentioning regression are wrong.



### J2.2 Types of interpolation



| Method | Description | Smoothness of the result |
|---|---|---|
| PIECEWISE CONSTANT (nearest neighbour) | Each interval simply takes the value of the nearest known point. The graph is a staircase | The LEAST smooth - it is discontinuous, giving the "softest"/crudest interpolant with no curvature |
| Linear | Straight lines joining consecutive points | Continuous but has sharp corners (kinks) at the data points |
| Polynomial | A single polynomial of degree n-1 through all n points | Smooth everywhere, but high-degree polynomials oscillate wildly near the edges (Runge's phenomenon) |
| SPLINE | Low-degree polynomials (usually cubic) on each interval, joined so that the first and second derivatives match | Smooth AND well behaved - the practical favourite |
| NONLINEAR | Uses a nonlinear model. Used in PROBABILITY THEORY AND STATISTICS; the GAUSSIAN PROCESS is a classic EXAMPLE (also called kriging) | Depends on the model |



> **NOTE: Two direct PYQs on interpolation types**
>
> "Which method creates interpolants that are softer?" Answer key: **Piecewise constant interpolation**. The reasoning in the paper's sense is that piecewise constant interpolation makes no attempt at curvature - it produces the crudest, "softest" (least mathematically demanding) interpolant, a simple step function.
>
> "The ______ interpolation method is used in probability theory and statistics, and the Gaussian process is one example." Answer: **nonlinear**. The Gaussian process (kriging) is a nonlinear, probabilistic interpolation technique used heavily in statistics and machine learning. Linear, polynomial and spline interpolation are all deterministic curve-fitting techniques, not probabilistic ones.



### J2.3 Lagrange interpolation - solved



*Lagrange's interpolation formula*
```
For points (x0,y0), (x1,y1), ... (xn,yn):

  f(x) = SUM over i of  [ y_i x PRODUCT over j not equal to i of (x - x_j)/(x_i - x_j) ]

For THREE points it becomes:

  f(x) =  y0 (x-x1)(x-x2) / [(x0-x1)(x0-x2)]
        + y1 (x-x0)(x-x2) / [(x1-x0)(x1-x2)]
        + y2 (x-x0)(x-x1) / [(x2-x0)(x2-x1)]
```



> **NOTE: PYQ worked out**
>
> "The values of x are 1, 3, 4 and those of f(x) are 1, 27, 64. What is the polynomial equation by using the Lagrange interpolation formula?"
>
> Answer: **8x^2 - 19x + 12**
>
> Rather than expanding the whole Lagrange formula (slow and error-prone under exam pressure), use this **verification shortcut**: the correct polynomial must reproduce every given data point. Test each option.
>
> Test **8x^2 - 19x + 12**:
> At x = 1: 8(1) - 19(1) + 12 = 8 - 19 + 12 = **1** - matches f(1) = 1
> At x = 3: 8(9) - 19(3) + 12 = 72 - 57 + 12 = **27** - matches f(3) = 27
> At x = 4: 8(16) - 19(4) + 12 = 128 - 76 + 12 = **64** - matches f(4) = 64
> All three points match, so this is the answer.
>
> Test **8x^2 + 9x + 12** (a distractor):
> At x = 1: 8 + 9 + 12 = 29, but f(1) should be 1. Fails immediately.
>
> **Exam technique:** for any "find the interpolating polynomial" question, substitute the smallest given x into each option. Usually three of the four options fail on the first substitution.



### J2.4 Finite difference operators


These appear in numerical-methods questions and look intimidating, but only a few identities are ever asked.


| Operator | Symbol | Definition |
|---|---|---|
| Forward difference | Delta | Delta f(x) = f(x + h) - f(x) |
| Backward difference | nabla | nabla f(x) = f(x) - f(x - h) |
| Central difference | delta | delta f(x) = f(x + h/2) - f(x - h/2) |
| Averaging (mean) operator | mu | mu f(x) = [ f(x + h/2) + f(x - h/2) ] / 2 |
| Shift operator | E | E f(x) = f(x + h) |



#### The identities you should memorise


*Key operator relations*
```
Delta = E - 1                      so    E = 1 + Delta
nabla = 1 - E^(-1)
delta = E^(1/2) - E^(-1/2)
mu    = ( E^(1/2) + E^(-1/2) ) / 2

AND THE ONE THAT IS ASKED:
   mu^2 = 1 + delta^2 / 4  =  ( delta^2 + 4 ) / 4
```



> **NOTE: PYQ worked out - the averaging operator**
>
> "If mu is an averaging operator and delta^n is the nth central difference operator, then what is the value of mu^2?"
>
> Answer: **mu^2 = (1/4)(delta^2 + 4)**
>
> Derivation, so you can reconstruct it if you forget:
> mu = ( E^(1/2) + E^(-1/2) ) / 2
>
> Square both sides:
> mu^2 = ( E^(1/2) + E^(-1/2) )^2 / 4
> = ( E + 2 + E^(-1) ) / 4
>
> Now note that delta = E^(1/2) - E^(-1/2), so
> delta^2 = E - 2 + E^(-1),  which gives  E + E^(-1) = delta^2 + 2
>
> Substitute:
> mu^2 = ( delta^2 + 2 + 2 ) / 4 = ( delta^2 + 4 ) / 4 = **(1/4)(delta^2 + 4)**
>
> The wrong options change either the fraction (1/2 instead of 1/4) or the constant (6 or 8 instead of 4). Remember the pair of numbers: **one quarter, and plus four.**



> **NOTE: PYQ worked out - nth difference of an exponential**
>
> "What is the value of Delta^n e^(ax+b)?"
>
> Answer: **(e^(ah) - 1)^n e^(ax+b)**
>
> Work out the first difference, then spot the pattern:
> Delta e^(ax+b) = e^(a(x+h)+b) - e^(ax+b)
> = e^(ax+b) e^(ah) - e^(ax+b)
> = e^(ax+b) ( e^(ah) - 1 )
>
> So one application multiplies by the factor (e^(ah) - 1). Applying it n times multiplies by that factor n times:
> Delta^n e^(ax+b) = **(e^(ah) - 1)^n e^(ax+b)**
>
> The two things to check in the options: the sign inside the bracket must be **minus 1** (not plus 1), and the exponent must stay **ax + b** (not ax - b), because differencing never changes the constant b.



## J3 Probability and Statistics



### J3.1 Basic probability


- **Probability** - P(E) = (number of favourable outcomes) / (total number of equally likely outcomes). It always lies between 0 and 1.
- **Classical definition** - Attributed to **Pierre-Simon Laplace**, who formalised probability as the ratio of favourable to total equally likely cases.
- **Sample space** - The set of all possible outcomes.
- **Mutually exclusive events** - Cannot happen together, so P(A and B) = 0 and P(A or B) = P(A) + P(B).
- **Independent events** - One does not affect the other, so P(A and B) = P(A) x P(B).
- **Addition rule** - P(A or B) = P(A) + P(B) - P(A and B).
- **Conditional probability** - P(A given B) = P(A and B) / P(B).
- **Complement** - P(not A) = 1 - P(A).


> **NOTE: Direct PYQ**
>
> "Who invented the probability definition?" Options: **Simon Laplace**, Euclid, None, Einstein. Answer: **Simon Laplace** (Pierre-Simon Laplace). He gave the classical definition of probability in his 1812 work. Euclid is geometry; Einstein is physics.



### J3.2 Bayesian vs frequentist probability



| Approach | Interpretation of probability |
|---|---|
| Classical / Frequency probability | The long-run relative frequency of an event in repeated identical trials. Objective |
| BAYESIAN probability | Probability as a **DEGREE OF BELIEF** in a proposition, which is **updated as new evidence arrives**. It is a "probability calculus of views/beliefs that obeys particular rules" (the Cox axioms) |


- **Bayes' theorem** - P(A given B) = [ P(B given A) x P(A) ] / P(B). Here P(A) is the **prior**, P(A given B) is the **posterior**, and P(B given A) is the **likelihood**.


> **NOTE: Direct PYQ**
>
> "Which probability calculus of views obeys particular rules?" Options: Standard deviation, Variance, **Bayesian probability**, Frequency probability. Answer: **Bayesian probability**.
>
> The phrase "calculus of **views**" is the clue - Bayesian probability treats probability as a quantified *belief or opinion*, updated by evidence according to fixed rules. Standard deviation and variance are *measures of spread*, not interpretations of probability at all.



### J3.3 Solved probability problems from the papers



> **NOTE: PYQ worked out - two dice, sum neither 5 nor 9**
>
> "If two dice are thrown, find the probability that the sum is neither 5 nor 9."
>
> Answer: **7/9**
>
> Total outcomes when two dice are thrown = 6 x 6 = **36**.
>
> Count the ways to get a sum of **5**: (1,4), (2,3), (3,2), (4,1) = **4 ways**
> Count the ways to get a sum of **9**: (3,6), (4,5), (5,4), (6,3) = **4 ways**
>
> These two events cannot happen together, so the sum is 5 or 9 in 4 + 4 = **8** ways.
>
> P(sum is 5 or 9) = 8/36 = 2/9
>
> P(sum is NEITHER 5 nor 9) = 1 - 2/9 = **7/9**
>
> Technique: whenever a question says "**neither ... nor ...**" or "**not**", count the unwanted cases and subtract from 1. It is almost always faster than counting the wanted cases.



> **NOTE: PYQ worked out - even number on a die**
>
> "Suppose a six faced die is thrown. Then the probability that the number appearing on the top is even is equal to:"
>
> Answer: **1/2**
>
> Sample space = {1, 2, 3, 4, 5, 6}, so 6 outcomes.
> Even numbers = {2, 4, 6}, so 3 favourable outcomes.
> P(even) = 3/6 = **1/2**
>
> Note the distractors 1/4, 1/6 and 1/9. The value 1/6 is the probability of one *specific* number, which is a common misread.



### J3.4 Probability distributions



| Distribution | Discrete or continuous | Used for |
|---|---|---|
| Bernoulli | Discrete | A single trial with two outcomes (success/failure) |
| BINOMIAL | Discrete | The number of successes in n independent trials. Mean = np, Variance = npq |
| POISSON | DISCRETE | The number of RARE events in a fixed interval of time or space. Mean = Variance = lambda. THE generic probability function for discrete random variables in this context |
| Geometric | Discrete | Number of trials until the first success |
| Uniform | Either | All outcomes equally likely |
| NORMAL (GAUSSIAN) | CONTINUOUS | The bell curve. Symmetric about the mean; mean = median = mode |
| Exponential | Continuous | Time between events in a Poisson process |
| Rayleigh | Continuous | Magnitude of a two-dimensional vector; used in signal fading models |
| Chi-square | Continuous | Testing goodness of fit and INDEPENDENCE in contingency tables |
| t distribution | Continuous | Small-sample tests of means |
| F distribution | Continuous | Comparing variances (ANOVA) |
| Cumulative distribution | Either | F(x) = P(X <= x). It is a FUNCTION, not a distribution family in itself |



> **NOTE: PYQ worked out**
>
> "Identify the generic probability density function that corresponds with discrete random variables." Options: Cumulative distribution, Gaussian distribution, **Poisson distribution**, Rayleigh distribution. Answer: **Poisson distribution**.
>
> Reasoning: the question asks for the one associated with **DISCRETE** random variables. Gaussian (normal) and Rayleigh are both **continuous** distributions. "Cumulative distribution" is a general concept applying to both. Only **Poisson** is a discrete distribution among the options - it counts whole numbers of events (0, 1, 2, 3 ...).



### J3.5 Measures of central tendency and dispersion



| Measure | Definition |
|---|---|
| Arithmetic Mean (AM) | Sum of all values divided by the number of values. The most common average |
| Median | The middle value when data is arranged in order. The **second quartile (Q2)**. Unaffected by extreme values |
| Mode | The most frequently occurring value |
| Geometric Mean (GM) | The nth root of the product of n values. Used for growth rates and ratios |
| Harmonic Mean (HM) | n divided by the sum of the reciprocals. Used for averaging rates and speeds |
| Relation | AM >= GM >= HM always |
| Range | Maximum minus minimum |
| Quartiles | Q1, Q2 (median), Q3 divide the data into four parts |
| Variance | The mean of the squared deviations from the mean |
| Standard deviation | The square root of the variance. Same units as the data |
| Coefficient of variation | (Standard deviation / Mean) x 100 - a unit-free measure of relative spread |



> **NOTE: PYQ worked out - a classic property of the mean**
>
> "The algebraic sum of deviations is zero when measured from the ______." Options: second quartile, geometric mean, **arithmetic mean**, harmonic mean. Answer: **arithmetic mean**.
>
> Proof in one line. The sum of deviations from the mean is
> SUM (x_i - mean) = SUM x_i - n x mean
>
> But by definition mean = (SUM x_i) / n, so n x mean = SUM x_i. Substituting:
> SUM (x_i - mean) = SUM x_i - SUM x_i = **0**
>
> Verify with a tiny example: data 2, 4, 6. Mean = 4. Deviations are -2, 0, +2, which sum to 0.
>
> This is a **defining property of the arithmetic mean** and one of the most frequently asked statistics facts. Note the related property: the sum of *squared* deviations is **minimum** when measured from the arithmetic mean.



### J3.6 Chi-square test for independence


- **Purpose** - To test whether two categorical variables are **independent** (unassociated), using a contingency table.
- **Degrees of freedom** - For an r x c contingency table, **df = (r - 1)(c - 1)**.


> **NOTE: PYQ worked out**
>
> "Eighty eight residents of a city, who were interviewed in a city are classified as male or female and also as drinkers or non-drinkers of tea. For testing association between sex and drinking of tea, the test statistic follows:"
>
> Answer: **Chi square distribution with 1 degree of freedom**
>
> Reasoning:
> - Testing **association between two categorical variables** means a **chi-square test of independence**. That eliminates the t-distribution and normal-distribution options.
> - Now the degrees of freedom. The table has **2 rows** (male, female) and **2 columns** (drinker, non-drinker).
> df = (r - 1)(c - 1) = (2 - 1)(2 - 1) = 1 x 1 = **1**
>
> Note that the sample size (88) is a deliberate red herring - it does not enter the degrees-of-freedom calculation at all. The distractor "chi square with 2 degrees of freedom" is what you get if you mistakenly use (r + c - 2) or forget to subtract.



## J4 Series, Calculus, Matrices and Differential Equations



### J4.1 Convergence of a p-series


- **p-series** - A series of the form SUM 1/n^p.
- **Convergence rule** - The p-series **CONVERGES if p > 1** and **DIVERGES if p <= 1**.


> **NOTE: PYQ worked out**
>
> "The series SUM 1 / (n^2)^(1/5) is:" Answer: **convergent**.
>
> Simplify the general term first - this is the whole trick:
> 1 / (n^2)^(1/5) = 1 / n^(2/5)
>
> So this is a p-series with **p = 2/5 = 0.4**.
>
> Since p = 0.4 is **less than 1**, the strict p-series rule says this series **DIVERGES**. However, the official answer key for this paper marked it **convergent**.
>
> **How to handle this in the exam:** learn the rule properly - *p greater than 1 converges, p less than or equal to 1 diverges*. Recognise that this particular key appears to be in error (or the printed expression differed from what was intended, e.g. a fifth root of n^2 in the denominator raised differently). Do not let one questionable key entry undermine the rule, which is standard and will be needed for other questions.
>
> Quick reference: SUM 1/n diverges (harmonic series, p = 1). SUM 1/n^2 converges (p = 2). SUM 1/sqrt(n) diverges (p = 1/2).



### J4.2 Euler's theorem on homogeneous functions


- **Homogeneous function of degree n** - f(tx, ty) = t^n f(x, y).
- **Euler's theorem** - If f is homogeneous of degree n, then x (df/dx) + y (df/dy) = **n f**.


> **NOTE: PYQ worked out**
>
> "If u = tan inverse (y/x), then x (du/dx) + y (du/dy) = ?"
>
> Answer: **0**
>
> Method 1 - Euler's theorem (fast). Check the degree of homogeneity of u:
> u(tx, ty) = tan inverse ( ty / tx ) = tan inverse ( y / x ) = u(x, y) = t^0 u(x, y)
>
> So u is homogeneous of **degree 0**. By Euler's theorem:
> x (du/dx) + y (du/dy) = n u = **0** x u = **0**
>
> Method 2 - direct differentiation (to confirm). With u = arctan(y/x):
> du/dx = -y / (x^2 + y^2)
> du/dy =  x / (x^2 + y^2)
>
> So x (du/dx) + y (du/dy) = -xy/(x^2+y^2) + xy/(x^2+y^2) = **0**
>
> **Lesson worth remembering:** any function of the pure ratio y/x is homogeneous of degree zero, so this expression is always 0. Recognising that saves the whole calculation.



### J4.3 Vector calculus - the normal to a surface


- **Gradient** - For a surface F(x, y, z) = constant, the vector **grad F = (dF/dx, dF/dy, dF/dz)** is **normal (perpendicular)** to the surface at every point.
- **Unit normal** - grad F divided by its own magnitude.


> **NOTE: PYQ worked out**
>
> "Find a unit vector normal to the surface x^3 + y^3 + 3xyz = 3 at the point (1, 2, -1)."
>
> Answer: **(1/sqrt 14)( -i + 3j + 2k )**
>
> Step 1 - write F and take partial derivatives.
> F = x^3 + y^3 + 3xyz - 3
>
> dF/dx = 3x^2 + 3yz
> dF/dy = 3y^2 + 3xz
> dF/dz = 3xy
>
> Step 2 - evaluate at the point (1, 2, -1).
> dF/dx = 3(1)^2 + 3(2)(-1) = 3 - 6 = **-3**
> dF/dy = 3(2)^2 + 3(1)(-1) = 12 - 3 = **9**
> dF/dz = 3(1)(2) = **6**
>
> So grad F = -3i + 9j + 6k
>
> Step 3 - simplify by taking out the common factor 3.
> grad F = 3( -i + 3j + 2k )
>
> Step 4 - find the magnitude of the simplified direction vector.
> | -i + 3j + 2k | = sqrt( 1 + 9 + 4 ) = **sqrt 14**
>
> Step 5 - the unit normal.
> n = ( -i + 3j + 2k ) / **sqrt 14**
>
> Note the distractors: one option has the signs as (i - 3j + 2k) and another divides by sqrt 2 instead of sqrt 14. Always (a) take out the common factor before computing the magnitude, and (b) double-check every sign.



### J4.4 Volume of a tetrahedron



> **NOTE: PYQ worked out**
>
> "The volume of the tetrahedron bounded by the surfaces x = 0, y = 0, z = 0 and x/a + y/b + z/c = 1 is:"
>
> Answer: **abc / 6**
>
> This is a standard result worth memorising outright. The plane x/a + y/b + z/c = 1 cuts the three axes at (a,0,0), (0,b,0) and (0,0,c). Together with the three coordinate planes it forms a tetrahedron with three mutually perpendicular edges of lengths a, b and c.
>
> Volume of such a tetrahedron = (1/3) x (base area) x height
> = (1/3) x (1/2 x a x b) x c
> = **abc / 6**
>
> Memory hook: the box (cuboid) with sides a, b, c has volume abc; the corner tetrahedron is exactly **one sixth** of it.



### J4.5 Matrices


- **Characteristic equation** - For a matrix A, it is **det(A - lambda I) = 0**. Its roots are the **eigenvalues**.
- **For a 2x2 matrix** - The characteristic equation is **lambda^2 - (trace)lambda + (determinant) = 0**, where trace = sum of the diagonal elements.
- **Cayley-Hamilton theorem** - Every square matrix satisfies its own characteristic equation. This is the standard tool for computing high powers of a matrix.


> **NOTE: PYQ worked out - characteristic equation**
>
> "The characteristic equation of matrix A = [[1, 4], [3, 5]] is ______."
>
> Answer: **lambda^2 - 6 lambda - 7 = 0**
>
> Use the 2x2 shortcut. For A = [[a, b], [c, d]]:
> characteristic equation is  lambda^2 - (a + d) lambda + (ad - bc) = 0
>
> Here a = 1, b = 4, c = 3, d = 5.
> **Trace** = a + d = 1 + 5 = **6**
> **Determinant** = ad - bc = (1)(5) - (4)(3) = 5 - 12 = **-7**
>
> Substituting:
> lambda^2 - (6) lambda + (-7) = 0
> **lambda^2 - 6 lambda - 7 = 0**
>
> Note both signs carefully: the trace term is always **minus** trace, and here the determinant is itself negative, so it appears as **- 7**. The distractors flip these signs.



> **NOTE: PYQ worked out - high power of a matrix**
>
> "If A = [[1,0,0],[0,-1,0],[1,0,1]] then the matrix for A^6 is ______."
>
> Answer: **[[1,0,0],[0,1,0],[6,0,1]]**
>
> Rather than multiplying six times, compute A^2 and look for the pattern.
>
> A^2: multiply A by A. The structure is lower-triangular-ish with a simple pattern:
> - The (1,1) entry stays 1 (1 x 1 = 1).
> - The (2,2) entry is (-1) x (-1) = **+1**.
> - The (3,3) entry stays 1.
> - The (3,1) entry accumulates: in A it is 1; in A^2 it becomes 2.
>
> So A^2 = [[1,0,0],[0,1,0],[2,0,1]]
>
> The pattern is clear: **A^n has (3,1) entry = n, and the (2,2) entry is (-1)^n.**
>
> For n = 6 (an even power): (-1)^6 = **+1**, and the (3,1) entry = **6**.
>
> A^6 = **[[1,0,0],[0,1,0],[6,0,1]]**
>
> **Technique to carry into the exam:** for these "high power of a matrix" questions, compute A^2 (and A^3 if needed), spot the arithmetic pattern in the changing entries, then jump to the required power. Also use parity: an even power always makes a -1 diagonal entry become +1.



### J4.6 Differential equations


- **Order** - The highest derivative present.
- **Degree** - The power of the highest derivative.
- **General solution** - Contains arbitrary constants.
- **Particular solution** - The specific part corresponding to the right-hand side (also called the particular integral, PI).
- **Complementary function (CF)** - The solution of the homogeneous equation (right-hand side = 0).
- **Complete solution** - CF + PI.


#### Forming a differential equation from a solution

If a solution contains **n arbitrary constants**, the differential equation is of **order n**, and you eliminate the constants by differentiating n times.


> **NOTE: PYQ worked out**
>
> "Which of the following options is the differential equation corresponding to y = a e^(2x) + b e^(-x) where a and b are arbitrary?"
>
> Answer: **y'' - y' - 2y = 0**
>
> Fast method - work backwards from the exponents. A solution of the form
> y = a e^(m1 x) + b e^(m2 x)
> comes from a second-order equation whose **auxiliary equation** has roots m1 and m2.
>
> Here the roots are **m = 2** and **m = -1**.
>
> So the auxiliary equation is (m - 2)(m + 1) = 0, i.e.
> m^2 - m - 2 = 0
>
> Translate m^2 to y'', m to y', and the constant to y:
> **y'' - y' - 2y = 0**
>
> Verify quickly with y = e^(2x): y' = 2e^(2x), y'' = 4e^(2x).
> Then y'' - y' - 2y = 4e^(2x) - 2e^(2x) - 2e^(2x) = 0. Correct.
>
> **Technique:** read the exponents off the given solution, form (m - r1)(m - r2) = 0, expand, and replace powers of m with derivatives of y. This converts a two-minute elimination problem into a fifteen-second one.



> **NOTE: PYQ worked out - separable equation**
>
> "The general solution of dy/dx = e^(x + y) is:"
>
> Answer: **e^x + e^(-y) = c**
>
> Method - separate the variables.
> dy/dx = e^(x+y) = e^x . e^y          (splitting the exponential)
>
> Bring all y terms to one side and all x terms to the other:
> dy / e^y = e^x dx
> e^(-y) dy = e^x dx
>
> Integrate both sides:
> INTEGRAL e^(-y) dy = INTEGRAL e^x dx
> -e^(-y) = e^x + k
>
> Rearranging (and absorbing the constant):
> **e^x + e^(-y) = c**
>
> Check the signs in the options carefully - the distractors offer e^(-x) + e^y and similar sign swaps. The rule: integrating e^(-y) gives **minus** e^(-y), which is what flips the sign when you rearrange.



> **NOTE: PYQ worked out - particular solution with a repeated root**
>
> "Which of the following options is the particular solution of the differential equation y'' - 6y' + 9y = 2 e^(3t)?"
>
> Answer: **t^2 e^(3t)**
>
> Step 1 - find the auxiliary equation and its roots.
> m^2 - 6m + 9 = 0, which factorises as (m - 3)^2 = 0.
> So m = 3 is a **REPEATED (double) root**.
>
> Step 2 - recognise the resonance case.
> The right-hand side is 2e^(3t), and **3 is already a root of the auxiliary equation - twice**. This is the "resonance" or "failure case". The normal trial solution Ce^(3t) will not work, and neither will Cte^(3t).
>
> Step 3 - apply the rule for repeated roots.
> When the exponent matches a root of multiplicity k, multiply the trial solution by **t^k**. Here k = 2, so the particular integral has the form **C t^2 e^(3t)**.
>
> That matches the answer **t^2 e^(3t)**.
>
> **The rule to memorise:** for y'' + ay' + by = e^(rt),
> - if r is NOT a root, the PI is proportional to e^(rt)
> - if r is a SIMPLE root, the PI is proportional to t e^(rt)
> - if r is a DOUBLE root, the PI is proportional to t^2 e^(rt)
>
> The distractors e^(3t)/2, e^(3t) and e^(3t)/9 all ignore the repeated root - they are what you would wrongly get by naive substitution.



> **NOTE: PYQ worked out - operator form**
>
> "The particular solution of the differential equation (D^4 - 18D^2 + 81)y = ______"  Answer: **x^2 e^(3x)**
>
> Here D is the differential operator d/dx. Factorise the operator polynomial:
> D^4 - 18D^2 + 81 = (D^2 - 9)^2 = (D - 3)^2 (D + 3)^2
>
> So **m = 3 is a double root** (and so is m = -3). Exactly as in the previous question, an e^(3x) forcing term against a **double** root gives a particular solution containing **x^2 e^(3x)**.
>
> Notice this is the same underlying idea asked twice in two different papers with different notation (t versus x, D-operator versus primes). **Learn the resonance rule once and you gain both marks.**



## J5 Physics Topics That Appeared



### J5.1 Lasers


- **LASER** - **Light Amplification by Stimulated Emission of Radiation.**
- **Properties of laser light** - Monochromatic (single wavelength), coherent (waves in phase), highly directional, very intense.
- **Population inversion** - The condition where more atoms are in the excited state than the ground state. It is **essential** for laser action.
- **Pumping** - Supplying energy to achieve population inversion (optical, electrical, chemical).
- **Metastable state** - An excited state with an unusually long lifetime (about 10^-3 s instead of 10^-8 s), which allows population inversion to build up.


| Process | Description | Lifetime of the initial state |
|---|---|---|
| Stimulated ABSORPTION | An atom in the GROUND STATE absorbs a photon and jumps to an excited state | The ground state is the lowest energy state, so an atom can stay there FOREVER unless disturbed - its lifetime is INFINITE |
| Spontaneous emission | An excited atom drops to a lower state on its own, emitting a photon in a random direction and phase | About 10^-8 s for an ordinary excited state |
| Stimulated emission | An incoming photon triggers an excited atom to emit a second identical photon - same direction, phase and frequency. This is what AMPLIFIES the light | - |



> **NOTE: PYQ worked out**
>
> "What is the lifetime of an atom's ground state in Stimulated Absorption?" Options: 2 minutes, 11 hours, 5 seconds, **Infinity**. Answer: **Infinity**.
>
> Reasoning: "lifetime" means the average time an atom remains in a state before spontaneously leaving it. The **ground state is the lowest possible energy level** - there is nowhere lower for the atom to fall to. So without external excitation, an atom remains in the ground state indefinitely. Its lifetime is therefore taken as **infinite**. The numeric options are arbitrary distractors.



#### The CO2 laser

- **CO2 laser** - A molecular gas laser, one of the most powerful and efficient continuous-wave lasers. Emits in the infrared at **10.6 micrometres**. Used for cutting, welding and surgery.
- **Which transitions produce the output** - In atoms, laser transitions occur between **electronic** energy levels. But CO2 is a **molecule**, and molecules also have **vibrational** and **rotational** energy levels. The CO2 laser output comes from transitions between **VIBRATIONAL states** (specifically the asymmetric stretching mode dropping to the symmetric stretching mode).


> **NOTE: Direct PYQ**
>
> "Which transition generates laser output in CO2 molecule?" Options: **Vibrational states**, Pulsed output, Molecular states, Energy states. Answer: **Vibrational states**.
>
> Note the distractors: "pulsed output" describes a *mode of operation*, not a transition; "molecular states" and "energy states" are too vague to be the specific answer. The precise, examinable fact is that CO2 lasing occurs between **vibrational** energy levels of the molecule.



### J5.2 Polarisation and retardation plates


- **Polarisation** - A property of **TRANSVERSE waves** in which the oscillations occur in a particular direction perpendicular to the direction of propagation. Light and all electromagnetic waves are transverse, so they can be polarised. **Longitudinal waves such as sound CANNOT be polarised** - this is the standard proof that light is transverse.
- **Unpolarised light** - Vibrations in all directions perpendicular to propagation.
- **Plane / linearly polarised light** - Vibrations confined to one plane.
- **Polaroid** - A sheet that transmits only one plane of vibration. Its transmission direction is the **pass axis**.
- **Brewster's law** - At the Brewster angle, reflected light is completely plane polarised; tan(Brewster angle) = refractive index.
- **Malus's law** - Transmitted intensity I = I0 cos^2(theta), where theta is the angle between the polariser and analyser axes.


> **NOTE: PYQ worked out**
>
> "Does polarisation vary with direction?" Options: Polarising axis, **Transverse wave**, Propagating axis, Pass axis. Answer: **Transverse wave**.
>
> The question is oddly worded, but the concept being tested is fundamental: polarisation is a **direction-dependent** property, and it exists **only because light is a transverse wave**. Since the oscillation is perpendicular to the direction of travel, there is a *choice* of direction for the oscillation - and that choice is what polarisation describes. In a longitudinal wave the oscillation is always along the direction of travel, so there is no such choice and no polarisation.



#### Double refraction and retardation plates

- **Birefringence (double refraction)** - Certain crystals (calcite, quartz) have **two different refractive indices** depending on the direction of polarisation. An entering ray splits into two: the **ordinary (O) ray** and the **extraordinary (E) ray**, which travel at different speeds.
- **Retardation plate (wave plate)** - A thin slice of a birefringent crystal. Because the O and E rays travel at different speeds through it, one is **retarded** relative to the other, producing a **phase shift** between them. This phase shift is what the plate is for.
- **Quarter-wave plate** - Introduces a phase difference of 90 degrees (a quarter wavelength). Converts linear polarisation to circular.
- **Half-wave plate** - Introduces a phase difference of 180 degrees. Rotates the plane of linear polarisation.


> **NOTE: PYQ worked out**
>
> "Which phenomenon causes a phase shift in the retardation plates?" Options: Phasor plates, Retardation plates, Polaroid filters, **Double refraction**. Answer: **Double refraction**.
>
> The causal chain: the plate is made of a **birefringent (doubly refracting)** crystal, therefore the two polarisation components see different refractive indices, therefore they travel at different speeds, therefore they emerge with a **phase difference**. So the underlying *phenomenon* is **double refraction**.
>
> Note that "Retardation plates" is offered as an option - but that is the *device*, not the phenomenon, so it cannot be the answer to "which phenomenon". Watch for this device-versus-phenomenon trap.



### J5.3 LED and photon energy


- **Photon energy formula** - E = hc / lambda, where h = 6.626 x 10^-34 J s and c = 3 x 10^8 m/s.
- **The practical shortcut** - **E (in eV) = 12400 / lambda (in Angstrom)** - memorise this. Some books use 12375 or 12398; all give the same answer to two decimal places.
- **Band gap of an LED** - The photon emitted has energy approximately equal to the semiconductor's band gap Eg, so Eg = hc/lambda.


> **NOTE: PYQ worked out**
>
> "An LED emits green light of wavelength lambda = 5511.11 Angstrom. Find the value of Eg."
>
> Answer: **2.25 eV**
>
> Use the shortcut formula:
> Eg (eV) = 12400 / lambda (in Angstrom)
> = 12400 / 5511.11
> = **2.25 eV**
>
> Check by the long method if you prefer:
> lambda = 5511.11 Angstrom = 5511.11 x 10^-10 m
> E = hc / lambda = (6.626 x 10^-34 x 3 x 10^8) / (5511.11 x 10^-10)
> = (1.9878 x 10^-25) / (5.51111 x 10^-7)
> = 3.608 x 10^-19 J
>
> Convert to electron volts by dividing by 1.6 x 10^-19:
> E = 3.608 x 10^-19 / 1.6 x 10^-19 = **2.25 eV**
>
> Note the distractor **3.606 eV** - that is the answer in units of 10^-19 **joules** mistaken for eV. Always finish the conversion. Memorise **12400 / lambda(Angstrom) = energy in eV** and this becomes a ten-second question.



### J5.4 Simple harmonic motion - the spring problem


- **Time period of a spring-mass system** - T = 2 pi sqrt( m / k ), where k is the spring constant.
- **Static extension** - When a mass m hangs at rest, the spring stretches by x where kx = mg, so **x = mg / k**.
- **The useful combination** - From T = 2 pi sqrt(m/k) we get m/k = T^2 / (4 pi^2). Substituting into x = (m/k) g gives **x = g T^2 / (4 pi^2)**. Notice the mass cancels out entirely.


> **NOTE: PYQ worked out**
>
> "A body of mass 4.9 kg hangs from a spring and oscillates with a period of 0.6 sec. How much will the spring shorten when the body is removed?"
>
> Answer: **0.089 metre**
>
> Use the derived formula (the mass is not even needed):
> x = g T^2 / (4 pi^2)
>
> Substitute g = 9.8 m/s^2, T = 0.6 s:
> x = (9.8 x 0.6 x 0.6) / (4 x 3.1416 x 3.1416)
> = (9.8 x 0.36) / (39.478)
> = 3.528 / 39.478
> = **0.0894 m**, which is approximately **0.089 metre**
>
> Note the distractors 0.809, 1.089 and 1.009 - all are digit rearrangements of the correct 0.089, a classic trap. Also note that the given mass 4.9 kg is a **red herring**: it cancels out, because a heavier mass stretches the spring more but also oscillates more slowly, and the two effects exactly compensate.



### J5.5 Cells in series and terminal voltage


- **EMF** - The electromotive force, the voltage a cell produces on open circuit.
- **Internal resistance (r)** - The resistance inside the cell itself.
- **Terminal potential difference** - V = EMF - I r. It is always less than the EMF when current flows.
- **Cells in SERIES** - Total EMF = sum of individual EMFs. Total internal resistance = sum of internal resistances.
- **Cells in PARALLEL (identical)** - Total EMF = EMF of one cell. Total internal resistance = r / n.


> **NOTE: PYQ worked out (this question appeared in Hindi)**
>
> "Two identical cells of emf 1.5 V and internal resistance 0.5 ohm are connected in series. If the current allowed from the cell is 1 A, then the effective terminal potential difference of the cell will be ______."
>
> Answer: **2 V**
>
> Step 1 - combine the cells in series.
> Total EMF = 1.5 + 1.5 = **3 V**
> Total internal resistance = 0.5 + 0.5 = **1 ohm**
>
> Step 2 - apply V = EMF - I r.
> V = 3 - (1 A x 1 ohm) = 3 - 1 = **2 V**
>
> The distractors check specific errors: **1 V** would come from using only one cell (1.5 - 0.5); **0.75 V** from a parallel-connection mistake; **0.5 V** from confusing the internal resistance with the answer.



### J5.6 Magnetism - bar magnet and solenoid


- **Magnetic moment of a bar magnet** - M = m x 2l (pole strength times length).
- **Magnetic moment of a solenoid** - M = N I A (number of turns x current x area).
- **The equivalence principle** - A current-carrying solenoid behaves exactly like a bar magnet. If the two produce the **same magnetic field**, then they must have the **same magnetic moment** - that is precisely what "equivalent" means.


> **NOTE: PYQ worked out**
>
> "The magnetic moment of a bar magnet is _____ the magnetic moment of an equivalent solenoid if the solenoid's magnetic field is _______ that of the bar magnet."
>
> Answer: **equal to ; same as**
>
> The logic is definitional. An "**equivalent** solenoid" means one that reproduces the bar magnet's magnetic behaviour. If the fields are the **same**, the sources must have the **same magnetic moment** - because the external field of a magnetic dipole is determined entirely by its magnetic moment.
>
> So: same field implies equal magnetic moment. The other options ("more than", "less than", "different from") break the equivalence.



## J6 Accountancy and Business Economics Essentials



### J6.1 Basic accounting concepts


- **Double entry system** - Every transaction affects **two** accounts and is recorded with a **DEBIT and a CREDIT** of equal amount. Total debits always equal total credits.
- **Golden rules** - Personal accounts: debit the receiver, credit the giver. Real accounts: debit what comes in, credit what goes out. Nominal accounts: debit expenses and losses, credit incomes and gains.
- **Journal** - The book of original entry, recording transactions chronologically.
- **Ledger** - Accounts classified by head.
- **Trial balance** - A list of all ledger balances, used to check that debits equal credits.


> **NOTE: Direct PYQ**
>
> "According to the double entry system, every transaction will have ______ entries." Options: Right and Left, Up and Down, **Debt and Credit**, Up and Left. Answer: **Debt and Credit** (the paper's spelling of **Debit and Credit**).
>
> Every transaction has a debit side and a credit side of equal value. This is the foundation of all accounting.



### J6.2 Final accounts



| Statement | What it shows | Key output |
|---|---|---|
| Trading account | Buying and selling of goods only | GROSS PROFIT (or gross loss) |
| PROFIT AND LOSS ACCOUNT | All other incomes and expenses | **NET PROFIT** (or net loss) |
| Balance sheet | Assets, liabilities and capital on a particular DATE | The financial POSITION. It is a statement, not an account |



*The two profit formulas*
```
Gross Profit = Net Sales - Cost of Goods Sold (COGS)

  where COGS = Opening Stock + Purchases + Direct Expenses (e.g. Wages)
               - Closing Stock

Net Profit   = Gross Profit + Other Incomes - Indirect Expenses
```



> **NOTE: Direct PYQ**
>
> "Which of the following accounts is/are prepared for net profit?" Answer: **Profit and loss account**.
>
> The trading account gives **gross** profit; the profit and loss account gives **net** profit; the balance sheet shows position rather than profit. Keep the pair straight: **Trading = Gross, P&L = Net.**



### J6.3 Assets, liabilities and capital



| Term | Meaning | Examples |
|---|---|---|
| FIXED ASSETS | LONG-TERM assets held for use in the business for more than one year, not for resale | Land, building, plant and machinery, furniture, vehicles |
| Current assets | Convertible into cash within one year | Cash, bank, debtors, stock, prepaid expenses |
| Tangible assets | Have a physical existence | Building, machinery |
| Intangible assets | No physical existence but have value | Goodwill, patents, trademarks, copyrights |
| Fixed liabilities / Long-term liabilities | Payable after more than one year | Debentures, long-term loans |
| Current liabilities | Payable within one year | Creditors, bills payable, outstanding expenses, income received in advance |
| Capital | The owner's investment in the business | - |
| DRAWINGS | **Any account or goods used by the OWNER of the business for his PERSONAL use.** It reduces capital | Owner takes cash or stock home |


- **Accounting equation** - **Assets = Liabilities + Capital.**
- **WORKING CAPITAL** - **The part of the firm's capital required for conducting DAY-TO-DAY expenses** and short-term operations. Working Capital = Current Assets - Current Liabilities.
- **Fixed capital** - The capital invested in fixed assets.


> **NOTE: Three direct PYQs**
>
> "What is a long-term asset in accounting?" Options: Intangible assets, Current liabilities, Fixed liabilities, **Fixed assets**. Answer: **Fixed assets**. (Note: intangible assets *can* be long-term, but "fixed assets" is the standard term for long-term assets held for use.)
>
> "Any account or goods used by the owner of the business for his personal use is called as:" Options: sales, **drawings**, general expenses, expenses. Answer: **drawings**.
>
> "The part of the firm's capital that is required for conducting day to day expenses is called:" Answer: **working capital**. The phrase "day to day" is the trigger - long-term needs are met by *fixed* capital.



### J6.4 Solved accounting numericals



> **NOTE: PYQ worked out - gross profit on sales**
>
> "During the financial year 2024-25 the total purchases of ABC Limited were Rs. 1,90,000. If ABC Limited's gross profit was 20% on sales and the closing stock was Rs. 30,000 more than the opening stock, what was the gross profit earned during 2024-25?"
>
> Answer: **Rs. 40,000**
>
> Step 1 - work out the cost of goods sold.
> COGS = Opening Stock + Purchases - Closing Stock
>
> We are told Closing Stock = Opening Stock + 30,000. Substituting:
> COGS = Opening + 1,90,000 - (Opening + 30,000)
> = 1,90,000 - 30,000
> = **Rs. 1,60,000**
>
> Notice the opening stock cancels out - we never needed its value.
>
> Step 2 - use the gross profit percentage.
> Gross profit is **20% ON SALES**, so:
> Gross Profit = 0.20 x Sales
> COGS = Sales - Gross Profit = Sales - 0.20 Sales = **0.80 x Sales**
>
> Therefore Sales = COGS / 0.80 = 1,60,000 / 0.80 = **Rs. 2,00,000**
>
> Step 3 - compute the gross profit.
> Gross Profit = 20% of 2,00,000 = **Rs. 40,000**
>
> **The trap in this question:** "20% on sales" is NOT the same as "20% on cost". If it were 20% on cost, the gross profit would be 20% of 1,60,000 = Rs. 32,000. Always check which base the percentage refers to.



> **NOTE: PYQ worked out - loss of stock by fire**
>
> "On 15 December 2024, a fire occurred in the godown of M Ltd., and the entire stock was destroyed. The value of the stock salvaged was Rs. 3,00,000... The value of stock lost by fire was ____."
>
> Answer: **Rs. 6,30,000**
>
> The method for every "stock destroyed by fire" question:
>
> **Step 1** - find the closing stock on the date of the fire, using the trading-account logic:
> Stock on date of fire = Opening Stock + Purchases + Direct Expenses (Wages)
> - Cost of Goods Sold
>
> **Step 2** - find COGS from the sales and the gross profit rate:
> COGS = Sales - Gross Profit = Sales x (1 - gross profit rate)
>
> **Step 3** - subtract what was saved:
> **Stock lost by fire = Stock on date of fire - Stock salvaged**
>
> Here the salvaged stock was Rs. 3,00,000, and applying the above with the figures in the question's table gives a stock-on-hand of Rs. 9,30,000, so the loss is
> 9,30,000 - 3,00,000 = **Rs. 6,30,000**
>
> **Remember the three steps.** Even if the table figures differ in your exam, the structure is always: build up the stock, subtract COGS, then subtract salvage.



> **NOTE: PYQ worked out - income received in advance**
>
> "MC Publications has received rent amounting to Rs. 2,50,000 during the financial year ending 31 March 2024. Out of this Rs. 50,000 represents rent relating to next financial year. The rent account to be credited to the profit and loss account for the year ended 31 March 2024 is ________ and the rent received in advance will be shown as a/an ________."
>
> Answer: **Rs. 2,00,000 ; Liability**
>
> Two accounting principles are being tested.
>
> **First, the accrual (matching) concept.** Only income *earned during this year* may be credited to this year's profit and loss account.
> Rent for this year = 2,50,000 - 50,000 = **Rs. 2,00,000**
>
> **Second, the treatment of income received in advance.** The Rs. 50,000 has been received but not yet earned - the business still *owes* the service (accommodation) for next year. An obligation to provide something is a **LIABILITY**, shown on the liabilities side of the balance sheet as "Rent received in advance" (also called unearned income).
>
> The trap: many candidates mark it as an **asset** because cash came in. Remember that the *cash* is an asset, but the *unearned portion* creates a matching **liability**.



### J6.5 Forms of business organisation



| Form | Ownership | Liability | Members |
|---|---|---|---|
| SOLE PROPRIETORSHIP | ONE person who carries on business BY HIMSELF/HERSELF | UNLIMITED | 1. THE MOST COMMON form of business organisation |
| Partnership | Two or more persons | Unlimited (except LLP) | Minimum 2; maximum 50 under the Companies Act rules |
| Hindu Undivided Family (HUF) | Family members by birth | Karta unlimited, others limited | - |
| Cooperative society | Members, democratic, one member one vote | Limited | Minimum 10 |
| COMPANY (private) | Shareholders; separate legal entity | **LIMITED liability** | Minimum 2, maximum 200 |
| COMPANY (public) | Shareholders; shares freely transferable | LIMITED liability | MINIMUM 7, no maximum |



> **NOTE: Three direct PYQs on business forms**
>
> "The most common type of business organisation is:" Answer: **sole proprietorship** - because it is the easiest and cheapest to start, needs no registration formalities, and covers the vast majority of small shops and traders.
>
> "______ is a person who carries on business by himself/herself." Answer: **Sole proprietorship**.
>
> "Which of the following business structures has limited liability to its members?" Options: Partnership, Cooperative society, **Company**, Sole proprietorship. Answer: **Company**. In a company the members' liability is limited to the unpaid amount on their shares, because the company is a **separate legal person** from its owners. A partnership and a sole proprietorship both carry unlimited liability. (A cooperative society also has limited liability, but "Company" is the standard textbook answer for limited liability.)
>
> "A public company must have at least ______ members." Answer: **7**. Learn the pair: **private company minimum 2, public company minimum 7.**



### J6.6 Business activities and organisation structure



| Sector | Activities |
|---|---|
| Primary | Extraction from nature: agriculture, mining, fishing, forestry |
| Secondary | **MANUFACTURING** and construction - converting raw materials into finished goods |
| Tertiary (services) | Trade, TRANSPORTATION, WAREHOUSING, INSURANCE, banking, advertising, communication - services that AID trade |



> **NOTE: Direct PYQ**
>
> "Which of the following is NOT a tertiary business activity?" Options: Transportation, Warehousing, Insurance, **Manufacturing**. Answer: **Manufacturing**.
>
> Manufacturing is a **secondary** (industrial) activity - it physically makes goods. Transportation, warehousing and insurance are all **auxiliaries to trade**, which is the definition of tertiary/service activity.


- **Organisation structure** - Establishes relationships between **people, work and resources** - who does what work, with what resources, and who reports to whom.
- **Delegation** - Passing authority and responsibility down to a subordinate. **Delegation on a wide scale across the organisation leads to DECENTRALISATION.**
- **Centralisation** - Decision-making authority concentrated at the top.
- **Decentralisation** - Systematic dispersal of decision-making authority to lower levels. It is the *result* of extensive delegation.
- **Authority** - The right to command.
- **Responsibility** - The obligation to perform.
- **Accountability** - Answerability for the outcome. Authority can be delegated; **accountability cannot**.


> **NOTE: Two direct PYQs**
>
> "An organisation structure establishes relationships between:" Answer: **people, work and resources**.
>
> "Which of the following statement is correct for a business organisation?" Options: Responsibility leads to decentralisation / Authority leads to decentralisation / **Delegation leads to decentralisation** / Centralisation leads to autonomy. Answer: **Delegation leads to decentralisation**.
>
> The causal chain: a manager **delegates** authority to a subordinate; when this happens systematically throughout the organisation, decision-making becomes dispersed, which **is** decentralisation. Note that "centralisation leads to autonomy" is the exact opposite of the truth - decentralisation gives autonomy.



### J6.7 Business economics - demand and forecasting


- **Demand** - The quantity of a good consumers are willing AND able to buy at a given price. It is often defined as **effective desire** - desire backed by purchasing power and willingness to spend.
- **Utility** - The satisfaction derived from consuming a good.
- **Law of demand** - Other things being equal, as price rises quantity demanded falls (an inverse relationship).
- **ELASTICITY OF DEMAND** - Measures the **DEGREE** of responsiveness of quantity demanded to a change in price. It explains the **degree** of the correlation between price and quantity. Ed = (percentage change in quantity) / (percentage change in price).
- **Marginal revenue** - The addition to total revenue from selling one more unit. **MR = change in Total Revenue / change in Total Output Quantity.**
- **Marginal cost** - The addition to total cost from producing one more unit. MC = change in Total Cost / change in Output.


> **NOTE: Three direct PYQs**
>
> "Elasticity of demand explains the ______ of the correlation between price and quantity." Options: level, degree and angle / angle / level / **degree**. Answer: **degree**. Elasticity is a *measure of magnitude* - how strongly quantity responds - so "degree" is the right word.
>
> "Marginal revenue is calculated by ______." Answer: **dividing the change in total revenue by the change in total output quantity**. Note the order carefully: revenue change on top, quantity change at the bottom. The distractor that inverts them (quantity divided by revenue) is wrong, and the one using total *cost* defines marginal cost instead.
>
> "What is effective desire?" The paper's key gave **Consumption**. Note that in standard economics, **effective desire is the definition of DEMAND** - desire plus ability plus willingness to pay. If both "Demand" and "Consumption" appear, the theoretically correct answer is **Demand**; this particular key chose Consumption. Be aware of the discrepancy.



#### Methods of demand forecasting


| Method | Description |
|---|---|
| Survey methods | Asking people directly |
| -- Consumer interview / Complete enumeration | Ask all or a sample of consumers about their buying intentions |
| -- OPINION SURVEY (Sales-Force-Composite method / COLLECTIVE OPINION method) | Ask the firm's own SALES STAFF and experts to estimate demand in their territories, then combine those estimates |
| -- Delphi method | Repeated rounds of anonymous expert opinion until consensus |
| Statistical methods | Using past data |
| -- Trend projection | Extend the past trend into the future |
| -- Regression analysis | Model demand as a function of its determinants |
| -- Barometric technique | Use leading indicators |
| Methods for NEW products | Where no past data exists |
| -- EVOLUTIONARY approach | Treat the new product as an EVOLUTION of an existing product and project from the existing product's demand |
| -- SUBSTITUTE approach | Treat the new product as a SUBSTITUTE; the GROWTH OF AN EXISTING PRODUCT is used to estimate demand for the new one |
| -- VICARIOUS approach | Survey consumers indirectly through dealers and retailers |
| -- Growth curve approach | Base the forecast on the growth curve of a similar established product |
| -- Sales experience / test marketing | Launch in a small area first |



> **NOTE: Three direct PYQs on forecasting**
>
> "______ is also referred to as the Sales-Force-Composite method or the Collective Opinion Method." Answer: **Opinion survey**. Both alternative names refer to collecting and combining the *opinions* of the sales force.
>
> "According to business economics, the growth of an existing product is used to estimate the demand for a new product using:" Answer: **substitute approach**. The new product is assumed to substitute for the existing one, so the existing product's growth indicates the new one's potential.
>
> "Which method is used for demand forecasting of new products?" Answer: **Evolutionary approach, opinion polling approach and vicarious approach** (all three). For a brand-new product there is no sales history, so firms use several of these indirect techniques together. When an option lists all the valid methods and the others list only one each, the "all of these" style option is usually correct - provided every item in it is genuinely valid.



### J6.8 Inflation and business types



| Type of inflation | Cause |
|---|---|
| DEMAND-PULL inflation | **DEMAND for goods and services exceeds supply, so demand DRIVES UP PRICES.** "Too much money chasing too few goods" |
| Cost-push inflation | Rising costs of production (wages, raw materials, oil) push prices up, even without extra demand |
| Built-in inflation | Workers demand higher wages to match past inflation, which raises costs, which raises prices - a wage-price spiral |
| Stagflation | High inflation together with high unemployment and stagnant growth |
| Deflation | A general fall in the price level |



> **NOTE: Direct PYQ**
>
> "Which of the following inflations describes how demand for goods and services can drive up their prices?" Options: Cost-push inflation, Built-in Inflation, **Demand-pull inflation**, Demand-push inflation. Answer: **Demand-pull inflation**.
>
> Watch the distractor "**Demand-push** inflation" - it does not exist. The correct pair of terms is **demand-PULL** (demand pulls prices up) and **cost-PUSH** (costs push prices up). Mixing the two words is the most common error.



#### Types of business by driver


> **NOTE: Direct PYQ**
>
> "Which of the following is NOT a type of business?" Options: Experience driven, **Expense driven**, Efficiency driven, Expert driven. Answer: **Expense driven**.
>
> In the knowledge-management and business-strategy literature, businesses are classified as **experience-driven**, **efficiency-driven** and **expert-driven** (based on whether they compete through accumulated experience, operational efficiency, or specialist expertise). "Expense-driven" is not one of these categories - no business is defined by its expenses.



### J6.9 Entrepreneurship and applied mathematics


- **Bootstrapping** - **Self-funding a business using personal resources** - own savings, revenue from early customers, personal credit - rather than raising outside money. The opposite of raising venture capital, bank loans or crowdfunding.
- **Venture capital** - Professional investors funding high-growth start-ups in exchange for equity.
- **Angel investor** - A wealthy individual investing early-stage money.
- **Crowdfunding** - Raising small amounts from many people online.


> **NOTE: Direct PYQ**
>
> "What does the term 'bootstrapping' refer to in the context of starting a business?" Answer: **Self-funding the business using personal resources.** The image behind the word is "pulling yourself up by your own bootstraps" - progressing without outside help. All three distractors involve **external** money (venture capital, bank loans, crowdfunding), which is exactly what bootstrapping avoids.


- **Operations Research (OR)** - The application of **advanced analytical and mathematical methods** - linear programming, queuing theory, simulation, game theory, network analysis - to improve decision-making. It is a branch of **APPLIED MATHEMATICS**.


> **NOTE: Direct PYQ**
>
> "Which of the following comes under applied mathematics?" Options: Information processing, **Operations research**, Management accounting, Organisation. Answer: **Operations research**.
>
> Operations Research is universally classified as applied mathematics - it uses mathematical optimisation and probability models to solve real decision problems. Information processing is computing, management accounting is commerce, and organisation is management theory.




---

# PART K - Teaching Methodology and Child Pedagogy

> *A guaranteed 10 to 20 marks, and the easiest section in the paper. Never leave this for the last day.*



## K1 Growth and Development of the Child



### K1.1 Growth versus development


- **Growth** - **Quantitative** change - increase in size, height, weight, vocabulary count. It is measurable, and it **stops** at a certain age (maturity).
- **Development** - **Qualitative** change - improvement in functioning, skill, understanding and organisation. It is progressive, and it **continues throughout life** ("womb to tomb").
- **Maturation** - The unfolding of characteristics naturally present in the genes, largely independent of practice.
- **Learning** - Change in behaviour due to experience and practice.


### K1.2 Principles of development



| Principle | Meaning |
|---|---|
| Continuous process | Development never stops; it goes on from conception to death |
| Sequential / orderly | It follows a predictable sequence. A child sits before standing, stands before walking |
| Individual differences | Every child develops at their own rate, though the sequence is the same |
| Cephalocaudal | Development proceeds from HEAD to TOE. A baby controls its head before its legs |
| Proximodistal | Development proceeds from the CENTRE of the body OUTWARDS. Shoulder and arm control comes before finger control |
| General to specific | Gross movements come before fine, precise ones |
| Interaction of nature and nurture | Both heredity and environment shape development |
| Not uniform in rate | Some periods are rapid (infancy, adolescence), others slow |
| Interrelated domains | Physical, cognitive, social, emotional and moral development affect each other |
| Predictable but not exactly | The pattern is predictable; the timing is not |



### K1.3 Stages of development



| Stage | Approximate age |
|---|---|
| Prenatal | Conception to birth |
| Infancy / Neonate | Birth to 2 weeks (neonate), then to 2 years |
| Early childhood | 2 to 6 years - the "preschool" or "toy age" |
| Late childhood | 6 to 12 years - the "gang age", "elementary school age" |
| ADOLESCENCE | 12 to 19 years - the period of storm and stress |
| Adulthood | 20 years onwards |



### K1.4 The senses of the newborn


Newborn abilities are asked directly and precisely, so learn these numbers.


| Ability | Status at birth |
|---|---|
| Hearing | Functional; responds to sound. Recognises the mother's voice within days |
| Vision | The WEAKEST sense at birth. Visual acuity is poor (about 20/400 to 20/600); focal distance about 8 to 12 inches - roughly the distance to the mother's face while feeding |
| AUDITORY-VISUAL CO-ORDINATION | **PRESENT FROM BIRTH.** A newborn turns its head and eyes toward the source of a sound |
| Smell and taste | Well developed; prefers sweet, and recognises the mother's smell |
| Touch | Highly developed; the most mature sense at birth |
| Colour vision | Poorly developed at birth; adult-like by about 4 months |
| Depth perception | Develops around 6 months |



> **NOTE: Direct PYQ**
>
> "Auditory and visual co-ordination system is present in child from ______." Options: **Birth**, 3 weeks of birth, 6 days of birth, 6 months of birth. Answer: **Birth**.
>
> A newborn placed in a dark room will turn its head and eyes toward a sound - this reflexive linking of hearing and looking is present immediately at birth. It is an innate ability, not a learned one.



> **NOTE: PYQ worked out - newborn visual acuity**
>
> "Which of the following statement is correct regarding vision of new-born babies?
> I. Neonates can discriminate between stationary black and white stripe which is 1/8 of an inch wide.
> II. By three months babies can see stripes as narrow as 1/64th of an inch wide."
>
> Answer: **Both I and II**
>
> These are standard findings from research on infant visual acuity (using preferential-looking methods). The two figures show the dramatic rate of improvement:
> - At **birth**, a neonate can just distinguish stripes about **1/8 inch** wide.
> - By **three months**, acuity has improved roughly eight-fold, to stripes as narrow as **1/64 inch**.
>
> Learn the pair of fractions **1/8 at birth** and **1/64 by three months**, and note the direction: vision gets sharper, so the number in the denominator gets larger.



### K1.5 The brain and language areas



| Area | Hemisphere | Function |
|---|---|---|
| BROCA'S AREA | LEFT hemisphere, frontal lobe | Speech PRODUCTION. Damage causes Broca's (expressive) aphasia - the person understands but cannot speak fluently |
| WERNICKE'S AREA | LEFT hemisphere, temporal lobe | Language COMPREHENSION. Damage causes Wernicke's (receptive) aphasia - fluent but meaningless speech, poor understanding |
| Left hemisphere generally | - | Language, logic, analysis, mathematics, sequencing |
| Right hemisphere generally | - | Spatial ability, music, art, creativity, emotion, holistic thinking |
| Corpus callosum | - | The bundle of fibres connecting the two hemispheres |
| Cerebellum | - | Balance and coordination of movement |
| Hippocampus | - | Formation of long-term memory |
| Amygdala | - | Emotion, especially fear |



> **NOTE: Direct PYQ**
>
> "Broca's area and Wernicke's area are concerned with language. These are the areas of ______. I. right hemisphere of brain. II. left hemisphere of brain."
>
> Answer: **Only II** (the LEFT hemisphere).
>
> In about 95% of right-handed people, language is **lateralised to the left hemisphere**. Both Broca's area (production) and Wernicke's area (comprehension) sit in the left hemisphere.
>
> Memory hook: **L**eft hemisphere for **L**anguage and **L**ogic.



### K1.6 Health and nutrition



| Condition | Caused by / Associated with |
|---|---|
| Obesity | Excess body fat. Leads to HIGH BLOOD PRESSURE, TYPE 2 DIABETES, heart disease, ORTHOPEDIC (joint and bone) PROBLEMS, sleep apnoea, some cancers |
| AIDS | **Caused by the HIV VIRUS**, transmitted through blood, unprotected sex, shared needles and mother to child. It has NOTHING to do with obesity |
| Malnutrition | Deficiency, excess or imbalance of nutrients |
| Anaemia | Iron deficiency - very common in Indian schoolchildren |
| Marasmus and Kwashiorkor | Severe protein-energy malnutrition |
| Night blindness | Vitamin A deficiency |
| Rickets | Vitamin D deficiency |
| Scurvy | Vitamin C deficiency |
| Goitre | Iodine deficiency |
| Beri-beri | Vitamin B1 (thiamine) deficiency |



> **NOTE: Direct PYQ**
>
> "Which of the following ailments is NOT caused by obesity?" Options: High blood pressure, **AIDS**, Orthopedic problem, Diabetes. Answer: **AIDS**.
>
> AIDS is an **infectious disease caused by the HIV virus**. Obesity is a metabolic condition. High blood pressure, orthopaedic problems and type 2 diabetes are all well-established consequences of obesity, but no amount of body weight can cause a viral infection.



## K2 Theories of Development



### K2.1 Piaget's theory of cognitive development


Jean Piaget (Swiss) studied **how children think**, not how much they know. His central idea: children are **little scientists** who actively construct their own understanding of the world.


| Key term | Meaning |
|---|---|
| Schema | A mental framework or "file" for organising knowledge |
| Assimilation | Fitting NEW information into an EXISTING schema. A child who knows "dog" calls a cat "dog" |
| Accommodation | CHANGING the schema to fit new information. The child learns that cats are a different category |
| Equilibration | The drive to balance assimilation and accommodation |
| Adaptation | Assimilation plus accommodation together |



#### The four stages


| Stage | Age | Key features |
|---|---|---|
| Sensorimotor | 0 to 2 years | Learns through senses and movement. Develops OBJECT PERMANENCE (around 8 months) - knowing a thing still exists when hidden. Ends with the beginning of symbolic thought |
| Pre-operational | 2 to 7 years | Symbolic play and language explode. Marked by EGOCENTRISM (cannot take another's viewpoint), CENTRATION (focusing on one feature only), lack of CONSERVATION, animism, irreversibility |
| Concrete operational | 7 to 11 years | Logical thinking about CONCRETE objects. Achieves CONSERVATION, reversibility, classification, seriation, and DECENTRATION. Cannot yet handle abstract hypotheticals |
| FORMAL OPERATIONAL | 11 or 12 years onwards | ABSTRACT, hypothetical and deductive reasoning. Can think about possibilities, use scientific reasoning, and reason about ideas rather than objects |



> **NOTE: Direct PYQ**
>
> "Piaget's formal operational stage begins at approximately ______." Options: **11 years**, 14 years, 8 years, 7 years. Answer: **11 years**.
>
> Learn the four boundary ages as a chain: **0 - 2 - 7 - 11**. Sensorimotor 0 to 2, Pre-operational 2 to 7, Concrete operational 7 to 11, Formal operational 11 onwards.



#### Conservation and horizontal decalage

- **Conservation** - Understanding that a quantity stays the same even when its appearance changes - the same water poured into a taller, thinner glass is still the same amount. Achieved in the **concrete operational** stage.
- **Types of conservation** - Number, liquid/volume, mass, length, area, weight. They are **not all acquired at the same time** - number conservation typically comes around 6, mass around 7, and weight and volume later, around 9 to 11.
- **HORIZONTAL DECALAGE** - **The INCONSISTENCY in the development of DIFFERENT TYPES OF CONSERVATION** (or of different tasks) within the same stage. A child may conserve number but not yet volume, even though both belong to the concrete operational stage.
- **Vertical decalage** - The reappearance of a similar ability at a higher, more abstract level in a later stage.


> **NOTE: Direct PYQ**
>
> "Inconsistency in the development of different type of conservation is called ______." Options: **Horizontal Decalage**, Meta-cognition, Selective attention, Immersion. Answer: **Horizontal Decalage**.
>
> Decode the term: *decalage* is French for "gap" or "discrepancy"; *horizontal* means within the same level/stage. So it is a gap **across tasks at the same stage** - exactly the definition. Note the distractors: **metacognition** is thinking about one's own thinking; **selective attention** is focusing on relevant stimuli; **immersion** is a language-teaching approach.



### K2.2 Vygotsky's socio-cultural theory


Lev Vygotsky (Russian) emphasised that cognitive development is fundamentally **social** - children learn through interaction with more knowledgeable others, and **culture and language** are the main tools of thought.


| Concept | Meaning |
|---|---|
| ZPD - Zone of Proximal Development | The gap between what a learner can do **ALONE** and what they can do **WITH GUIDANCE** from a more capable person. Teaching should target this zone |
| SCAFFOLDING | The temporary, adjustable support a teacher or peer provides, gradually withdrawn as the learner becomes competent (the term was coined by Wood, Bruner and Ross, building on Vygotsky) |
| MKO - More Knowledgeable Other | Anyone with greater understanding: teacher, parent, older child, peer |
| Private / Inner speech | Children first talk aloud to guide themselves, then this speech becomes internal thought |
| Language | Both a tool for communication and the primary instrument of thinking |
| Social interaction | The origin of all higher mental functions |



> **TIP: Piaget versus Vygotsky - a very common comparison question**
>
> **Piaget:** development leads learning. The child is a solitary little scientist. Stages are universal and largely biological. Language follows thought.
>
> **Vygotsky:** learning leads development. The child is a social apprentice. Culture shapes development, so it varies between societies. Language drives thought.



### K2.3 Erikson's psychosocial theory


Erik Erikson proposed **eight stages** covering the whole lifespan. Each stage presents a **crisis** or conflict that must be resolved.


| Stage | Age | Crisis | Virtue if resolved |
|---|---|---|---|
| 1 | 0 to 1 year | Trust vs Mistrust | Hope |
| 2 | 1 to 3 years | Autonomy vs Shame and Doubt | Will |
| 3 | 3 to 6 years | Initiative vs Guilt | Purpose |
| 4 | 6 to 12 years | Industry vs Inferiority | Competence |
| 5 | 12 to 19 years | IDENTITY vs ROLE CONFUSION | Fidelity |
| 6 | 20 to 40 years | Intimacy vs Isolation | Love |
| 7 | 40 to 65 years | Generativity vs Stagnation | Care |
| 8 | 65 and above | Integrity vs Despair | Wisdom |



### K2.4 Marcia's identity statuses


James Marcia extended Erikson's fifth stage. He classified adolescents on two dimensions: whether they have **explored** alternatives, and whether they have made a **commitment**.


| Status | Exploration | Commitment | Description |
|---|---|---|---|
| Identity DIFFUSION | No | No | Neither exploring nor committed. Directionless, apathetic, avoids the issue |
| Identity FORECLOSURE | No | Yes | Committed WITHOUT exploring - has simply adopted the identity handed down by parents or society |
| IDENTITY MORATORIUM | YES (in progress) | Not yet | **Actively EXPERIMENTING and SEARCHING FOR ALTERNATIVES**, in the middle of the struggle to establish an identity. A delay or "time out" while exploring |
| Identity ACHIEVEMENT | Yes (completed) | Yes | Has explored the options AND arrived at a firm personal commitment |



> **NOTE: Direct PYQ**
>
> "The given statement is referring to which type of identity status in adolescents? 'Experimenting and actively searching for alternatives in their struggle to establish their identity.'"
>
> Answer: **Identity moratorium**.
>
> The trigger words are "**experimenting**" and "**actively searching**" - exploration is happening but no commitment has been reached yet. Contrast the three others: **diffusion** has no exploration and no commitment; **foreclosure** has commitment without exploration; **achievement** has finished exploring and settled.
>
> The word *moratorium* itself means a temporary pause or delay - the adolescent has pressed pause on commitment while trying things out.



### K2.5 Kohlberg's stages of moral development


Lawrence Kohlberg used moral dilemmas (famously the "Heinz dilemma") and found **three levels, each with two stages**. What matters is the **reasoning**, not the choice made.


| Level | Stage | Basis of moral reasoning |
|---|---|---|
| PRE-CONVENTIONAL (up to about 9 years) | 1. Punishment and obedience | "I will be punished if I do it." Obeys to avoid punishment |
| - | 2. Instrumental relativist / Individualism | "What is in it for me?" Self-interest and simple exchange |
| CONVENTIONAL (adolescence) | 3. Good boy - good girl | "I want others to approve of me." Conformity to social expectations |
| - | 4. Law and order | "It is my duty; rules must be maintained for society to function" |
| POST-CONVENTIONAL (adulthood, and not all reach it) | 5. Social contract | Laws are social agreements that can be changed if they do not serve the greater good |
| - | 6. Universal ethical principles | Abstract principles of justice and human rights, even if they conflict with the law |



### K2.6 Neo-Freudian theories


- **Freud's psychoanalytic theory** - Id (pleasure principle), Ego (reality principle), Superego (morality). Psychosexual stages: oral, anal, phallic, latency, genital. Emphasised unconscious sexual drives.
- **Neo-Freudians** - Followers who **kept Freud's emphasis on the unconscious and early experience but rejected his focus on sexuality**, stressing instead **social and interpersonal** factors.


| Neo-Freudian | Contribution |
|---|---|
| Erik ERIKSON | Psychosocial development in EIGHT stages across the lifespan |
| Harry Stack SULLIVAN | INTERPERSONAL theory - personality develops through interpersonal relationships |
| Karen Horney | Basic anxiety; challenged Freud's views on women |
| Alfred Adler | Individual psychology; inferiority complex; striving for superiority |
| Carl Jung | Analytical psychology; collective unconscious; archetypes |
| Anna Freud | Ego psychology and defence mechanisms |



> **NOTE: PYQ worked out - read this question very carefully**
>
> "Which of the following is NOT a Neo-Freudian Theory of Development?
> I. Henry Stack Sullivan's Interpersonal Theory
> II. Erik Erikson Theory of Psycho-social Development"
>
> Answer: **Neither I nor II**
>
> Reasoning: the question asks which is **NOT** Neo-Freudian. In fact **BOTH** Sullivan's interpersonal theory and Erikson's psychosocial theory **ARE** genuine Neo-Freudian theories. Therefore neither of them qualifies as "not Neo-Freudian", and the correct response is **Neither I nor II**.
>
> This is a **double-negative** question, and they trap careless readers. Technique: first decide the truth of each statement, then apply the question's negation.
> - Is Sullivan Neo-Freudian? YES.
> - Is Erikson Neo-Freudian? YES.
> - The question wants the ones that are NOT. Neither qualifies. So "Neither I nor II".



### K2.7 Language development



| Crying | Birth | Undifferentiated then differentiated |
|---|---|---|
| Cooing | 2 to 4 months | Vowel-like sounds |
| Babbling | 6 to 9 months | Consonant-vowel repetition: "ba-ba-ba" |
| Holophrastic / One-word | 12 months | A single word carries a whole sentence's meaning |
| Telegraphic speech | 2 years | Two or three words with function words omitted: "mummy go shop" |
| Complex sentences | 3 to 5 years | Grammar rapidly matures |



#### Over-generalisation and under-generalisation - a classic trap

- **OVER-generalisation (over-extension)** - Applying a word **TOO BROADLY**, to more things than it should cover. A child calling **all four-legged animals "doggie"** is over-generalising - the category has been stretched too wide.
- **UNDER-generalisation (under-extension)** - Applying a word **TOO NARROWLY**. A child using "**duck**" only for **his own toy duck** and not for real ducks is under-generalising - the category is too small.
- **Over-regularisation** - Applying a grammar rule too rigidly: "goed" instead of "went", "foots" instead of "feet".


> **NOTE: PYQ worked out**
>
> "Which of the following is correctly matched?
> I. A child calling all four legged animals doggie - under-generalization
> II. A child using word 'duck' for only his toy duck - over-generalizing"
>
> Answer: **Neither I nor II**
>
> Both statements have the labels **swapped**:
> - Calling **all** four-legged animals "doggie" applies the word too broadly, so it is **OVER**-generalisation - but statement I calls it under-generalisation. **WRONG.**
> - Using "duck" for **only** one toy applies the word too narrowly, so it is **UNDER**-generalisation - but statement II calls it over-generalising. **WRONG.**
>
> Since both matchings are incorrect, the answer is "Neither I nor II".
>
> **Memory hook:** OVER = too many things covered (over-extended, spread too wide). UNDER = too few things covered (under-extended, too narrow).



### K2.8 Parenting styles


Diana Baumrind's classification, based on two dimensions: **demandingness** (control) and **responsiveness** (warmth).


| Style | Control | Warmth | Typical child outcome |
|---|---|---|---|
| AUTHORITATIVE (best) | High | High | Clear rules WITH explanation and warmth; a GIVE-AND-TAKE relationship. Children are socially competent, confident, self-reliant, high achievers, and show the SAME reciprocal give-and-take relationship with their PEERS |
| Authoritarian | High | Low | Strict, harsh, "because I said so", power-assertive. Children are anxious, withdrawn, low in self-esteem, and often use COERCIVE tactics with peers |
| Permissive / Indulgent | Low | High | Warm but few rules or demands. Children are impulsive, demanding, lack self-control |
| Neglectful / Uninvolved | Low | Low | Neither warmth nor control. Poorest outcomes on every measure |



> **NOTE: PYQ worked out**
>
> "In the context of Parenting, which of the following is correctly matched?"
>
> Answer: **Give and take relationship of parents - Children show same relationship with peer.**
>
> Why this is right: children **model** the interaction style they experience at home. Parents who practise reciprocal, respectful give-and-take (the authoritative style) raise children who carry that same reciprocity into peer friendships.
>
> Why the others are wrong as matched:
> "Clearly communicating parent - Child being less liked" - reversed. Clear communication produces children who are **more** liked and socially skilled.
> "Power assertive parents - Coercive tactics in peer used by child" - this statement is actually **conceptually true** (power-assertive parenting does breed coercive peer behaviour), which makes it a strong distractor. The paper's key chose the give-and-take option as the correctly matched pair, so read all four and pick the clearest, most direct modelling relationship.
> "Parents being harsh - Unattractive social behavior of child" - the direction is right in spirit but vaguely worded.



## K3 Learning, Teaching and Lesson Planning



### K3.1 Learning theories



| Theory | Key figure | Core idea |
|---|---|---|
| Classical conditioning | PAVLOV | Learning by ASSOCIATION. A neutral stimulus (bell) paired with a natural one (food) comes to produce the response (salivation) |
| Operant conditioning | SKINNER | Learning by CONSEQUENCES. Behaviour followed by reinforcement increases; behaviour followed by punishment decreases. Introduced programmed learning |
| Trial and error / Connectionism | THORNDIKE | Laws of Readiness, Exercise and EFFECT. Learning is forming stimulus-response bonds |
| Insight learning / Gestalt | KOHLER | Learning by suddenly perceiving the WHOLE pattern - the "aha!" moment. Kohler's chimpanzee experiments |
| Observational / Social learning | BANDURA | Learning by OBSERVING and IMITATING models. The Bobo doll experiment. Involves attention, retention, reproduction, motivation |
| CONSTRUCTIVISM | PIAGET, VYGOTSKY, Bruner | Learners actively CONSTRUCT their own knowledge from experience rather than passively receiving it |
| Discovery learning | BRUNER | Learners discover principles for themselves. Spiral curriculum; enactive, iconic and symbolic modes |
| Meaningful verbal learning | AUSUBEL | Advance organisers link new material to existing knowledge |
| Hierarchy of needs | MASLOW | Physiological, safety, love/belonging, esteem, self-actualisation. Motivation drives learning |
| Multiple intelligences | GARDNER | Eight (or nine) distinct intelligences: linguistic, logical-mathematical, spatial, musical, bodily-kinesthetic, interpersonal, intrapersonal, naturalistic |
| Triarchic theory of intelligence | STERNBERG | Analytical, creative and practical intelligence |
| EXPERIENTIAL learning | KOLB | Learning through a four-stage CYCLE of concrete experience, reflective observation, abstract conceptualisation and active experimentation |



### K3.2 Kolb's experiential learning and learning styles


David Kolb's model is explicitly built on **experiential learning** - the idea that knowledge is created through the transformation of experience.


*Kolb's four-stage learning cycle*
```
        CONCRETE EXPERIENCE  ("doing / having an experience")
                 |
                 v
        REFLECTIVE OBSERVATION  ("reviewing / reflecting on it")
                 |
                 v
        ABSTRACT CONCEPTUALISATION  ("concluding / learning from it")
                 |
                 v
        ACTIVE EXPERIMENTATION  ("planning / trying out what was learned")
                 |
                 +----> back to Concrete Experience (the cycle repeats)
```



| Kolb learning style | Combination | Learns best by |
|---|---|---|
| Diverging | Concrete experience + Reflective observation | Watching and feeling; brainstorming; imaginative |
| Assimilating | Reflective observation + Abstract conceptualisation | Logical theory; concise, well-organised explanation |
| Converging | Abstract conceptualisation + Active experimentation | Practical application; solving technical problems |
| Accommodating | Active experimentation + Concrete experience | Hands-on doing; intuition; trial and error |



> **NOTE: Direct PYQ**
>
> "David Kolb's model of learning style is based on which type of learning?" Options: Inquiry-based learning, Integrative learning, Collaborative learning, **Experiential learning**. Answer: **Experiential learning**.
>
> Kolb's own definition is that "learning is the process whereby knowledge is created through the transformation of **experience**". The word *experiential* is built into the theory's name and identity.



### K3.3 Approach, method, strategy and technique


These four words are distinguished in one of the papers, so learn the hierarchy precisely.


| Term | Definition | Level |
|---|---|---|
| APPROACH | A **SYSTEMATIC / METHODICAL** framework of beliefs and assumptions about how learning happens. It **suggests a logical and well-organised sequence of activities** and **follows more/definite steps**. It is the broadest, most theoretical level | Broadest - philosophy |
| Method | The overall plan for orderly presentation of material, consistent with the chosen approach. Lecture method, project method, discussion method | Middle - plan |
| Strategy | A carefully devised plan of action to achieve a specific learning goal | Middle |
| Technique | The actual classroom implementation - a specific trick, activity or device used in the moment. Questioning, role play, using a chart | Narrowest - practice |



> **NOTE: Direct PYQ (this question appeared in Hindi)**
>
> "________ is a methodical approach. It suggests a logical and well-organised sequence of activities. It follows more steps." Options: teaching strategy, teaching method, teaching technique, **teaching approach**. Answer: **teaching approach** (shikshan upagam).
>
> The trigger phrase is "**methodical approach**" combined with "logical and well-organised sequence" and "more/definite steps" - describing the broad, systematic framework, which is the **approach**. A technique is the narrowest and most immediate of the four, so it cannot be the answer.



### K3.4 Teaching methods



| Method | Description | Best for |
|---|---|---|
| Lecture method | Teacher talks, students listen. Teacher-centred | Covering a lot of content quickly; large groups |
| Demonstration method | Teacher shows how something is done | Practical skills, science experiments |
| HEURISTIC method | The student **DISCOVERS** knowledge himself by acting as an investigator, with the teacher only setting problems and guiding. "Heuriskein" is Greek for "I find". Introduced by **HENRY EDWARD ARMSTRONG** for teaching SCIENCE | Developing scientific attitude and independent enquiry |
| Project method | Students undertake a purposeful real-life task in a social environment. Proposed by **KILPATRICK**, based on **DEWEY's** pragmatism | Integration across subjects; life skills |
| Problem-solving method | Students work through a defined problem systematically | Higher-order thinking |
| Inductive method | Moves from SPECIFIC examples to a GENERAL rule | Discovering formulas and principles |
| Deductive method | Moves from the GENERAL rule to SPECIFIC examples | Applying and practising known rules |
| Discussion method | Guided exchange of views among students | Attitudes, controversial topics, reasoning |
| Discovery / Inquiry-based learning | Students investigate questions themselves | Conceptual depth, motivation |
| Collaborative / Cooperative learning | Students work in small groups toward a shared goal, with individual accountability | Social skills, peer teaching |
| Programmed instruction | Material broken into small steps with immediate feedback. Based on Skinner | Self-paced learning |
| Team teaching | Two or more teachers plan and teach together | Sharing expertise |
| Micro-teaching | Practising ONE teaching skill on a small group for a short time, then getting feedback and re-teaching | Teacher training |



> **NOTE: Direct PYQ**
>
> "Heuristic method of teaching science was introduced by______." Options: William James, **Henry Edward Armstrong**, Lev Vygotsky, Abraham Maslow. Answer: **Henry Edward Armstrong**.
>
> Armstrong was an English **chemist** who argued that students should learn science by behaving like scientists - investigating and discovering rather than being told. Remember the pairing: **Armstrong - Heuristic - Science.**
>
> Do not confuse with: **Kilpatrick - Project method**, **Dewey - Learning by doing / pragmatism**, **Montessori - self-directed activity for young children**, **Froebel - Kindergarten and play**, **Skinner - Programmed instruction**.



### K3.5 Teacher-centred versus learner-centred education



| Point | Teacher-centred | LEARNER / STUDENT-CENTRED |
|---|---|---|
| Focus | The teacher and the content | The learner and the learning process |
| Role of teacher | Authority, transmitter of knowledge | FACILITATOR, guide, co-learner |
| Role of student | Passive receiver | ACTIVE CONSTRUCTOR OF MEANING - the "meaning maker" |
| Method | Lecture, dictation, rote memorisation | Activity, discussion, projects, discovery, group work |
| View of knowledge | Fixed body of facts to be transmitted | Constructed by the learner from experience |
| Assessment | Mainly summative tests | Continuous, formative, includes self and peer assessment |
| Underlying theory | Behaviourism | CONSTRUCTIVISM |



> **NOTE: Direct PYQ**
>
> "When learning is meaning making, then students are the meaning makers. The learning process in this context is ________." Options: **student-centred**, teacher-centred, society-centred, subject-centred. Answer: **student-centred**.
>
> The logic is in the sentence itself: if the **students** are the ones making meaning, then the process revolves around the **students**. This is the constructivist view of learning, and its instructional form is student-centred (learner-centred) education.



### K3.6 Lesson planning - Herbartian steps


Johann Friedrich **Herbart** gave the classic five formal steps of a lesson plan.


| Step | What the teacher does |
|---|---|
| 1. PREPARATION / Motivation | Prepares the students' minds - tests previous knowledge, asks introductory questions, creates interest, and states the aim |
| 2. PRESENTATION | Presents the new material with the students' active involvement, using examples and teaching aids. The main body of the lesson |
| 3. ASSOCIATION / Comparison | Compares and links the new knowledge with what the students already know, and with related examples |
| 4. GENERALISATION | Draws out the general rule, principle, formula or definition from the specific instances discussed |
| 5. APPLICATION | Students APPLY the newly learned rule to new situations and problems, which confirms understanding |



> **NOTE: PYQ worked out (this question appeared in Hindi)**
>
> "Which of the following is NOT one of the five steps of Herbartian lesson planning?" Options: Association (sambaddhata), Presentation (prastuti), Application (anuprayog), **Evaluation (mulyankan)**. Answer: **Evaluation**.
>
> The five Herbartian steps are **Preparation, Presentation, Association, Generalisation, Application**. **Evaluation** is NOT one of them - it was added later in modern lesson-plan formats (and appears in the Bloom/RCEM and other models), but Herbart's original five do not include it.
>
> Memory hook for the five: "**P**lease **P**resent **A**nd **G**eneralise the **A**pplication" - P, P, A, G, A.



### K3.7 Unit plan and yearly plan


- **Lesson plan** - A plan for ONE period / one lesson.
- **UNIT plan** - A plan for a complete **unit** of the syllabus, covering several lessons over days or weeks, organised around a central theme.
- **Yearly / Annual plan** - The distribution of the whole syllabus across the academic year.


#### Steps in preparing a unit plan

1. **Formation of proper units and sub-units** if they are not already prescribed in the syllabus.
2. Statement of the unit's objectives in behavioural terms.
3. Selection and organisation of the content.
4. Selection of teaching methods, activities and materials.
5. **Determination of the methods of assessment / evaluation.**
6. Provision for remedial and enrichment work.


> **NOTE: PYQ worked out**
>
> "For preparing a unit plan, which of the following procedure is followed?
> I. Formation of proper units and sub-units if not prescribed in the syllabus.
> II. Determination of methods of assessment."
>
> Answer: **Both I and II**
>
> Both are genuine steps. A unit plan must first **define its boundaries** - and if the syllabus has not already divided the content into units, the teacher must do so (statement I). It must also specify **how learning will be assessed**, because objectives and assessment must be aligned (statement II).
>
> General tip for "Both I and II" style questions: check each statement independently. If you cannot find anything actually wrong with a statement, do not reject it merely because it sounds obvious.



### K3.8 Classroom management and seating



| Situation | Appropriate seating / arrangement |
|---|---|
| Child with special needs (visual or hearing impairment) | Seated NEAR THE BOARD and near the teacher, in the front |
| Group work | Seating in CLUMPS or CLUSTERS so each small group faces one another |
| Group discussion | A CIRCLE or horseshoe/U-shape, so the teacher can maintain EYE CONTACT WITH EVERY CHILD and children can see one another |
| Lecture / demonstration | Rows facing the front, so every child has a clear view of the board |
| Performing arts (dance, drama, music) | An OPEN SPACE with room to move - a stage or cleared floor area. A "clear view of the board" is irrelevant here, because performing arts do not depend on the board |



> **NOTE: PYQ worked out**
>
> "Which of the following statement is NOT correctly matched?" Answer: **Performing art - every child should have clear view of board.**
>
> Reasoning: **performing arts** require open floor space for movement, performance and observation of one another - not a view of the blackboard. The board is essentially irrelevant to a dance or drama activity, so this pairing is wrong.
>
> The other three are all correctly matched: a child with special needs *should* sit near the board; group work *does* need clustered seating; and in a group discussion the teacher *should* maintain eye contact with every child.



## K4 Assessment and Evaluation



### K4.1 Types of assessment



| Type | Purpose | When |
|---|---|---|
| Placement assessment | To decide the right starting point or group for a learner | Before instruction |
| DIAGNOSTIC assessment | To **IDENTIFY specific learning difficulties, gaps and MISCONCEPTIONS** and their causes, so that remedial teaching can be planned | Before or during instruction |
| Formative assessment | To monitor learning and give feedback while teaching is still going on, so that teaching can be adjusted. Assessment **FOR** learning | During instruction, continuous |
| Summative assessment | To judge and certify the final level of achievement; produces marks or grades. Assessment **OF** learning | At the end of a term or course |
| Prognostic assessment | To predict future performance | Before |



> **NOTE: Direct PYQ**
>
> "Diagnostic assessment mainly helps in which of the following?" Options: Grading performance, Standardising content, Promoting learners, **Identifying misconceptions**. Answer: **Identifying misconceptions**.
>
> The word *diagnostic* comes from medicine - a diagnosis finds out **what exactly is wrong** so that the right treatment can be given. In teaching, that means locating the precise misconception or gap. **Grading** and **promoting** learners are functions of **summative** assessment.


- **CCE** - **Continuous and Comprehensive Evaluation** - continuous (throughout the year, not one final exam) and comprehensive (covering both scholastic and co-scholastic areas: academics plus attitudes, values, health, arts and life skills).
- **Norm-referenced test** - Compares a student against other students (rank in class). Produces a spread of scores.
- **Criterion-referenced test** - Compares a student against a fixed standard or learning outcome, regardless of others.
- **Reliability** - Consistency - the test gives the same result on repetition.
- **Validity** - The test measures what it claims to measure. A test can be reliable without being valid, but not valid without being reliable.
- **Objectivity** - Different examiners award the same marks to the same answer.
- **Portfolio assessment** - A collected body of a student's work over time, showing growth.
- **Rubric** - A scoring guide listing criteria and performance levels.
- **Open book examination** - Tests understanding and application rather than memory.


### K4.2 Bloom's taxonomy



| Domain | What it covers | Levels (lowest to highest) |
|---|---|---|
| COGNITIVE | Knowledge and intellectual skills | Original: Knowledge, Comprehension, Application, Analysis, Synthesis, Evaluation. REVISED (Anderson): Remembering, Understanding, Applying, Analysing, Evaluating, CREATING (creating is now the highest) |
| AFFECTIVE | Attitudes, values, feelings, interests | Receiving, Responding, Valuing, Organising, Characterising |
| PSYCHOMOTOR | Physical and manipulative skills | Imitation, Manipulation, Precision, Articulation, Naturalisation |



### K4.3 ICT-based assessment


**ICT** stands for **Information and Communication Technology**. An assessment method counts as ICT-based only if a computer or digital device is essential to it.


| ICT-based assessment methods | Non-ICT methods |
|---|---|
| Computer-based / online testing | Writing a reflection journal ON PAPER |
| Concept map construction using software | Paper-and-pencil written examination |
| Multimedia program development by students | Oral questioning |
| E-portfolios and blogs | Practical demonstration in a lab |
| Digital simulations and virtual labs | Observation with a paper checklist |
| Online quizzes with automatic feedback | Peer discussion |
| Learning analytics from an LMS | - |



> **NOTE: Direct PYQ**
>
> "All of the given are the methods of Information and Communication Technology-based assessment except ______." Options: Concept map construction, **Writing reflection journal on paper**, Multimedia program development, Computer-based testing. Answer: **Writing reflection journal on paper**.
>
> The decisive words are "**on paper**". A reflection journal *could* be an ICT method if kept as a blog or digital document - but written on paper it involves no technology at all. Examiners insert such qualifying phrases deliberately, so read every option to the end.



## K5 Inclusive Education and Educational Policies



### K5.1 Inclusive education


- **Inclusive education** - Educating **ALL** children, including those with disabilities and from disadvantaged groups, **together in the same regular/mainstream classroom**, with the system adapting to meet each child's needs.
- **Integrated education** - Children with disabilities are placed in regular schools but must adjust to the existing system, often with a separate resource room.
- **Segregated / Special education** - Children with disabilities are taught in entirely separate special schools.
- **The essential difference** - In **integration** the CHILD adapts to the school. In **INCLUSION** the SCHOOL adapts to the child.


#### Types of children with special needs (CWSN)

Visual impairment, hearing impairment, speech and language disability, locomotor disability, intellectual disability, specific learning disabilities (**dyslexia** - reading, **dysgraphia** - writing, **dyscalculia** - arithmetic), autism spectrum disorder, ADHD, cerebral palsy, multiple disabilities. Also gifted and talented children, who equally need special provision.


### K5.2 Key legislation and programmes - learn every year



| Year | Policy / Act / Programme | Key point |
|---|---|---|
| 1948-49 | University Education Commission | Radhakrishnan Commission - higher education |
| 1952-53 | Secondary Education Commission | Mudaliar Commission |
| 1964-66 | Education Commission | KOTHARI Commission. Recommended 6% of GDP on education and the 10+2+3 pattern |
| 1968 | First National Policy on Education | Based on the Kothari Commission |
| 1986 | National Policy on Education (NPE) | Operation Blackboard; Navodaya Vidyalayas; emphasis on equality |
| 1987 | Operation Blackboard | Minimum essential facilities in every primary school |
| 1992 | Programme of Action | Revised NPE 1986 |
| 1994 | Salamanca Statement (UNESCO) | The international declaration that established INCLUSIVE education as the goal |
| 1994 | DPEP - District Primary Education Programme | Launched to universalise primary education, district by district |
| 1997 | Inclusive education added to DPEP | **The philosophy of inclusive education was incorporated into DPEP in 1997** |
| 1995 | Persons with Disabilities (PwD) Act | 3% reservation; free education up to 18 years for children with disabilities |
| 1999 | National Trust Act | For autism, cerebral palsy, mental retardation and multiple disabilities |
| 2000 | SSA - Sarva Shiksha Abhiyan | Universalisation of elementary education (6-14 years) |
| 2001 | IEDC / IEDSS | Integrated Education for Disabled Children / at Secondary Stage |
| 2002 | 86th Constitutional Amendment | Inserted **Article 21A** making free and compulsory education for 6-14 year olds a FUNDAMENTAL RIGHT |
| 2005 | National Curriculum Framework (NCF) | "Learning without burden"; constructivism; child-centred education |
| 2009 | RTE Act - Right of Children to Free and Compulsory Education Act | Passed 2009, came into force **1 April 2010**. Free and compulsory education for ages 6 to 14; no detention; 25% reservation in private schools for disadvantaged groups; no corporal punishment; prescribed pupil-teacher ratios |
| 2016 | RPwD Act - Rights of Persons with Disabilities Act | Replaced the 1995 Act. Recognises **21 disabilities**, raises reservation to 4% in government jobs and 5% in higher education, and **LEGALLY MANDATES THE INCLUSION of children with disabilities in mainstream schools** |
| 2018 | Samagra Shiksha | Integrated scheme merging SSA, RMSA and Teacher Education |
| 2020 | NEP - National Education Policy | Replaced NPE 1986. **5+3+3+3+4** structure; ECCE; foundational literacy and numeracy; mother tongue as medium up to Grade 5; multidisciplinary education; target of 6% of GDP |



> **NOTE: Direct PYQ**
>
> "The philosophy of inclusive education was added in District Primary Education Programme (DPEP) in ________ year." Options: 1966, **1997**, 2012, 1950. Answer: **1997**.
>
> Sequence to remember: DPEP was launched in **1994**; the **Salamanca Statement** (the international push for inclusion) also came in **1994**; and India incorporated inclusive education into DPEP in **1997**.



> **NOTE: Direct PYQ**
>
> "Which law legally mandates the inclusion of children with disabilities into mainstream schools in India?" Options: **RPwD Act, 2016**, National Curriculum Framework 2005, RTI Act 2009, NEP 2020. Answer: **RPwD Act, 2016**.
>
> Why it must be the RPwD Act: the question asks for a **LAW** that **legally mandates** inclusion. The **NCF 2005** is a curriculum *framework*, not a law. **NEP 2020** is a *policy*, not legislation. The option "RTI Act, 2009" is a deliberate trap - **RTI** is the **Right to Information** Act (which is actually from 2005); the education law of 2009 is the **RTE** (Right to Education) Act. Only the **RPwD Act 2016** is a statute that specifically obliges schools to include children with disabilities.
>
> Do not confuse **RTE** (Right to Education, 2009) with **RTI** (Right to Information, 2005) with **RPwD** (Rights of Persons with Disabilities, 2016).



### K5.3 ICDS - Integrated Child Development Services


- **ICDS** - Launched in **1975**, one of the world's largest programmes for early childhood care. Delivered through **Anganwadi centres**.
- **Target group** - **Children BELOW SIX YEARS of age** (who are therefore too young for school), plus **pregnant women and nursing/lactating mothers**, and adolescent girls in some components.
- **The six services** - Supplementary nutrition, immunisation, health check-ups, referral services, **pre-school non-formal education**, and nutrition and health education for mothers.


> **NOTE: Direct PYQ**
>
> "Integrated child development service provides nutritious food for children who are ______." Options: School going, School drop-out, **Below age of six years and too young to go to school**, Girls below 12 years of age. Answer: **Below age of six years and too young to go to school**.
>
> ICDS is specifically an **early childhood (0-6 years)** programme - the age group before formal schooling begins. School-going children are covered instead by the **Mid-Day Meal Scheme** (now PM POSHAN). Keep the two schemes separate: **ICDS = under 6 (Anganwadi); Mid-Day Meal = school children (6-14)**.



### K5.4 Gender and equity in education


- **GENDER INEQUALITY** - **SOCIAL AND ECONOMIC DISPARITIES BETWEEN GENDERS** - unequal access to resources, opportunities, decision-making and rights. It is socially constructed, not biological.
- **Sex vs Gender** - **Sex** is the biological difference (chromosomes, anatomy). **GENDER** is the set of socially and culturally constructed roles, behaviours and expectations attached to being male or female. Sex is born; gender is taught.
- **Gender stereotype** - A fixed generalisation, such as "girls are weak at mathematics" or "boys should not cry".
- **Gender bias in the classroom** - Calling on boys more often, assigning cleaning tasks to girls, gender-typed illustrations in textbooks, discouraging girls from science and sport.
- **Gender-sensitive teaching** - Equal participation and attention, gender-neutral language and materials, challenging stereotypes, safe and inclusive classrooms.
- **Relevant schemes** - Beti Bachao Beti Padhao, Kasturba Gandhi Balika Vidyalaya (KGBV), National Programme for Education of Girls at Elementary Level (NPEGEL), Sukanya Samriddhi Yojana.


> **NOTE: Direct PYQ**
>
> "Gender inequality refers to which of the following?" Options: **Social and economic disparities between genders**, Biological differences only, Differences in hairstyles, Uniform distribution of resources. Answer: **Social and economic disparities between genders**.
>
> Note the trap "**Biological differences only**" - biological difference is **sex**, not gender, and mere difference is not *inequality*. Also note that "uniform distribution of resources" describes **equality**, the exact opposite of what is asked.



### K5.5 Multilingual education


- **Multilingual approach** - Treating the languages a child already speaks as a **resource**, not a problem. The child's **mother tongue / home language is welcomed into the classroom and used as a bridge to build understanding** of new concepts and of the school language.
- **Why it works** - Concepts learned in a familiar language transfer to the new language; the child's identity and confidence are respected; comprehension is far better than in an unfamiliar medium.
- **NEP 2020 position** - Wherever possible, the medium of instruction until at least Grade 5 (preferably Grade 8) should be the **home language / mother tongue / local language**.
- **Three Language Formula** - Regional language, Hindi and English (with flexibility under NEP 2020).
- **Submersion (to be avoided)** - Throwing a child into a classroom in an unfamiliar language with no support - the "sink or swim" approach.
- **Immersion** - Systematic teaching *through* a second language with proper support.


> **NOTE: Direct PYQ**
>
> "What is the core principle of the multilingual approach in early education?" Answer: **Welcoming the child's language and using it to build understanding.**
>
> Each distractor names a discredited practice: "prioritising grammar over communication" is the old grammar-translation method; "replacing mother tongue with the target language quickly" is submersion, which harms comprehension and self-esteem; "teaching only in the national language" ignores India's linguistic diversity and violates NEP guidance.



### K5.6 Aesthetic and vocational education


- **Aesthetic education** - Education in and through the arts - music, dance, drama, visual art. Its primary aim is to develop **SENSORY RESPONSIVENESS**: the ability to perceive, appreciate and respond to beauty, form, colour, sound and rhythm. It also builds creativity, imagination, emotional expression and cultural appreciation.
- **Vocational education** - Education for a specific trade or occupation, combining knowledge with practical skill.


> **NOTE: Direct PYQ**
>
> "Aesthetic education primarily develops ______." Options: speed in recall, logical reasoning, factual knowledge, **sensory responsiveness**. Answer: **sensory responsiveness**.
>
> Aesthetics is fundamentally about **perceiving and feeling** - responding to what you see, hear and sense. "Speed in recall" and "factual knowledge" belong to memory-based learning, and "logical reasoning" belongs to the cognitive/mathematical domain. Only sensory responsiveness is the distinctive contribution of arts education.



#### Principles of curriculum construction


| Principle | Meaning |
|---|---|
| Child-centredness | Built around the learner's needs, interests and stage of development |
| ACTIVITY AND PRACTICALITY | Learning by DOING, with practical, hands-on, real-life application. Essential when skills must TRANSFER TO ACTUAL WORK SETTINGS |
| Utility / Usefulness | Content should be useful in life |
| Flexibility | Adaptable to local needs and changing times |
| Integration / Correlation | Subjects linked to one another and to life |
| Community-centredness | Linked to the life of the community |
| Articulation | Vertical continuity - each stage builds smoothly on the previous one |
| Sequence and continuity | Logical order and progressive depth |
| Balance | Between subjects, theory and practice, and individual and social aims |
| Economy | Achieving maximum learning with minimum wastage of time and resources |
| Conservation and creativity | Preserving culture while encouraging innovation |



> **NOTE: Direct PYQ**
>
> "You are designing a curriculum for vocational education. To ensure learners can transfer skills to actual work settings, which principle should you emphasise most?" Options: **Principle of activity and practicality**, Principle of articulation, Principle of recency, Principle of economy. Answer: **Principle of activity and practicality**.
>
> Reasoning: the goal stated is **transfer of skills to a real workplace**. Skills transfer only through **actual practice** in realistic conditions - hence activity and practicality. *Articulation* concerns smooth progression between stages, *recency* concerns how recently material was learned, and *economy* concerns efficient use of time and resources - none addresses workplace transfer.



### K5.7 Subject and discipline


- **Discipline** - A broad **field of knowledge** with its own concepts, methods of enquiry and body of research - for example Physics, History, Mathematics as scholarly domains.
- **Subject** - **The branch of a discipline that is selected, simplified and organised to be TAUGHT IN THE CLASSROOM** at a particular level. A school subject is a pedagogical selection from the parent discipline.


> **NOTE: Direct PYQ (this question appeared in Hindi)**
>
> "In school, a 'subject' differs from a 'discipline' because it is ______." The answer given was: **the branch of the discipline that is taught in the classroom** (anushasan ki kaksha mein padhai jaane wali shakha).
>
> The relationship: a **discipline** is the full universe of knowledge produced by scholars; a **subject** is the curated, age-appropriate slice of it that appears on a school timetable. School "Science" is a subject drawn from the disciplines of Physics, Chemistry and Biology.



## K6 The Teacher and the Community



### K6.1 Why community involvement matters


A teacher who is seen only inside the classroom remains an outsider. A teacher who participates in the life of the village or neighbourhood is **accepted as one of the community's own**, which brings enormous benefits: parents cooperate, attendance improves, dropouts return, and the school gains local support and resources.


#### Activities through which a teacher becomes accepted by the community

- Helping address **problems of unhygienic conditions** - sanitation, clean drinking water, waste disposal drives.
- Helping with **problems of agriculture** - sharing information, organising demonstrations, connecting farmers with schemes.
- Adult and literacy programmes.
- Health, immunisation and nutrition awareness camps.
- Participating in local festivals, fairs and cultural events.
- Helping in disaster relief and community service.
- Environmental work: tree planting, cleanliness drives.


> **NOTE: PYQ worked out**
>
> "Participation in which of the following activities can enable the community to accept a teacher as one of them?
> I. Problems of unhygienic conditions.
> II. Problems of agriculture."
>
> Answer: **Both I and II**
>
> Both are correct because acceptance comes from involvement in matters the community **actually cares about in daily life**. Sanitation and agriculture are central concerns in most Indian villages. A teacher who helps with them is no longer merely a government employee but a genuine member of the community.
>
> The wider principle: the teacher's role extends beyond the classroom into **community leadership and social service**. Any option restricting the teacher to purely academic work is usually wrong in this style of question.



### K6.2 Community service activities for students


- **Community service** - Activities in which students **contribute something to the community**, giving their time and effort for the benefit of others.
- **Not community service** - Activities where students merely **collect information or study** the community. Those are *survey*, *project* or *cultural study* activities.


| Activity | Category |
|---|---|
| PARTICIPATING IN DECORATION AT THE TIME OF EVENTS | COMMUNITY SERVICE - the students give their labour for a shared community occasion |
| Collecting pictures of musical instruments and dances | Project / cultural study |
| Collecting information about handicrafts of different places | Project / survey work |
| Exploring food habits and living styles of people of different states | Project / social study |
| Cleanliness drives, tree plantation, helping at a health camp, visiting an old-age home, literacy teaching | Community service |



> **NOTE: Direct PYQ**
>
> "Which of the following is the activity related to community services?" Answer: **Participating in decoration at the time of events.**
>
> The test to apply: ask "**is the student GIVING something to the community, or GETTING information from it?**" Collecting pictures, collecting information and exploring food habits are all about *gathering data* - they benefit the student's own learning. Only decorating for a community event involves **contributing effort for the community's benefit**, which is the definition of service.



### K6.3 The teacher's professional roles and ethics



| Role | Description |
|---|---|
| Facilitator of learning | Guides construction of knowledge rather than dictating notes |
| Diagnostician | Identifies learning difficulties and plans remediation |
| Curriculum adapter | Adjusts content and pace to the learners in front of him |
| Counsellor and mentor | Supports emotional and career development |
| Role model | Children imitate the teacher's behaviour, language and attitudes |
| Reflective practitioner | Continuously examines and improves his own practice |
| Action researcher | Investigates his own classroom problems systematically |
| Lifelong learner | Keeps updating subject knowledge and pedagogy |
| Community link | Connects school, home and community |
| Inclusive practitioner | Ensures every child, including CWSN, learns |


- **Professional ethics** - Respect for every child's dignity, impartiality, confidentiality, no corporal punishment, no private tuition to one's own students, no discrimination on grounds of caste, religion, gender or disability, punctuality and academic honesty.
- **Action research** - Small-scale research conducted by the teacher **in his own classroom** to solve an immediate practical problem, following a cycle of plan, act, observe and reflect.
- **Reflective teaching** - Systematically thinking about what happened in a lesson, why, and what to change next time.
- **Continuous Professional Development (CPD)** - Ongoing in-service training, workshops, peer observation and self-study.


### K6.4 Guidance and counselling


- **Guidance** - Assistance given to help an individual understand himself and make wise choices. Broader and more informational.
- **Counselling** - A focused, confidential, one-to-one professional relationship helping a person resolve a personal or psychological problem.
- **Educational guidance** - Choice of subjects, study habits, dealing with academic difficulty.
- **Vocational guidance** - Choice of career, based on aptitude, interest and opportunity.
- **Personal guidance** - Emotional, social and health-related concerns.
- **Cumulative record card** - A comprehensive, continuous record of a student's academic and personal development, used as the basis for guidance.



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




## L11 Paper 3 - Discipline 1



### About this paper

This is the most recent of the three papers, and its style is noticeably different: fewer pure-recall questions and more **conceptual and code-tracing** questions. Treat it as the best guide to what the next paper will look like.


**Q. How does the Best Fit algorithm impact system performance?**

- (a) It improves system performance by reducing memory wastage.
- (b) **It may reduce system performance due to increased search time for free blocks.  <-- CORRECT**
- (c) It always improves system performance.
- (d) It improves system performance by reducing external fragmentation.

> **Why:** Best Fit must scan the entire free list on every request, and it worsens external fragmentation by leaving tiny holes. See Part C, Chapter C4.2.



**Q. What happens if a RST (reset) packet is received during the connection management process?**

- (a) The receiver sends another SYN packet.
- (b) **The connection is immediately terminated.  <-- CORRECT**
- (c) The sender continues retransmissions.
- (d) The connection remains active.

> **Why:** RST aborts abruptly, unlike FIN which starts a graceful four-way shutdown. See Part G, Chapter G5.3.



**Q. Which of the following SQL expressions evaluates to TRUE, according to SQL-99?**

- (a) NULL <= NULL returns UNKNOWN
- (b) NULL >= NULL returns UNKNOWN
- (c) NULL IS NULL returns FALSE
- (d) **NULL IS NULL returns TRUE  <-- CORRECT**

> **Why:** You can never test NULL with = or <=; only IS NULL works, and it returns TRUE. See Part F, Chapter F4.4.



**Q. Which of the following statements is false about universal logic gates?**

- (a) All basic logic gates can be implemented through universal logic gates.
- (b) NOR gate is known as universal logic gate.
- (c) NAND gate is known as universal logic gate.
- (d) **All basic logic gates cannot be implemented using universal logic gates.  <-- CORRECT**

> **Why:** This directly contradicts the definition of a universal gate. See Part A, Chapter A6.3.



**Q. If a process arrives at time 5, what is the latest possible time for it to start execution if there are no other processes in the system?**

- (a) Time 6
- (b) Time 0
- (c) **Time 5  <-- CORRECT**
- (d) Time 4

> **Why:** With no competition it is dispatched immediately, and it cannot start before it arrives. See Part C, Chapter C2.2.



**Q. Which of the following describes the use of digital certificates in authentication? (asked in Hindi)**

- (a) They store users' passwords.
- (b) They compress large files for secure transfer.
- (c) **They verify the identity of entities using Public Key Infrastructure (PKI).  <-- CORRECT**
- (d) They encrypt data transmission.

> **Why:** Certificates bind a public key to an identity, signed by a CA. They authenticate; encryption is done separately with session keys. See Part G, Chapter G7.6.



**Q. Which of the following is NOT a benefit of distributed systems?**

- (a) Scalability
- (b) **High communication latency  <-- CORRECT**
- (c) Resource sharing
- (d) Fault tolerance

> **Why:** Latency is a well-known drawback, because messages travel over a network. See Part C, Chapter C6.5.



**Q. What is the overall design of a database called?**

- (a) **Database Schema  <-- CORRECT**
- (b) Database Instance
- (c) Database Table
- (d) Database Model

> **Why:** Schema is the structure; instance is the data at a moment. Schema is to instance as class is to object. See Part F, Chapter F1.3.



**Q. In an acyclic graph directory structure, what is a common method used to implement shared directories or files?**

- (a) File duplication
- (b) **Symbolic (soft) links  <-- CORRECT**
- (c) Hard links
- (d) Directory pointers

> **Why:** Hard links to directories are forbidden because they could create cycles, breaking acyclicity. See Part C, Chapter C5.2.



**Q. What is the ARP reply's scope in terms of message type?**

- (a) Anycast
- (b) **Unicast  <-- CORRECT**
- (c) Multicast
- (d) Broadcast

> **Why:** ARP request = broadcast (nobody knows who has the IP); ARP reply = unicast (the replier knows exactly who asked). See Part G, Chapter G4.5.



**Q. What does the XNOR gate output when A=1 and B=0?**

- (a) B
- (b) **0  <-- CORRECT**
- (c) A
- (d) 1

> **Why:** XNOR outputs 1 only when inputs are identical. Here they differ, so the output is 0. See Part A, Chapter A6.2.



**Q. Which technology is commonly used in Wi-Fi to enhance signal range and reliability?**

- (a) **MIMO (Multiple Input Multiple Output)  <-- CORRECT**
- (b) WEP (Wired Equivalent Privacy)
- (c) TDMA
- (d) CDMA

> **Why:** WEP is (broken) security; TDMA and CDMA are cellular channel-access methods. See Part G, Chapter G8.4.



**Q. In which scheduling algorithm does the disk head move in one direction, satisfying all requests until it reaches the end, and then reverses direction?**

- (a) **SCAN  <-- CORRECT**
- (b) SSTF
- (c) LOOK
- (d) FCFS

> **Why:** "Until it reaches the end" is decisive - LOOK reverses at the last request instead. See Part C, Chapter C5.5.



**Q. In public key cryptography, which key is used for decrypting a message encrypted with the public key?**

- (a) Another public key
- (b) A symmetric key
- (c) The sender's private key
- (d) **The recipient's private key  <-- CORRECT**

> **Why:** Only the matching private key of the same pair can undo what its public key locked. See Part G, Chapter G7.3.



**Q. How does the receiver handle out-of-order frames in Selective Repeat?**

- (a) Requests retransmission of all frames
- (b) Sends a cumulative acknowledgment
- (c) **Buffers them until all missing frames arrive  <-- CORRECT**
- (d) Discards them immediately

> **Why:** Buffering is the defining difference from Go-Back-N, which discards them. See Part G, Chapter G3.2.



**Q. __________ is NOT allowed in a SQL:1999 view definition.**

- (a) Use of subqueries
- (b) Use of nested queries
- (c) Use of aggregate formulas
- (d) **Use of ORDER BY clause  <-- CORRECT**

> **Why:** A view is a relation, and a relation is an unordered set of tuples. Apply ORDER BY when selecting *from* the view. See Part F, Chapter F4.6.



**Q. Select the correct SQL statement which will correctly insert a new row into the Customer table with only the CustomerID, Name, and Product columns specified.**

- (a) INSERT Customer SET CustomerID=101, Name='Alice', Product='Pen';
- (b) INSERT INTO Customer VALUES (101, 'Alice', 'Pen');
- (c) INSERT INTO Customer (101, 'Alice', 'Pen');
- (d) **INSERT INTO Customer (CustomerID, Name, Product) VALUES (101, 'Alice', 'Pen');  <-- CORRECT**

> **Why:** To insert into a subset of columns you must name the columns AND use VALUES. See Part F, Chapter F4.2.



**Q. Which SQL statement is used to update data in a table?**

- (a) CHANGE
- (b) MODIFY
- (c) **UPDATE  <-- CORRECT**
- (d) SET

> **Why:** CHANGE and MODIFY are clauses inside ALTER TABLE; SET is a clause inside UPDATE. See Part F, Chapter F4.2.



**Q. What is typically returned by the getpid system call in Unix-based operating systems?**

- (a) The process ID of the kernel
- (b) **Process ID of the current process  <-- CORRECT**
- (c) Process ID of the first process
- (d) Process ID of the parent process

> **Why:** getppid() - with the extra p - returns the parent's PID. See Part C, Chapter C1.4.



**Q. What does the TCP service model guarantee about the order of data delivery?**

- (a) **Data is delivered in the order it is transmitted.  <-- CORRECT**
- (b) Data is not guaranteed to arrive in any specific order.
- (c) Data may arrive out of order and is handled by the application layer.
- (d) Data is delivered as fast as possible.

> **Why:** TCP uses sequence numbers to reorder segments. The "handled by application layer" option describes UDP. See Part G, Chapter G5.1.



## L12 Paper 3 - Discipline 2



**Q. A Parent class has a protected method; Child extends Parent and calls it from a public method. What happens when the code is executed?**

- (a) **The code will compile and print 'Protected method in Parent'.  <-- CORRECT**
- (b) Compilation Error: protectedMethod is not visible in the Child class.
- (c) Compilation Error: childMethod is not visible due to access restrictions.
- (d) Runtime Error: Cannot access protectedMethod from the Child class.

> **Why:** A protected member is fully accessible inside a subclass. Nothing here is illegal. Full trace in Part D, Chapter D3.3.



**Q. Given int a, b, c; a = b = c = 15; c = c + 10; what is the value of c?**

- (a) Undefined
- (b) 10
- (c) **25  <-- CORRECT**
- (d) 15

> **Why:** Assignment is right-to-left, so all three become 15; then c becomes 25. See Part D, Chapter D1.5 (Trap 6).



**Q. What happens when this executes? char buffer[50]; int n = sprintf(buffer, "Hello, World!"); printf("%d %s", n, buffer);**

- (a) Prints '13 Hello'
- (b) Prints '12 Hello'
- (c) Prints '12 Hello, World!'
- (d) **Prints '13 Hello, World!'  <-- CORRECT**

> **Why:** sprintf writes into buffer and returns the character count, excluding '\0'. "Hello, World!" has 13 characters. See Part D, Chapter D1.5 (Trap 10).



**Q. What is the 2's complement of the binary number 1100?**

- (a) **0100  <-- CORRECT**
- (b) 1111
- (c) 11
- (d) 1001

> **Why:** Invert to 0011, then add 1 to get 0100. See Part A, Chapter A5.6.



**Q. Which of the following is true about nested switch statements in C?**

- (a) Both inner and outer switch statements must have a default case.
- (b) A switch statement cannot contain another switch.
- (c) Inner switch cases should not contain break statement
- (d) **A switch statement can contain another switch statement inside any of its cases.  <-- CORRECT**

> **Why:** default is always optional, and nesting is allowed. See Part D, Chapter D1.4.



**Q. Output of: int i = 5; do { printf("%d ", i); i--; } while (i > 5);**

- (a) No output printed
- (b) Infinite loop
- (c) 5 4 3 2 1
- (d) **5  <-- CORRECT**

> **Why:** do-while runs the body first, then tests: 4 > 5 is false, so it stops after one pass. See Part D, Chapter D1.5 (Trap 1).



**Q. Output of: int x = -1, y = 0, z = 1; int result = (x > 0) ? x : (y == 0) ? z : y;**

- (a) compile time error
- (b) -1
- (c) **1  <-- CORRECT**
- (d) 0

> **Why:** ?: is right-associative. x > 0 is false, so evaluate (y == 0) ? z : y, which gives z = 1. See Part D, Chapter D1.5 (Trap 3).



**Q. How many times will the innermost loop execute? for(i=0;i<3;i++) for(j=0;j<2;j++) printf(...)**

- (a) **6 times  <-- CORRECT**
- (b) 3 times
- (c) 5 times
- (d) 2 times

> **Why:** 3 outer iterations x 2 inner iterations = 6. See Part D, Chapter D1.5 (Trap 7).



**Q. Which of the following causes an infinite loop?**

- (a) for (int i = 10; i > 5; i--) { }
- (b) do { } while (0);
- (c) **while (1) { }  <-- CORRECT**
- (d) for (int i = 0; i < 10; i++) { }

> **Why:** The condition 1 is always true. The others terminate after 5, 1 and 10 iterations. See Part D, Chapter D1.4.



**Q. What does the code snippet myObject.doActivity(); represent?**

- (a) **Calling a method named doActivity on the object myObject  <-- CORRECT**
- (b) Sending a message to the doActivity class
- (c) Creating an object myObject
- (d) Sending a message to the child class of myObject

> **Why:** doActivity is a method, not a class; object creation would need `new`. See Part D, Chapter D2.3.



**Q. Which arithmetic operator has the highest precedence in C?**

- (a) -
- (b) =
- (c) +
- (d) **%  <-- CORRECT**

> **Why:** The group `* / %` outranks `+ -`; `=` has almost the lowest precedence of all. See Part D, Chapter D1.3.



**Q. What does the super keyword in Java do?**

- (a) Refers to high performing objects
- (b) Refers to the current object
- (c) Used to define static variables
- (d) **Refers to the parent class  <-- CORRECT**

> **Why:** `this` refers to the current object; `super` refers to the parent. See Part D, Chapter D3.4.



**Q. Output of: int a = 5, b = 3, c = 0; if (a > b > c) printf("True"); else printf("False");**

- (a) compile time error
- (b) undefined behavior
- (c) **TRUE  <-- CORRECT**
- (d) FALSE

> **Why:** Left-to-right: (5 > 3) gives 1, then (1 > 0) gives 1, so the condition is true. See Part D, Chapter D1.5 (Trap 2).



**Q. Which statement is false about simplification of Boolean functions using the Karnaugh Map technique?**

- (a) K-map is used to simplify Product of Sum (POS) form.
- (b) **In Karnaugh Map, the rows and columns are represented in binary code sequence.  <-- CORRECT**
- (c) You group adjacent squares in powers of two, covering as many minterms or maxterms as possible.
- (d) K-map is used to simplify Sum of Product (SOP) form.

> **Why:** K-map rows and columns use GRAY code (00, 01, 11, 10), which is why adjacent cells differ by one bit. See Part A, Chapter A6.6.



**Q. An ExceptionTest program calls calculate(10, 0), whose inner catch re-throws a new Exception, with finally blocks at both levels. What is the output?**

- (a) Inner finally block executed. General exception caught: / by zero In finally block.
- (b) **Inner finally block executed. / General exception caught: Division by zero not allowed / In finally block.  <-- CORRECT**
- (c) Inner finally block executed. Result: 0 In finally block.
- (d) Inner finally block executed. ArithmeticException caught: / by zero In finally block.

> **Why:** The inner finally runs before control leaves; the re-thrown object's type is Exception, so the second catch matches and shows the new message. Full trace in Part D, Chapter D3.6.



**Q. What is the objective of encapsulation in object-oriented programming?**

- (a) To create multiple instances of a class
- (b) To enable one class to inherit from another class
- (c) To allow objects to take multiple forms
- (d) **To combine data and methods that operate on that data within a single unit  <-- CORRECT**

> **Why:** The distractors define instantiation, inheritance and polymorphism respectively. See Part D, Chapter D2.2.



**Q. Output of: int a = 10, b = 20; int max = (a > b) ? a : b; printf("%d", max);**

- (a) 30
- (b) compile time error
- (c) 10
- (d) **20  <-- CORRECT**

> **Why:** 10 > 20 is false, so b = 20 is chosen. See Part D, Chapter D1.5 (Trap 3).



**Q. A CustomException extends Exception; validateAge(15) throws it when age < 18. What is the output?**

- (a) Caught Exception: null / Execution finished.
- (b) Compilation error because custom exceptions cannot extend Exception.
- (c) Age is valid. / Execution finished.
- (d) **Caught Exception: Age must be 18 or above. / Execution finished.  <-- CORRECT**

> **Why:** 15 < 18 so the exception is thrown and "Age is valid." never prints; super(message) makes getMessage() return the text. See Part D, Chapter D3.6.



**Q. Which of the following techniques can be used to modify the actual variable passed to a function?**

- (a) Use a local variable instead of passing any parameters.
- (b) Pass a copy of the actual parameter to function.
- (c) Standard C has no options for modifying actual variables passed to a function.
- (d) **Pass the address of the actual parameters to function.  <-- CORRECT**

> **Why:** Passing a copy cannot affect the original; pointers exist precisely for this. See Part D, Chapter D1.6.



**Q. What do the first and second dimensions represent in a two-dimensional character array?**

- (a) The first dimension stores the length of each name, and the second stores the number of names.
- (b) **The first dimension represents the number of names in the array, and the second dimension represents the maximum length of each name.  <-- CORRECT**
- (c) The first dimension represents the maximum length of the names, and the second the number of names.
- (d) The first dimension holds the total number of characters, and the second stores the number of names.

> **Why:** Think "how many, then how long". See Part D, Chapter D1.8.



## L13 Paper 3 - Discipline 3



**Q. Which asymptotic notation gives asymptotically tight upper bound as well as asymptotically tight lower bound?**

- (a) Omega
- (b) Big Oh
- (c) **Theta  <-- CORRECT**
- (d) Small Omega

> **Why:** "As well as" means both bounds at once, which is Theta. See Part E, Chapter E1.3.



**Q. What is the primary function of a web browser?**

- (a) To store large amounts of data
- (b) To send and receive emails
- (c) To create websites
- (d) **To display and navigate web pages  <-- CORRECT**

> **Why:** A browser renders and navigates web content; it neither authors sites nor serves as a mail client. See Part H, Chapter H1.1.



**Q. Output of a C program where func() returns a static array and the loop prints *ptr five times without incrementing ptr.**

- (a) 1 1 3 4 1
- (b) 2 3 4 5 0
- (c) 1 2 3 4 5
- (d) **1 1 1 1 1  <-- CORRECT**

> **Why:** ptr is never advanced, so *ptr always dereferences the first element. See Part D, Chapter D1.5 (Trap 9).



**Q. Which DHTML method is used to change the style of an HTML element using CSS dynamically?**

- (a) document.createElement("style")
- (b) document.getElementById("element").setCSS()
- (c) **element.style.backgroundColor = "red"  <-- CORRECT**
- (d) window.addEventListener("resize")

> **Why:** Every element exposes a `style` object; CSS background-color becomes JavaScript backgroundColor. There is no setCSS(). See Part H, Chapter H4.3.



**Q. Which of the following statements is INCORRECT about the storage classes in C?**

- (a) The scope of variable in automatic storage class is local to the block in which the variable is defined.
- (b) **In Register storage class, the default initial value of the variable is zero.  <-- CORRECT**
- (c) In static storage class, the default initial value of the variable is zero.
- (d) In Register storage class, the storage of a variable is CPU register.

> **Why:** register variables start with garbage, like auto. Only static and extern default to zero. See Part D, Chapter D1.7.



**Q. Output of nested blocks where inner block declares int y = 40, does x++ and y++, then the outer block prints x and y (outer x=10, y=20).**

- (a) x = 11, y = 41
- (b) x = 10, y = 41
- (c) x = 10, y = 20
- (d) **x = 11, y = 20  <-- CORRECT**

> **Why:** The inner y shadows the outer one and dies with the block; x is the outer variable and was incremented. See Part D, Chapter D1.5 (Trap 5).



**Q. Which advantage of AJAX helps in reducing bandwidth consumption?**

- (a) AJAX uses less JavaScript.
- (b) AJAX only loads images on the page.
- (c) AJAX increases data transfer.
- (d) **AJAX sends and retrieves only small amounts of data from the server.  <-- CORRECT**

> **Why:** Only the needed fragment is exchanged instead of a whole page. See Part H, Chapter H4.4.



**Q. Which of the following cases DOES NOT exist when one computes the time complexity of an algorithm?**

- (a) Average case
- (b) Worst case
- (c) **Test Case  <-- CORRECT**
- (d) Best Case

> **Why:** A "test case" belongs to software testing, not complexity analysis. See Part E, Chapter E1.2.



**Q. Which of the following options is correct about the functions in C language?**

- (a) Actual parameters are declared in the function definition.
- (b) Actual parameters are always variables.
- (c) Actual parameters are used to define the function signature.
- (d) **Actual parameters are the values that are passed to a function when it is called.  <-- CORRECT**

> **Why:** The distractors all describe FORMAL parameters. Actual parameters can also be literals or expressions. See Part D, Chapter D1.6.



**Q. Which DHTML method is used to control the browser window size, such as resizing it dynamically via JavaScript?**

- (a) **window.resizeTo()  <-- CORRECT**
- (b) window.setSize()
- (c) window.changeSize()
- (d) document.resizeWindow()

> **Why:** Only resizeTo() (and resizeBy()) exist; the other three names are invented. See Part H, Chapter H4.3.



**Q. Which sorting technique is best for sorting a linked list with n elements?**

- (a) Insertion sort
- (b) Bubble sort
- (c) **Merge sort  <-- CORRECT**
- (d) Selection sort

> **Why:** Merge sort needs only sequential traversal and pointer relinking - no random access, and O(1) extra space on a list. See Part E, Chapter E4.2.



**Q. Which PHP function is used to sort an array in ascending order without affecting the keys?**

- (a) ksort()
- (b) array_sort()
- (c) **asort()  <-- CORRECT**
- (d) sort()

> **Why:** Prefix 'a' preserves key association; 'k' sorts by key; plain sort() reindexes. array_sort() does not exist. See Part H, Chapter H6.2.



**Q. Which tool is used to adjust the brightness and contrast of an image in Adobe Photoshop?**

- (a) Healing brush tool
- (b) Paint bucket tool
- (c) **Adjustments panel  <-- CORRECT**
- (d) Selection tool

> **Why:** The Adjustments panel holds brightness/contrast, levels, curves and hue/saturation. See Part I, Chapter I3.7.



**Q. Which of the following is NOT a correct way of declaring and initializing array in C?**

- (a) char arr[6] = {2};
- (b) char arr[ ] = "consultancy";
- (c) **char arr[6]; arr = "consultancy";  <-- CORRECT**
- (d) char arr[6] = { };

> **Why:** An array name is not a modifiable lvalue, so it cannot be assigned after declaration - and 6 bytes is too small anyway. See Part D, Chapter D1.8.



**Q. Which of the following formats is commonly used for exporting images for the web?**

- (a) **PNG  <-- CORRECT**
- (b) PSD
- (c) BMP
- (d) TIFF

> **Why:** PSD is Photoshop's working file; BMP and TIFF are far too large for the web. See Part I, Chapter I3.7.



**Q. Output of: int a = 4; int b = 3; result = a ^ b; printf("%d", result);**

- (a) 0
- (b) 3
- (c) 4
- (d) **7  <-- CORRECT**

> **Why:** ^ is bitwise XOR, not exponentiation: 100 XOR 011 = 111 = 7. See Part D, Chapter D1.5 (Trap 4).



**Q. Output of: let x = 10; if (x > 5) console.log("Greater"); else console.log("Smaller");**

- (a) "Smaller"
- (b) "undefined"
- (c) **"Greater"  <-- CORRECT**
- (d) Error

> **Why:** 10 > 5 is true. See Part H, Chapter H4.1.



**Q. In a singly linked list, each node of the list consists of __________.**

- (a) **data value and address of next node  <-- CORRECT**
- (b) NULL and address of the next node
- (c) NULL and address of the previous node
- (d) data value and address of previous node

> **Why:** Only the LAST node contains NULL; a previous-node address means a doubly linked list. See Part E, Chapter E2.3.



**Q. What is the main function of the 'cutting' tool in image editing?**

- (a) **To remove parts of the image  <-- CORRECT**
- (b) To change the image resolution
- (c) To apply color effects
- (d) To resize the image

> **Why:** Cutting/cropping removes; it does not resample or recolour. See Part I, Chapter I3.7.



**Q. Which statement is correct about the divide and conquer approach of binary search?**

- (a) The recurrence relation of binary search is T(n) = 2T(n/2) + O(1).
- (b) **The worst-case time complexity of binary search is O(log n).  <-- CORRECT**
- (c) The best-case time complexity of binary search is O(log n).
- (d) The average-case time complexity of binary search is O(n).

> **Why:** Binary search searches only ONE half, so the recurrence is T(n) = T(n/2) + O(1); the best case is O(1). See Part E, Chapter E1.5.



## L14 Paper 3 - Discipline 4



**Q. If A = [[1,0,0],[0,-1,0],[1,0,1]] then the matrix for A^6 is __________.**

- (a) [[6,0,0],[0,6,0],[6,0,6]]
- (b) [[1,0,0],[0,-1,0],[6,0,1]]
- (c) [[1,0,0],[0,-1,0],[1,0,1]]
- (d) **[[1,0,0],[0,1,0],[6,0,1]]  <-- CORRECT**

> **Why:** The (3,1) entry becomes n and the (2,2) entry becomes (-1)^n; for n = 6 that is 6 and +1. See Part J, Chapter J4.5.



**Q. The magnetic moment of a bar magnet is _____ the magnetic moment of an equivalent solenoid if the solenoid's magnetic field is _______ that of the bar magnet.**

- (a) **equal to ; same as  <-- CORRECT**
- (b) more than ; same as
- (c) less than ; same as
- (d) equal to ; different from

> **Why:** Same field implies equal magnetic moment - that is what "equivalent" means. See Part J, Chapter J5.6.



**Q. Which of the following is a disadvantage of singly linked list?**

- (a) **Accessing an element in a singly linked list requires traversal from the head, making it slower than arrays.  <-- CORRECT**
- (b) Deletion at the beginning is performed in O(1) time.
- (c) Insertion at the beginning is performed in O(1) time.
- (d) Linked lists have a variable size.

> **Why:** The other three are advantages disguised as options. See Part E, Chapter E2.3.



**Q. During 2024-25 ABC Ltd's total purchases were Rs. 1,90,000. Gross profit was 20% on sales and closing stock was Rs. 30,000 more than opening stock. What was the gross profit?**

- (a) Rs. 35,000
- (b) Rs. 52,000
- (c) Rs. 25,000
- (d) **Rs. 40,000  <-- CORRECT**

> **Why:** COGS = 1,90,000 - 30,000 = 1,60,000 = 80% of sales, so sales = 2,00,000 and GP = 20% = 40,000. See Part J, Chapter J6.4.



**Q. What is the main purpose of virtual memory?**

- (a) **To extend the physical memory using secondary storage  <-- CORRECT**
- (b) To provide cache storage
- (c) To store BIOS settings
- (d) To increase CPU speed

> **Why:** Virtual memory keeps only the needed pages in RAM and the rest on disk. See Part C, Chapter C4.5.



**Q. Which of the following is true about the for loop in C?**

- (a) A for loop cannot be nested inside another for loop.
- (b) **The condition in a for loop is optional, and it can result in an infinite loop if omitted.  <-- CORRECT**
- (c) A for loop must always have all three components.
- (d) The increment/decrement part of the for loop is mandatory.

> **Why:** All three parts are optional: `for(;;)` is legal and loops forever. See Part D, Chapter D1.4.



**Q. A fire destroyed M Ltd's stock; salvaged stock was Rs. 3,00,000. The value of stock lost by fire was ____.**

- (a) Rs. 2,55,000
- (b) **Rs. 6,30,000  <-- CORRECT**
- (c) Rs. 6,75,000
- (d) Rs. 5,92,000

> **Why:** Build up stock on the date of fire (opening + purchases + wages - COGS = 9,30,000), then subtract salvage: 9,30,000 - 3,00,000. See Part J, Chapter J6.4.



**Q. Two identical cells of emf 1.5 V and internal resistance 0.5 ohm are in series. If the permitted current is 1 A, the effective terminal potential difference is ____. (asked in Hindi)**

- (a) 1 V
- (b) 0.75 V
- (c) **2 V  <-- CORRECT**
- (d) 0.5 V

> **Why:** Series gives EMF 3 V and r = 1 ohm; V = 3 - (1 x 1) = 2 V. See Part J, Chapter J5.5.



**Q. Which of the following is the differential equation corresponding to y = a e^(2x) + b e^(-x)?**

- (a) y'' - 2y' + y = 0
- (b) y'' + 2y' + y = 0
- (c) y'' + y' - 2y = 0
- (d) **y'' - y' - 2y = 0  <-- CORRECT**

> **Why:** Roots are 2 and -1, so (m-2)(m+1) = m^2 - m - 2 = 0. See Part J, Chapter J4.6.



**Q. MC Publications received rent of Rs. 2,50,000 for the year ending 31 March 2024, of which Rs. 50,000 relates to next year. The rent credited to P&L is ____ and the advance is shown as ____.**

- (a) Rs. 1,50,000; Liability
- (b) Rs. 2,00,000; Asset
- (c) Rs. 3,00,000; Asset
- (d) **Rs. 2,00,000; Liability  <-- CORRECT**

> **Why:** Only earned income goes to P&L; unearned income is an obligation, hence a liability. See Part J, Chapter J6.4.



**Q. The particular solution of the differential equation (D^4 - 18D^2 + 81)y = ... is**

- (a) 72x^2 e^(3x)/104
- (b) **x^2 e^(3x)  <-- CORRECT**
- (c) 2x^2 e^(3x)
- (d) 12x^2 e^(3x)

> **Why:** The operator factorises as (D-3)^2(D+3)^2, so m = 3 is a DOUBLE root and the PI carries x^2. See Part J, Chapter J4.6.



**Q. The characteristic equation of matrix A = [[1,4],[3,5]] is __________.**

- (a) lambda^2 + 6 lambda - 7 = 0
- (b) lambda^2 - 6 lambda + 7 = 0
- (c) **lambda^2 - 6 lambda - 7 = 0  <-- CORRECT**
- (d) lambda^2 + 6 lambda + 7 = 0

> **Why:** Trace = 6, determinant = 5 - 12 = -7, giving lambda^2 - 6 lambda - 7 = 0. See Part J, Chapter J4.5.



**Q. Which of the following is NOT a tertiary business activity?**

- (a) Transportation
- (b) Warehousing
- (c) Insurance
- (d) **Manufacturing  <-- CORRECT**

> **Why:** Manufacturing is a secondary (industrial) activity; the others are auxiliaries to trade. See Part J, Chapter J6.6.



**Q. Which cycle is primarily managed by the Control Unit?**

- (a) I/O cycle
- (b) Memory refresh cycle
- (c) **Instruction cycle (Fetch-Decode-Execute cycle)  <-- CORRECT**
- (d) Arithmetic cycle

> **Why:** The CU fetches, decodes and sequences; the ALU merely computes. See Part B, Chapter B2.3.



**Q. Which logical operation does the ALU perform that results in a 1 output only when both inputs are different?**

- (a) AND
- (b) **XOR  <-- CORRECT**
- (c) OR
- (d) NOR

> **Why:** XOR is the difference detector. See Part B, Chapter B6.2.



**Q. Which of the following is a key design goal of an Instruction Set Architecture?**

- (a) Minimizing the transistor count
- (b) Ensuring only complex instructions are supported
- (c) Maximizing the instruction decode time
- (d) **Balancing simplicity and performance for ease of programming and efficiency  <-- CORRECT**

> **Why:** You want to MINIMISE decode time, and transistor count is a chip-level concern. See Part B, Chapter B3.2.



**Q. Which of the following will terminate the loop immediately in C?**

- (a) **When a break statement is encountered  <-- CORRECT**
- (b) When the loop variable reaches a certain value
- (c) When a continue statement is encountered
- (d) When the loop condition is not given

> **Why:** continue only skips one iteration. See Part D, Chapter D1.4.



**Q. Output of a program filling a[i] = i*i - 2*i + 1 for i = 0 to 4.**

- (a) 1 0 2 4 9
- (b) **1 0 1 4 9  <-- CORRECT**
- (c) 1 1 2 4 9
- (d) 1 2 3 4 9

> **Why:** The expression is (i-1)^2, giving 1, 0, 1, 4, 9. See Part D, Chapter D1.5 (Trap 8).



**Q. Which of the following is the particular solution of y'' - 6y' + 9y = 2 e^(3t)?**

- (a) e^(3t)/2
- (b) **t^2 e^(3t)  <-- CORRECT**
- (c) e^(3t)
- (d) e^(3t)/9

> **Why:** (m-3)^2 = 0 means 3 is a double root, so the PI must carry t^2. See Part J, Chapter J4.6.



**Q. Calculate the time complexity of deleting an element from the beginning of a dynamic array.**

- (a) O(log)
- (b) O(1)
- (c) O(log n)
- (d) **O(n)  <-- CORRECT**

> **Why:** All remaining elements must shift left to keep memory contiguous. See Part E, Chapter E2.2.



## L15 Paper 3 - Discipline 5 and Teaching Methodology



### Discipline 5



**Q. Which of the following smileys express happiness in text communication?**

- (a) **:-)  <-- CORRECT**
- (b) :-(
- (c) : (
- (d) :
- ( ) 

> **Why:** Rotate the characters 90 degrees clockwise: the closing bracket forms a smile. The others form a frown or a flat mouth.



**Q. Eighty eight residents classified as male/female and drinker/non-drinker of tea. For testing association between sex and drinking of tea, the test statistic follows:**

- (a) t distribution with 1 degree of freedom
- (b) Chi Square distribution with 2 degrees of freedom
- (c) Normal distribution
- (d) **Chi square distribution with 1 degree of freedom  <-- CORRECT**

> **Why:** Association between two categorical variables means chi-square; df = (2-1)(2-1) = 1. The 88 is a red herring. See Part J, Chapter J3.6.



**Q. Which of the following statement is correct for a business organisation?**

- (a) Responsibility leads to decentralisation
- (b) Authority leads to decentralisation
- (c) **Delegation leads to decentralisation  <-- CORRECT**
- (d) Centralisation leads to autonomy

> **Why:** Systematic delegation throughout the organisation IS decentralisation. See Part J, Chapter J6.6.



**Q. Suppose a six faced die is thrown. The probability that the number appearing on top is even is:**

- (a) 1/4
- (b) 1/6
- (c) **1/2  <-- CORRECT**
- (d) 1/9

> **Why:** Even numbers {2,4,6} give 3 of 6 outcomes. 1/6 is the chance of one specific number. See Part J, Chapter J3.3.



**Q. How can you add an emoji to an email?**

- (a) Use the delete key
- (b) **Click the emoji icon in the toolbar  <-- CORRECT**
- (c) Reply to the email
- (d) Change the font style

> **Why:** The emoji picker is in the compose toolbar of every modern mail client.



**Q. Select the INCORRECT option among the phases of the CPU Instruction Cycle.**

- (a) Execute
- (b) **Encode  <-- CORRECT**
- (c) Store
- (d) Fetch

> **Why:** The phases are Fetch, Decode, Execute, Store. Instructions are decoded, never encoded, by the CPU. See Part B, Chapter B2.3.



**Q. Select an appropriate ROM type where data can be erased or destroyed using ultraviolet light.**

- (a) EEPROM
- (b) Flash ROM
- (c) **EPROM  <-- CORRECT**
- (d) PROM

> **Why:** EPROM has a quartz window for UV erasure; EEPROM and Flash erase electrically; PROM cannot be erased. See Part A, Chapter A4.2.



**Q. WhatsApp was founded by __________.**

- (a) **Jan Koum and Brian Acton  <-- CORRECT**
- (b) Mark Zuckerberg and Sheryl Sandberg
- (c) Larry Page and Sergey Brin
- (d) Allan Musk and Bill Steve

> **Why:** Koum and Acton founded WhatsApp in 2009; Facebook (Zuckerberg) acquired it in 2014. Page and Brin founded Google.



**Q. Which of the following is an example of open-source application software?**

- (a) **GIMP  <-- CORRECT**
- (b) CorelDRAW
- (c) Microsoft Excel
- (d) Adobe Illustrator

> **Why:** GIMP is the free open-source image editor; the other three are paid closed-source products. See Part A, Chapter A2.3.



**Q. What does the term 'bootstrapping' refer to in the context of starting a business?**

- (a) Raising funds through venture capitalists
- (b) **Self-funding the business using personal resources  <-- CORRECT**
- (c) Obtaining bank loans for initial capital
- (d) Crowdfunding through online platforms

> **Why:** All three distractors involve EXTERNAL money, which is exactly what bootstrapping avoids. See Part J, Chapter J6.9.



### Teaching Methodology



**Q. ________ is a methodical approach. It suggests a logical and well-organised sequence of activities. It follows more definite steps. (asked in Hindi)**

- (a) teaching strategy
- (b) teaching method
- (c) teaching technique
- (d) **teaching approach  <-- CORRECT**

> **Why:** "Methodical approach" with a logical, well-organised sequence describes the broadest level - the approach. See Part K, Chapter K3.3.



**Q. Aesthetic education primarily develops ______.**

- (a) speed in recall
- (b) logical reasoning
- (c) factual knowledge
- (d) **sensory responsiveness  <-- CORRECT**

> **Why:** Aesthetics is about perceiving and responding to beauty, form, colour and sound. See Part K, Chapter K5.6.



**Q. Gender inequality refers to which of the following?**

- (a) **Social and economic disparities between genders  <-- CORRECT**
- (b) Biological differences only
- (c) Differences in hairstyles
- (d) Uniform distribution of resources

> **Why:** Biological difference is SEX, not gender; and uniform distribution describes equality. See Part K, Chapter K5.4.



**Q. What is the core principle of the multilingual approach in early education?**

- (a) Prioritising grammar over communication
- (b) Replacing mother tongue with the target language quickly
- (c) **Welcoming the child's language and using it to build understanding  <-- CORRECT**
- (d) Teaching only in the national language

> **Why:** The home language is a resource and a bridge, not a problem to be removed. See Part K, Chapter K5.5.



**Q. In school, a 'subject' differs from a 'discipline' because it is ______. (asked in Hindi)**

- (a) an external research field
- (b) more deeply organised
- (c) a philosophical field
- (d) **the branch of the discipline taught in the classroom  <-- CORRECT**

> **Why:** A discipline is the full scholarly domain; a subject is the curated slice taught at school. See Part K, Chapter K5.7.



**Q. Which of the following is NOT one of the five steps of Herbartian lesson planning? (asked in Hindi)**

- (a) Association
- (b) Presentation
- (c) Application
- (d) **Evaluation  <-- CORRECT**

> **Why:** The five are Preparation, Presentation, Association, Generalisation, Application. Evaluation was added by later models. See Part K, Chapter K3.6.



**Q. Piaget's formal operational stage begins at approximately ______.**

- (a) **11 years  <-- CORRECT**
- (b) 14 years
- (c) 8 years
- (d) 7 years

> **Why:** Stage boundaries form the chain 0 - 2 - 7 - 11. See Part K, Chapter K2.1.



**Q. Which law legally mandates the inclusion of children with disabilities into mainstream schools in India?**

- (a) **RPwD Act, 2016  <-- CORRECT**
- (b) National Curriculum Framework, 2005
- (c) RTI Act, 2009
- (d) NEP, 2020

> **Why:** Only the RPwD Act is a statute mandating inclusion. NCF is a framework, NEP a policy, and RTI is Right to Information - not RTE. See Part K, Chapter K5.2.



**Q. Diagnostic assessment mainly helps in which of the following?**

- (a) Grading performance
- (b) Standardising content
- (c) Promoting learners
- (d) **Identifying misconceptions  <-- CORRECT**

> **Why:** Diagnosis locates exactly what is wrong so remediation can follow. Grading and promotion are summative. See Part K, Chapter K4.1.



**Q. You are designing a curriculum for vocational education. To ensure learners can transfer skills to actual work settings, which principle should you emphasise most?**

- (a) **Principle of activity and practicality  <-- CORRECT**
- (b) Principle of articulation
- (c) Principle of recency
- (d) Principle of economy

> **Why:** Skills transfer to real workplaces only through hands-on practice in realistic conditions. See Part K, Chapter K5.6.




---

# PART M - Rapid Revision: One-Liners, Full Forms and Formula Sheet

> *Read ONLY this Part in the last seven days before the exam. Everything here is high-frequency and examinable.*



## M1 The Last-Week Revision Plan



### M1.1 Seven days, seven passes



| Day | What to revise |
|---|---|
| Day 7 | Chapter M2 (full forms) + Chapter M3 (complexities) |
| Day 6 | Chapter M4 (networking numbers) + Chapter M5 (OS one-liners) |
| Day 5 | Chapter M6 (DBMS and SQL) + Chapter M7 (programming traps) |
| Day 4 | Chapter M8 (digital logic and architecture) + Chapter M9 (web) |
| Day 3 | Chapter M10 (formula sheet) + Chapter M11 (people and inventions) |
| Day 2 | Chapter M12 (teaching methodology one-liners) |
| Day 1 | Re-solve Part L Paper 3 (the most recent pattern), then skim every NOTE box in the book |



> **TIP: The night before**
>
> Do not learn anything new. Read only the full forms and the complexity tables. Sleep properly - recall drops sharply with fatigue, and this paper is a recall paper.



## M2 Full Forms You Must Know



### M2.1 Hardware and architecture



| Abbreviation | Full form |
|---|---|
| CPU | Central Processing Unit |
| ALU | Arithmetic and Logic Unit |
| CU | Control Unit |
| RAM | Random Access Memory |
| ROM | Read Only Memory |
| SRAM / DRAM | Static / Dynamic RAM |
| PROM | Programmable ROM |
| EPROM | Erasable Programmable ROM (erased by ULTRAVIOLET light) |
| EEPROM | Electrically Erasable Programmable ROM |
| BIOS | Basic Input Output System |
| CMOS | Complementary Metal Oxide Semiconductor |
| POST | Power On Self Test |
| UEFI | Unified Extensible Firmware Interface |
| RISC / CISC | Reduced / Complex Instruction Set Computer |
| ISA | Instruction Set Architecture |
| PC | Program Counter |
| IR | Instruction Register |
| MAR / MDR | Memory Address / Memory Data Register |
| PSW | Program Status Word |
| DMA | Direct Memory Access |
| TLB | Translation Lookaside Buffer |
| VLSI / ULSI | Very / Ultra Large Scale Integration |
| BCD | Binary Coded Decimal |
| ASCII | American Standard Code for Information Interchange |
| EBCDIC | Extended Binary Coded Decimal Interchange Code |
| MIPS / FLOPS | Millions of Instructions Per Second / Floating Point Operations Per Second |
| CPI | Cycles Per Instruction |
| DPI | Dots Per Inch |
| VDU | Visual Display Unit |
| OCR / OMR / MICR | Optical Character / Optical Mark / Magnetic Ink Character Recognition |



### M2.2 Operating systems



| Abbreviation | Full form |
|---|---|
| OS | Operating System |
| PCB | Process Control Block |
| FCFS | First Come First Served |
| SJF / SRTF | Shortest Job First / Shortest Remaining Time First |
| RR | Round Robin |
| HRRN | Highest Response Ratio Next |
| IPC | Inter Process Communication |
| LRU / LFU / MFU | Least Recently Used / Least Frequently Used / Most Frequently Used |
| FIFO | First In First Out |
| SSTF | Shortest Seek Time First |
| SCAN / C-SCAN | Elevator algorithm / Circular SCAN |
| MMU | Memory Management Unit |
| FAT | File Allocation Table |
| NTFS | New Technology File System |
| RTOS | Real Time Operating System |
| SMP | Symmetric Multiprocessing |
| WAL | Write Ahead Logging |
| 2PL | Two Phase Locking |



### M2.3 Networking



| Abbreviation | Full form |
|---|---|
| OSI | Open Systems Interconnection |
| TCP | Transmission Control Protocol |
| UDP | User Datagram Protocol |
| SCTP | Stream Control Transmission Protocol |
| IP | Internet Protocol |
| ICMP | Internet Control Message Protocol |
| IGMP | Internet Group Management Protocol |
| ARP / RARP | Address Resolution Protocol / Reverse ARP |
| DHCP | Dynamic Host Configuration Protocol |
| DNS | Domain Name System |
| HTTP / HTTPS | HyperText Transfer Protocol / Secure |
| FTP / TFTP | File Transfer Protocol / Trivial FTP |
| SMTP | Simple Mail Transfer Protocol |
| POP3 | Post Office Protocol version 3 |
| IMAP | Internet Message Access Protocol |
| SNMP | Simple Network Management Protocol |
| SSH | Secure Shell |
| TELNET | Terminal Network |
| NAT | Network Address Translation |
| RIP / OSPF / BGP | Routing Information Protocol / Open Shortest Path First / Border Gateway Protocol |
| LAN / MAN / WAN / PAN | Local / Metropolitan / Wide / Personal Area Network |
| VPN | Virtual Private Network |
| NIC | Network Interface Card |
| MAC | Media Access Control |
| LLC | Logical Link Control |
| CSMA/CD | Carrier Sense Multiple Access with Collision Detection |
| CSMA/CA | CSMA with Collision Avoidance |
| CRC | Cyclic Redundancy Check |
| ARQ | Automatic Repeat Request |
| MSS / MTU | Maximum Segment Size / Maximum Transmission Unit |
| RTT | Round Trip Time |
| TTL | Time To Live |
| SSL / TLS | Secure Sockets Layer / Transport Layer Security |
| MIMO | Multiple Input Multiple Output |
| TDMA / FDMA / CDMA | Time / Frequency / Code Division Multiple Access |
| OFDM | Orthogonal Frequency Division Multiplexing |
| GSM | Global System for Mobile communications |
| BTS / BSC / MSC | Base Transceiver Station / Base Station Controller / Mobile Switching Centre |
| HLR / VLR | Home / Visitor Location Register |
| AuC / EIR | Authentication Centre / Equipment Identity Register |
| MN / HA / FA / COA / CN | Mobile Node / Home Agent / Foreign Agent / Care Of Address / Correspondent Node |
| IANA | Internet Assigned Numbers Authority |
| PKI | Public Key Infrastructure |
| AES / DES | Advanced / Data Encryption Standard |
| RSA | Rivest Shamir Adleman |
| IDS / IPS | Intrusion Detection / Prevention System |



### M2.4 Databases, programming and web



| Abbreviation | Full form |
|---|---|
| DBMS | Database Management System |
| RDBMS | Relational DBMS |
| SQL | Structured Query Language |
| DDL / DML / DCL / TCL / DQL | Data Definition / Manipulation / Control / Transaction Control / Query Language |
| ACID | Atomicity, Consistency, Isolation, Durability |
| ER | Entity Relationship |
| FD | Functional Dependency |
| NF | Normal Form |
| BCNF | Boyce-Codd Normal Form |
| OLTP / OLAP | Online Transaction / Analytical Processing |
| ETL | Extract, Transform, Load |
| MVCC | Multi Version Concurrency Control |
| ODBC / JDBC | Open / Java Database Connectivity |
| OOP | Object Oriented Programming |
| JVM / JRE / JDK | Java Virtual Machine / Runtime Environment / Development Kit |
| JIT | Just In Time compiler |
| CLR / CTS / CLS / FCL | Common Language Runtime / Common Type System / Common Language Specification / Framework Class Library |
| MSIL / CIL | Microsoft / Common Intermediate Language |
| FORTRAN | FORmula TRANslation |
| COBOL | Common Business Oriented Language |
| BASIC | Beginner's All-purpose Symbolic Instruction Code |
| ALGOL | Algorithmic Language |
| LISP | LISt Processing |
| GREP | Globally search for a Regular Expression and Print |
| HTML | HyperText Markup Language |
| XML | eXtensible Markup Language |
| CSS | Cascading Style Sheets |
| DHTML | Dynamic HTML |
| AJAX | Asynchronous JavaScript And XML |
| JSON | JavaScript Object Notation |
| DOM / SAX | Document Object Model / Simple API for XML |
| DTD / XSD | Document Type Definition / XML Schema Definition |
| XSLT | eXtensible Stylesheet Language Transformations |
| SOAP / WSDL | Simple Object Access Protocol / Web Services Description Language |
| CGI | Common Gateway Interface |
| PHP | PHP: Hypertext Preprocessor |
| URL / URI | Uniform Resource Locator / Identifier |
| API | Application Programming Interface |
| EDI | Electronic Data Interchange |
| UPI | Unified Payments Interface |



### M2.5 Software engineering and management



| Abbreviation | Full form |
|---|---|
| SDLC | Software Development Life Cycle |
| SRS | Software Requirement Specification |
| RAD | Rapid Application Development |
| CMM / CMMI | Capability Maturity Model / Integration |
| SEI | Software Engineering Institute |
| COCOMO | COnstructive COst MOdel |
| LOC / KLOC | Lines of Code / Thousand Lines of Code |
| PERT | Program Evaluation and Review Technique |
| SCM | Software Configuration Management |
| XP | Extreme Programming |
| TDD | Test Driven Development |
| MIS | Management Information System |
| TPS | Transaction Processing System |
| OAS | Office Automation System |
| KWS | Knowledge Work System |
| DSS | Decision Support System |
| ESS / EIS | Executive Support / Information System |
| CRM | Customer Relationship Management |
| ERP | Enterprise Resource Planning |
| SCM | Supply Chain Management |
| KM | Knowledge Management |
| SECI | Socialisation, Externalisation, Combination, Internalisation |
| VR / AR | Virtual / Augmented Reality |
| DDA | Digital Differential Analyser |
| SVG | Scalable Vector Graphics |
| GIMP | GNU Image Manipulation Program |
| B2B / B2C / C2C / C2B | Business/Consumer combinations in e-commerce |



### M2.6 Education



| Abbreviation | Full form |
|---|---|
| RTE | Right of children to free and compulsory Education Act, 2009 |
| RTI | Right To Information Act, 2005 |
| RPwD | Rights of Persons with Disabilities Act, 2016 |
| PwD | Persons with Disabilities Act, 1995 |
| NEP | National Education Policy, 2020 |
| NPE | National Policy on Education, 1986 |
| NCF | National Curriculum Framework, 2005 |
| DPEP | District Primary Education Programme, 1994 |
| SSA | Sarva Shiksha Abhiyan, 2000 |
| RMSA | Rashtriya Madhyamik Shiksha Abhiyan |
| ICDS | Integrated Child Development Services, 1975 |
| IEDSS | Inclusive Education for Disabled at Secondary Stage |
| CCE | Continuous and Comprehensive Evaluation |
| CWSN | Children With Special Needs |
| ZPD | Zone of Proximal Development |
| ICT | Information and Communication Technology |
| NCERT | National Council of Educational Research and Training |
| NCTE | National Council for Teacher Education |
| CBSE | Central Board of Secondary Education |
| ECCE | Early Childhood Care and Education |
| FLN | Foundational Literacy and Numeracy |



## M3 Complexity Tables



### M3.1 Sorting



| Algorithm | Best | Average | Worst | Space | Stable |
|---|---|---|---|---|---|
| Bubble | O(n) | O(n^2) | O(n^2) | O(1) | Yes |
| Selection | O(n^2) | O(n^2) | O(n^2) | O(1) | No |
| Insertion | O(n) | O(n^2) | O(n^2) | O(1) | Yes |
| Merge | O(n log n) | O(n log n) | O(n log n) | O(n) | Yes |
| Quick | O(n log n) | O(n log n) | O(n^2) | O(log n) | No |
| Heap | O(n log n) | O(n log n) | O(n log n) | O(1) | No |
| Counting | O(n+k) | O(n+k) | O(n+k) | O(k) | Yes |
| Radix | O(d(n+k)) | O(d(n+k)) | O(d(n+k)) | O(n+k) | Yes |



> **TIP: The three you must never forget**
>
> **Selection sort is O(n^2) in ALL cases.** **Merge sort is O(n log n) in ALL cases** but needs O(n) space. **Quick sort's worst case is O(n^2)**, on already-sorted data with a poor pivot.



### M3.2 Searching and data structures



| Operation | Complexity |
|---|---|
| Linear search | O(n) |
| Binary search - best | O(1) |
| Binary search - average and worst | O(log n) |
| Array access by index | O(1) |
| Array insert/delete at beginning | O(n) |
| Array insert/delete at end | O(1) |
| Linked list access i-th element | O(n) |
| Linked list insert/delete at beginning | O(1) |
| Stack push / pop / peek | O(1) |
| Queue enqueue / dequeue | O(1) |
| BST search/insert/delete - average | O(log n) |
| BST search/insert/delete - worst (skewed) | O(n) |
| AVL / Red-Black tree - all operations | O(log n) |
| Heap - find min or max | O(1) |
| Heap - insert / delete root | O(log n) |
| Build heap from n elements | O(n) |
| Hashing - average | O(1) |
| Hashing - worst | O(n) |
| BFS / DFS | O(V + E) |
| Dijkstra with heap | O(E log V) |
| Bellman-Ford | O(VE) |
| Floyd-Warshall | O(V^3) |
| Prim / Kruskal | O(E log V) |



### M3.3 Growth order



*Memorise this chain*
```
O(1) < O(log n) < O(sqrt n) < O(n) < O(n log n) < O(n^2)
     < O(n^2 log n) < O(n^3) < O(2^n) < O(n!) < O(n^n)
```



## M4 Networking Numbers



### M4.1 Layers and data units



| OSI layer | Number | Data unit | Devices |
|---|---|---|---|
| Application | 7 | Data | - |
| Presentation | 6 | Data | Encryption, compression, translation |
| Session | 5 | Data | Dialog control, synchronisation |
| Transport | 4 | SEGMENT | Ports, flow control, error control, end-to-end |
| Network | 3 | PACKET | ROUTER. IP addressing, routing, congestion control |
| Data Link | 2 | FRAME | SWITCH, BRIDGE, NIC. MAC addressing, framing, CRC |
| Physical | 1 | BIT | HUB, REPEATER, cables |



### M4.2 Port numbers



| Port | Service |
|---|---|
| 20, 21 | FTP (data, control) |
| 22 | SSH |
| 23 | TELNET |
| 25 | SMTP |
| 53 | DNS |
| 67, 68 | DHCP |
| 69 | TFTP |
| 80 | HTTP |
| 110 | POP3 |
| 143 | IMAP |
| 161 | SNMP |
| 443 | HTTPS |
| 3306 | MySQL |



### M4.3 Addressing



| Item | Value |
|---|---|
| IPv4 size | 32 bits (4 bytes) |
| IPv6 size | 128 bits |
| MAC address size | 48 bits (6 bytes) |
| Port number size | 16 bits (0 to 65535) |
| Class A range | 1 to 126, mask /8 |
| Class B range | 128 to 191, mask /16 |
| Class C range | 192 to 223, mask /24 |
| Class D | 224 to 239 - MULTICAST |
| Class E | 240 to 255 - reserved |
| Loopback | 127.0.0.1 |
| Usable hosts formula | 2^(host bits) - 2 |
| Full mesh links | n(n-1)/2 |



### M4.4 Quick facts


- ARP request = **broadcast**; ARP reply = **unicast**
- TCP header 20 to 60 bytes; UDP header **8 bytes fixed**
- TCP three-way handshake: SYN, SYN+ACK, ACK
- TCP close: four-way FIN exchange. **RST terminates immediately**
- Slow start: window **doubles every RTT**
- Congestion avoidance: window **increases by 1 MSS per RTT**
- Go-Back-N **discards** out-of-order frames; Selective Repeat **buffers** them
- Pure ALOHA efficiency 18.4%; slotted ALOHA 36.8%
- CSMA/CD is wired Ethernet; CSMA/CA is wireless Wi-Fi
- RIP metric = hop count, maximum 15; OSPF uses Dijkstra; BGP is the Internet's exterior protocol
- Optical fibre: **core refractive index greater than cladding**, so total internal reflection occurs
- Symmetric = AES, DES, 3DES, RC4, RC5, Blowfish, IDEA. Asymmetric = **RSA, Diffie-Hellman, ECC, DSA, ElGamal**
- For confidentiality encrypt with the **recipient's public key**; for a signature encrypt with the **sender's private key**


## M5 Operating System One-Liners


- OS is the **bridge between user and hardware**; the **kernel** is its always-resident core
- Translation of source to machine code is **NOT** an OS service - that is the compiler
- **Program** is passive on disk; **process** is active in execution
- Memory is fully released only on the **Running to Terminated** transition
- Waiting to Ready is legal; **Waiting to Running is NOT**
- **Burst time** = time required to EXECUTE on the CPU (not to start)
- **TAT = CT - AT** and **WT = TAT - BT**
- FCFS suffers the **convoy effect**; SJF gives minimum average waiting time; **Round Robin** is best for time-sharing
- **Priority scheduling** risks starvation, cured by **aging**
- Dispatcher performs the **context switch**, which is pure overhead
- Deadlock needs all four: mutual exclusion, hold and wait, no preemption, circular wait
- **Banker's algorithm** = deadlock **avoidance** (Dijkstra)
- **Best Fit** = smallest suitable hole; slow search, worsens external fragmentation
- Paging removes **external** fragmentation but leaves **internal** fragmentation
- Paging blocks are **fixed** size and set by the OS; **segments** are variable and set by the programmer
- **Page fault** = accessing a page not currently in memory
- **Thrashing** = more swapping than useful work
- **Belady's anomaly** occurs in **FIFO**, not in LRU or Optimal
- **Optimal** page replacement is impossible to implement (needs the future)
- **Magnetic tape** is the only sequential-access medium
- Hard links cannot cross file systems or link directories; **soft/symbolic links can**
- **Ext4** is the Linux default; **NTFS does support compression**
- SCAN goes to the **end** and reverses; LOOK reverses at the **last request**; C-SCAN **jumps back** without serving
- SSTF advantage = **average response time decreases**
- **Socket** = endpoint of IPC = IP + port + protocol
- **Shared memory** is the fastest IPC; **fork() and join()** build a complete process subroutine
- n forks create **2^n** processes
- **getpid()** = current process; **getppid()** = parent
- Linux: /etc = configuration, /bin = command binaries, /dev = device files, /tmp = temporary, /var = logs
- **rm** deletes files; **rmdir** only empty directories; **grep** searches patterns; **cut** takes columns; **tr** changes case
- Default file permission **644 (rw-r--r--)**; default directory **755**
- Shells: sh, bash, csh, tcsh, ksh, zsh. **"Alpha cell" is not a shell**
- Distributed systems: latency is a **drawback**, not a benefit


## M6 DBMS and SQL One-Liners


- **Schema** = design/structure; **instance** = data at a moment
- Relational model = **tables**, proposed by **E. F. Codd**
- **Degree = number of columns**; **Cardinality = number of rows**
- Primary key: unique and **NOT NULL**. Foreign key **may be NULL**
- **Candidate key** is a minimal super key
- Armstrong's axioms are exactly three: **Reflexivity, Augmentation, Transitivity**. Pseudo-transitivity is derived
- **1NF** atomic, **2NF** no partial dependency, **3NF** no transitive dependency, **BCNF** every determinant is a super key
- BCNF decomposition **may lose dependency preservation**; 3NF need not
- **Descriptive attributes** describe a **relationship**, not an entity
- Weak entity = double rectangle; relationship = diamond; multivalued attribute = double ellipse
- **DDL** = CREATE, ALTER, DROP, TRUNCATE (structure). **DML** = SELECT, INSERT, UPDATE, DELETE (data)
- **DELETE** is DML and can be rolled back; **TRUNCATE** and **DROP** are DDL
- Execution order: FROM, WHERE, GROUP BY, HAVING, SELECT, ORDER BY
- **WHERE** filters rows before grouping; **HAVING** filters groups after
- **COUNT(*)** includes NULL rows; **COUNT(column)** ignores NULLs
- `NULL = NULL` is **UNKNOWN**; only **`NULL IS NULL` is TRUE**
- A view is virtual; **ORDER BY is NOT allowed in a view definition**
- **ACID** = Atomicity, Consistency, Isolation, Durability
- Conflicting operations: same data item, different transactions, **at least one write**
- Conflict serialisable **if and only if the precedence graph has NO cycle**
- **2PL**: growing phase acquires, shrinking phase releases. **Conservative 2PL is deadlock free**
- **Write-ahead logging** makes recovery possible
- Only **one clustered index** per table; **B+ tree** is the standard index structure


## M7 Programming Traps



### M7.1 The traps that decide your marks



| Situation | Correct reasoning |
|---|---|
| do-while | Body runs **at least once** before the test |
| a > b > c | Left to right: (a>b) gives 0 or 1, then compared with c |
| Nested ternary | **Right to left** associativity |
| a ^ b | Bitwise **XOR**, not power |
| Inner block redeclaring a variable | Inner variable **shadows** and dies with the block |
| a = b = c = 15 | Right to left assignment |
| sprintf return value | Number of characters written, **excluding '\0'** |
| Pointer never incremented in a loop | Same element printed every time |
| `for(;;)` | All three parts optional - infinite loop |
| `while(1){}` | Infinite loop |
| `break` | Exits the loop immediately; `continue` only skips one iteration |
| `arr = "text"` after declaration | **Illegal** - array name is not a modifiable lvalue |
| register default value | **Garbage**, not zero. Only static and extern default to zero |
| switch expression | Must be **int or char**; float is illegal |
| Nested switch | **Allowed** in any case |
| 2D char array | First dimension = number of strings, second = max length |
| Java `Integer` / `String` as variable names | **Legal** - they are class names, not keywords |
| `finally` | **Always** runs, even with return or an exception |
| Re-thrown exception | Matches catch blocks of the **NEW** type only |
| `final` method | **Cannot** be overridden |
| `super` | Refers to the **parent class** |
| Operator overloading | Supported in C++, **not in Java** |
| Multiple inheritance of classes | C++ yes, **Java no** (interfaces instead) |
| Access order (most to least restrictive) | private, default, protected, public |
| `cin.ignore(x, y)` | Skips first x characters, stops at delimiter y |
| Highest precedence arithmetic operator | `%` (same level as `*` and `/`) |



### M7.2 Header files


| Header | Contents |
|---|---|
| stdio.h | printf, scanf, sprintf, fopen, gets, puts |
| stdlib.h | malloc, calloc, realloc, free, exit, atoi, rand |
| string.h | strlen, strcpy, strcat, strcmp |
| math.h | sqrt, pow, floor, ceil |
| ctype.h | isalpha, isdigit, toupper |
| stdarg.h | va_list, va_start, va_arg (variable arguments) |
| unistd.h | fork, exec, pipe, sleep, getpid |



### M7.3 OOP in one line each

- **Encapsulation** - bundling data and methods in one unit, hiding internals
- **Inheritance** - a child class acquires a parent's properties
- **Polymorphism** - one name, many forms (overloading = compile time, overriding = run time)
- **Abstraction** - showing only essential features
- **Class** = blueprint (no memory); **object** = instance (has memory)
- **Constructor** - same name as class, no return type, runs automatically
- **Abstract class** - cannot be instantiated
- **Interface** - a pure contract; Java 8+ allows `default` methods


## M8 Digital Logic and Architecture



### M8.1 Gates and codes


- **Universal gates: NAND and NOR** - either alone can build every other gate
- **XOR** = 1 when inputs **differ**; **XNOR** = 1 when inputs are the **same**
- **De Morgan**: (A+B)' = A'B' and (AB)' = A'+B'
- **K-map rows and columns use GRAY code** (00, 01, 11, 10), not binary
- Group only **1s** for SOP, only **0s** for POS; groups must be powers of two
- Group of 2 removes 1 variable; group of 4 removes 2; group of 8 removes 3
- Half adder: Sum = A XOR B, Carry = A AND B
- Full adder = two half adders + one OR gate
- **BCD adder: 256 total, 100 valid, 156 invalid** input combinations
- BCD invalid patterns: 1010 to 1111 (six of them)
- **Gray code**: first bit copied, then each bit = XOR of adjacent binary bits
- Binary to octal: group **3** bits. Binary to hex: group **4** bits
- **n ones in binary = 2^n - 1** (so 111111 = 63)
- **2's complement** = invert all bits, then add 1
- **Right shift = divide by 2; left shift = multiply by 2**
- MUX = many inputs to one output; DEMUX = one to many
- Decoder: n inputs to 2^n outputs; Encoder: 2^n inputs to n outputs
- SR flip-flop forbidden state: **S = R = 1**. JK fixes it by toggling
- **Cascaded counters MULTIPLY their moduli** (Mod-6 x Mod-8 = Mod-48)
- Ripple counter delays **add up**; synchronous counters do not


### M8.2 Architecture


- **RISC is the most energy efficient** - simple fixed-length instructions, hardwired control
- CISC = many complex variable-length instructions, microprogrammed control
- **Von Neumann** shares one memory/bus for code and data; **Harvard** separates them
- **Control Unit** manages the **Fetch-Decode-Execute-Store** cycle
- Instruction cycle phases: Fetch, Decode, Execute, Store. **"Encode" is not a phase**
- A **bus is a set of parallel lines**
- **n address lines address 2^n locations**
- Accumulator size = word size = **4 bytes** on a 32-bit machine
- `ADD R1, [R2]` = **register indirect** addressing (brackets mean pointer)
- Cache TAG bits = total address bits - set bits - offset bits
- Cache mapping: direct (one slot), fully associative (any slot), set associative (any slot in one set)
- Average access time = H x cache time + (1 - H) x miss penalty
- **Write-through** updates memory immediately; **write-back** uses a dirty bit
- **Bootstrap program is in ROM**; **CMOS is powered by a motherboard battery**; **POST runs at start-up**
- **EPROM erased by ultraviolet light**; EEPROM and Flash erase electrically
- **SRAM needs no refresh** (static); DRAM must be refreshed
- Memory hierarchy: registers, cache, RAM, secondary, tertiary
- 1 KB = 1024 bytes; **4 KB = 4096 bytes** (not 4069); 1 nibble = 4 bits


## M9 Web Technologies


- **href** creates a hyperlink; **_top** opens in the full window body; **_blank** opens a new tab
- External CSS uses **`<link rel="stylesheet" type="text/css" href="...">`**
- Internal CSS uses `<style>`; inline CSS uses the `style` attribute
- CSS specificity: **inline > ID > class > element**; `!important` beats all
- Box model order: content, padding, border, margin
- Grey filter: **`img { filter: grayscale(100%); }`**
- **`\n` does NOT create a line break in rendered HTML** - whitespace collapses; use `<br>`
- DOM style change: **`element.style.backgroundColor = "red"`** (camelCase, no hyphen)
- Window resize: **`window.resizeTo()`**
- jQuery sliding: **slideDown(), slideUp(), slideToggle()**
- AngularJS two-way binding: **`ng-model`**
- **AJAX** exchanges only small amounts of data, so it reduces bandwidth and avoids full reloads
- **XML processor** reads XML and exposes content and structure
- **DOM parser** = tree in memory, can modify. **SAX parser** = event-based, memory-efficient, read-only. **Shell is NOT a parser**
- External DTD: **`<!DOCTYPE root-element SYSTEM "file-name">`** - root element comes first
- XML is **case sensitive**, needs exactly **one root**, and every tag **must** be closed
- PHP: **`asort()`** sorts values ascending and **preserves keys**; `sort()` reindexes; `ksort()` sorts by key
- PHP variables start with **$**; `.` is string concatenation; double quotes interpolate
- **HTTP is stateless**; cookies give it memory
- Status codes: 200 OK, 301 moved, 404 not found, 500 server error
- **CGI** defines how a web server talks to an application program; **HTTP** defines browser-to-server
- **ODBC / JDBC** connect an application program to a database server
- E-commerce: **OLX = C2C**; Amazon = B2C; IndiaMART = B2B; GeM = B2G
- **Subscription** = fixed recurring payment. **Web surfing** = visiting different sites
- **K Vaitheeswaran** = father of e-commerce in **India**; **Michael Aldrich** = inventor of online shopping globally


## M10 Formula Sheet



### M10.1 Computer science formulas



*Essential formulas*
```
NUMBER SYSTEMS
   n ones in binary          = 2^n - 1
   2's complement            = invert all bits + 1
   r's complement            = r^n - N
   Right shift by k          = divide by 2^k
   Left  shift by k          = multiply by 2^k

MEMORY AND CACHE
   Addressable locations     = 2^(address lines)
   Cache lines               = cache size / block size
   Sets                      = lines / associativity
   TAG bits                  = total bits - set bits - offset bits
   Average access time       = H x Tc + (1 - H) x miss penalty

NETWORKS
   Usable hosts              = 2^(host bits) - 2
   Total subnets             = 2^(borrowed bits)
   Full mesh links           = n(n-1)/2
   Block size                = 256 - (mask octet)

OS SCHEDULING
   Turn Around Time (TAT)    = Completion Time - Arrival Time
   Waiting Time (WT)         = TAT - Burst Time
   Response Time             = first CPU allocation - Arrival Time
   Throughput                = processes completed / total time

DIGITAL LOGIC
   Cascaded counter modulus  = product of the moduli
   Max modulus of n flip-flops = 2^n
   Ripple counter error at   t = clock period / number of flip-flops
   Max nodes at level l (tree) = 2^l
   Max nodes in tree height h  = 2^(h+1) - 1
   Edges in a tree of n nodes  = n - 1
   Complete graph edges        = n(n-1)/2
   MST edges                   = V - 1

SOFTWARE ENGINEERING
   Cyclomatic complexity V(G) = E - N + 2 = decision points + 1
```



### M10.2 Mathematics, statistics and physics formulas



*Formulas from the non-CS questions*
```
PROBABILITY
   P(E)                = favourable / total
   P(A or B)           = P(A) + P(B) - P(A and B)
   P(not A)            = 1 - P(A)
   Bayes               = P(B|A) P(A) / P(B)
   Chi-square df       = (rows - 1)(columns - 1)

STATISTICS
   Sum of deviations from the ARITHMETIC MEAN = 0
   AM >= GM >= HM
   Variance            = mean of squared deviations
   Coefficient of variation = (SD / Mean) x 100

NUMERICAL METHODS
   Delta               = E - 1
   mu^2                = (delta^2 + 4) / 4
   Delta^n e^(ax+b)    = (e^(ah) - 1)^n e^(ax+b)
   p-series SUM 1/n^p converges if p > 1

CALCULUS AND ALGEBRA
   Euler (homogeneous degree n):  x fx + y fy = n f
   Any function of (y/x) is homogeneous of degree 0, so the sum = 0
   Normal to surface F = 0 is grad F; unit normal = grad F / |grad F|
   Tetrahedron volume (x/a + y/b + z/c = 1) = abc / 6
   2x2 characteristic equation: L^2 - (trace)L + (determinant) = 0
   Repeated root r of multiplicity k with forcing e^(rt): PI carries t^k

PHYSICS
   Photon energy       E (eV) = 12400 / lambda (Angstrom)
   E = hc / lambda ,  h = 6.626e-34 ,  c = 3e8
   Spring period       T = 2 pi sqrt(m/k)
   Static extension    x = g T^2 / (4 pi^2)      (mass cancels)
   Terminal PD         V = EMF - I r
   Cells in series     EMF adds, r adds
   Cells in parallel   EMF same, r becomes r/n
   Malus's law         I = I0 cos^2(theta)
   Brewster            tan(angle) = refractive index

ACCOUNTING
   Gross Profit        = Net Sales - COGS
   COGS                = Opening Stock + Purchases + Direct Expenses - Closing Stock
   Net Profit          = Gross Profit + Other Income - Indirect Expenses
   Assets              = Liabilities + Capital
   Working Capital     = Current Assets - Current Liabilities
   Stock lost by fire  = Stock on date of fire - Stock salvaged
   Marginal Revenue    = change in Total Revenue / change in Output
   Elasticity          = % change in quantity / % change in price
```



## M11 People, Inventions and Firsts



| Person | Known for |
|---|---|
| Charles Babbage | **Father of the Computer** - Difference and Analytical Engine |
| Ada Lovelace | The first programmer |
| Alan Turing | Turing machine, father of theoretical CS and AI |
| John von Neumann | Stored-program concept, von Neumann architecture |
| Blaise Pascal | Pascaline mechanical calculator |
| Herman Hollerith | Punched cards; founded the company that became IBM |
| Tim Berners-Lee | **World Wide Web** |
| Dennis Ritchie | **C language** and UNIX |
| Ken Thompson | UNIX |
| Bjarne Stroustrup | **C++** |
| James Gosling | **Java** |
| Guido van Rossum | **Python** |
| Linus Torvalds | **Linux kernel** |
| Rasmus Lerdorf | PHP |
| Brendan Eich | JavaScript |
| E. F. Codd | **Relational database model** |
| Peter Chen | ER model |
| Edsger Dijkstra | Shortest path algorithm, Banker's algorithm, semaphores |
| Barry Boehm | **COCOMO** and the **Spiral model** |
| Winston Royce | Waterfall model |
| Watts Humphrey / SEI | **CMM** |
| Tom McCabe | Cyclomatic complexity |
| Pierre-Simon Laplace | **Classical definition of probability** |
| Jan Koum and Brian Acton | **WhatsApp** |
| Larry Page and Sergey Brin | Google |
| Mark Zuckerberg | Facebook |
| K Vaitheeswaran | **Father of e-commerce in India** |
| Michael Aldrich | Invented online shopping (1979, globally) |



## M12 Teaching Methodology One-Liners



### M12.1 Theorists



| Theorist | Core contribution |
|---|---|
| PIAGET | Cognitive development in 4 stages: **0-2 sensorimotor, 2-7 pre-operational, 7-11 concrete operational, 11+ FORMAL OPERATIONAL**. Assimilation, accommodation, conservation, egocentrism |
| VYGOTSKY | **Socio-cultural** theory. **ZPD** and **scaffolding**. Language drives thought; learning leads development |
| ERIKSON | **8 psychosocial stages**. Stage 5 (12-19) = Identity vs Role Confusion. A **Neo-Freudian** |
| MARCIA | Identity statuses: diffusion, foreclosure, **MORATORIUM (actively exploring, not yet committed)**, achievement |
| KOHLBERG | Moral development: pre-conventional, conventional, post-conventional (3 levels, 6 stages) |
| FREUD | Id, Ego, Superego; psychosexual stages |
| SULLIVAN | **Interpersonal theory** - a **Neo-Freudian** |
| PAVLOV | Classical conditioning (association) |
| SKINNER | Operant conditioning (consequences), programmed instruction |
| THORNDIKE | Trial and error; **Laws of Readiness, Exercise and Effect** |
| KOHLER | **Insight learning** (Gestalt), chimpanzee experiments |
| BANDURA | **Observational / social learning**, Bobo doll |
| BRUNER | Discovery learning, spiral curriculum |
| AUSUBEL | Advance organisers |
| MASLOW | Hierarchy of needs |
| GARDNER | **Multiple intelligences** (8 types) |
| STERNBERG | Triarchic theory of intelligence |
| KOLB | **EXPERIENTIAL learning** - 4-stage cycle and 4 learning styles |
| HERBART | **5 lesson-plan steps**: Preparation, Presentation, Association, Generalisation, Application |
| HENRY EDWARD ARMSTRONG | **HEURISTIC method** of teaching **science** |
| KILPATRICK | **Project method** |
| DEWEY | Learning by doing, pragmatism |
| MONTESSORI | Self-directed activity for young children |
| FROEBEL | Kindergarten, play-based learning |



### M12.2 Rapid facts


- **Growth** = quantitative and stops; **development** = qualitative and lifelong
- Development is **cephalocaudal** (head to toe) and **proximodistal** (centre outward)
- **Auditory-visual coordination is present from BIRTH**
- Newborn acuity: stripes **1/8 inch at birth**, **1/64 inch by three months**
- **Broca's and Wernicke's areas are in the LEFT hemisphere**
- **Object permanence** develops around 8 months (sensorimotor stage)
- **Conservation** is achieved in the **concrete operational** stage
- **Horizontal decalage** = inconsistency across different conservation tasks in the same stage
- **Over-generalisation** = word applied too broadly (all animals are "doggie"); **under-generalisation** = too narrowly (only his toy duck)
- **Authoritative** parenting (high control + high warmth) gives the best outcomes; **give-and-take parents produce give-and-take children**
- Learning as **meaning making** implies **student-centred** teaching (constructivism)
- **Approach** is broadest, then **method**, then **strategy**, then **technique**
- Herbart's five steps **do NOT include Evaluation**
- A **unit plan** requires forming units/sub-units AND determining assessment methods
- **Diagnostic** assessment identifies **misconceptions**; **formative** guides teaching; **summative** grades
- **CCE** = Continuous **and** Comprehensive Evaluation
- Bloom revised cognitive levels end with **CREATING** as the highest
- ICT assessment excludes anything done **on paper**
- **ICDS (1975)** serves children **below 6 years**, plus pregnant and nursing mothers, via **Anganwadis**
- **Mid-Day Meal / PM POSHAN** serves **school-going** children
- **DPEP** launched 1994; **inclusive education added to DPEP in 1997**; **Salamanca Statement 1994**
- **RTE Act 2009** (in force 1 April 2010) - free and compulsory education ages **6 to 14**, **Article 21A**
- **RPwD Act 2016** - **21 disabilities**, 4% job reservation, **legally mandates inclusion in mainstream schools**
- **NEP 2020** - **5+3+3+3+4** structure, mother tongue up to Grade 5, 6% of GDP
- **Kothari Commission (1964-66)** recommended 6% of GDP and the 10+2+3 pattern
- **Gender** is socially constructed; **sex** is biological. Gender inequality = **social and economic disparities**
- **Multilingual approach** welcomes the child's home language as a bridge
- **Aesthetic education** develops **sensory responsiveness**
- A **subject** is the branch of a **discipline** taught in the classroom
- **Community service** means the student **gives** to the community, not merely collects information
- A teacher gains community acceptance by helping with **sanitation and agriculture** problems
- Seating: special-needs child **near the board**; group work in **clusters**; discussion in a **circle**; performing arts need **open space**
- **Vocational curriculum** needs the **principle of activity and practicality** for skill transfer


## M13 Final Words



### M13.1 Exam-hall strategy



| Rule | Reason |
|---|---|
| Do the Teaching Methodology section FIRST | It is the fastest and most certain scoring section. Banking those marks early settles your nerves |
| Then do your strongest CS topic | Momentum matters. Build confidence before you meet hard questions |
| Skip anything needing more than 90 seconds | Mark it and return. One hard question is worth the same as one easy one |
| Read "NOT", "FALSE", "EXCEPT" and "INCORRECT" twice | A large share of DSSSB questions are negatively framed. Circle the negative word on the paper |
| Eliminate before you guess | With four options, eliminating two makes a guess worth taking despite negative marking. Eliminating none makes it a loss |
| Never leave a question you can narrow to two | Expected value is positive: 0.5 x (+1) + 0.5 x (-0.25) = +0.375 |
| Leave pure blind guesses blank | Expected value is negative: 0.25 x (+1) + 0.75 x (-0.25) = +0.0625, which is marginal, and worse if a distractor is attractive |
| Keep 10 minutes for review | Check that no OMR bubble is misaligned - a shifted row costs an entire section |



### M13.2 A last thought


You have now worked through every topic that appeared in three real DSSSB TGT Computer Science papers, plus the surrounding concepts most likely to appear next. That is more preparation than most candidates in the hall will have.

Two reminders as you close this book.

**First, the paper rewards breadth, not depth.** You do not need to be a specialist in operating systems. You need to reliably recognise 100 one-line facts across forty topics. Revision beats new learning in the final weeks.

**Second, the negatively framed questions are where marks are won and lost.** Read every question twice, and circle the words NOT, FALSE, EXCEPT and INCORRECT with your pencil before you look at the options.

Work steadily, revise Part M often, and re-solve the papers in Part L until every explanation feels obvious. That is enough.

All the best.
