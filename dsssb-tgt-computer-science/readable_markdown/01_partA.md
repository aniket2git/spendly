
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

