
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

