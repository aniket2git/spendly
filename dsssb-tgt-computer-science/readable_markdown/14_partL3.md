
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

