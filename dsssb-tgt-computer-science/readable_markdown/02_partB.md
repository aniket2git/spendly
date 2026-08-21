
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

