
---

# PART 5 - Data Structures and Algorithms

> *Weightage: 6 to 9 marks in DSSSB, 6 to 12 expected. Almost pure recall once the complexity tables are memorised.*



## 5.1 Complexity Analysis



> **WEIGHTAGE: 2-3 marks | Complexity of a named algorithm is asked in every paper | Priority CRITICAL**



### 5.1.1 Questions



**Q. [PYQ] Which of the following asymptotic notation gives asymptotically tight upper bound as well as asymptotically tight lower bound?**

- (a) Omega
- (b) Big Oh
- (c) **Theta  <-- CORRECT**
- (d) Small Omega

> **Why:** The words "**as well as**" demand both bounds simultaneously - that is **Theta**. Big Oh gives only the upper bound, Omega only the lower, and small omega is not even tight.



**Q. [PYQ] Which of the following cases DOES NOT exist when one computes the time complexity of an algorithm?**

- (a) Average case
- (b) Worst case
- (c) **Test Case  <-- CORRECT**
- (d) Best Case

> **Why:** Only **best, average and worst** exist. "Test case" belongs to software testing.



**Q. [PYQ] Arrange the following in the order of growth: O(n), O(n^2), O(2^n), O(log n), O(n log n), O(n^2 log n)**

- (a) O(n), O(n^2), O(log n), O(2^n), O(n log n), O(n^2 log n)
- (b) O(n), O(2^n), O(2^n), O(log n), O(n^2 log n), O(n log n)
- (c) **O(log n), O(n), O(n log n), O(n^2), O(n^2 log n), O(2^n)  <-- CORRECT**
- (d) O(n^2), O(n), O(2^n), O(log n), O(n log n), O(n^2 log n)

> **Why:** Substitute n = 1024 (so log n = 10) and compare: 10 < 1024 < 10,240 < 1,048,576 < 10,485,760 < 2^1024. **Rule: polynomials always beat exponentials, and a log factor is weaker than one extra power of n.**



**Q. [EXPECTED] Which of the following grows fastest for large n?**

- (a) n^3
- (b) n^2 log n
- (c) **2^n  <-- CORRECT**
- (d) n log n

> **Why:** Exponential growth eventually dominates every polynomial, no matter how large the exponent. Full chain: **O(1) < O(log n) < O(sqrt n) < O(n) < O(n log n) < O(n^2) < O(n^3) < O(2^n) < O(n!) < O(n^n)**.



**Q. [PYQ] [TRAP] Which statement is correct about the divide and conquer approach of binary search?**

- (a) The recurrence relation of binary search is T(n) = 2T(n/2) + O(1).
- (b) **The worst-case time complexity of binary search is O(log n).  <-- CORRECT**
- (c) The best-case time complexity of binary search is O(log n).
- (d) The average-case time complexity of binary search is O(n).

> **Why:** Binary search discards half and searches **only one** half, so the recurrence is **T(n) = T(n/2) + O(1)** - the coefficient is 1, not 2. Its **best case is O(1)** (target is the middle element immediately), average and worst are O(log n).



**Q. [EXPECTED] The recurrence T(n) = 2T(n/2) + O(n) solves to:**

- (a) O(n)
- (b) O(log n)
- (c) **O(n log n)  <-- CORRECT**
- (d) O(n^2)

> **Why:** This is the **merge sort** recurrence. Learn the standard set: T(n)=T(n/2)+O(1) gives O(log n) (binary search); T(n)=2T(n/2)+O(1) gives O(n); T(n)=T(n-1)+O(n) gives O(n^2); T(n)=2T(n-1)+O(1) gives O(2^n) (Tower of Hanoi).



**Q. [EXPECTED] A precondition for applying binary search is that the array must be:**

- (a) of even length
- (b) **sorted  <-- CORRECT**
- (c) of numeric type
- (d) stored in a linked list

> **Why:** Binary search relies on discarding half based on an ordering comparison, so the data **must already be sorted**. This is also why binary search is impractical on linked lists - no random access to the middle.



## 5.2 Linear Data Structures



> **WEIGHTAGE: 2-4 marks | Linked-list properties are a repeat favourite | Priority CRITICAL**



### 5.2.1 Questions



**Q. [PYQ] What are the data structures categorised as a linear list?**

- (a) Binary tree
- (b) Graphs
- (c) Circular queue
- (d) **Array  <-- CORRECT**

> **Why:** A **linear list** means a strict sequence where each element has one predecessor and one successor. Trees and graphs are non-linear; a circular queue links its last element back to the first, breaking the plain sequence.



**Q. [PYQ] In a singly linked list, each node of the list consists of __________.**

- (a) **data value and address of next node  <-- CORRECT**
- (b) NULL and address of the next node
- (c) NULL and address of the previous node
- (d) data value and address of previous node

> **Why:** Only the **last** node holds NULL. An address of the *previous* node indicates a **doubly** linked list.



**Q. [PYQ] [TRAP] Which of the following is a disadvantage of singly linked list?**

- (a) **Accessing an element requires traversal from the head, making it slower than arrays.  <-- CORRECT**
- (b) Deletion at the beginning is performed in O(1) time.
- (c) Insertion at the beginning is performed in O(1) time.
- (d) Linked lists have a variable size.

> **Why:** Three options are genuine **advantages** disguised as answers. The real weakness is **no random access**: reaching the i-th element costs O(n), whereas an array does it in O(1).



**Q. [PYQ] [NUMERICAL] Calculate the time complexity of deleting an element from the beginning of a dynamic array.**

- (a) O(log)
- (b) O(1)
- (c) O(log n)
- (d) **O(n)  <-- CORRECT**

> **Why:** After removing a[0], all remaining n-1 elements must **shift left** to preserve contiguity. Only deletion at the **end** is O(1).



**Q. [EXPECTED] [NUMERICAL] What is the time complexity of inserting at the beginning of a singly linked list?**

- (a) O(n)
- (b) **O(1)  <-- CORRECT**
- (c) O(log n)
- (d) O(n^2)

> **Why:** Just create the node and repoint the head - no shifting. This is exactly where linked lists beat arrays.



**Q. [EXPECTED] A stack follows which order?**

- (a) FIFO
- (b) **LIFO  <-- CORRECT**
- (c) Priority order
- (d) Random

> **Why:** **LIFO** - Last In First Out, like a pile of plates. push, pop and peek are all **O(1)**.



**Q. [EXPECTED] [TRAP] Which of the following is NOT an application of a stack?**

- (a) Recursion / function call management
- (b) Infix to postfix conversion
- (c) Balanced parentheses checking
- (d) **CPU scheduling ready queue  <-- CORRECT**

> **Why:** The ready queue is FIFO, so it uses a **queue**. Stack applications: function call stack, recursion, expression conversion and evaluation, parenthesis matching, undo/redo, browser back button, **DFS**, backtracking, string reversal.



**Q. [EXPECTED] Which traversal technique uses a queue?**

- (a) DFS
- (b) **BFS  <-- CORRECT**
- (c) Inorder traversal
- (d) Postorder traversal

> **Why:** **BFS uses a QUEUE** and explores level by level; **DFS uses a STACK** (or recursion) and dives deep first. Both are O(V + E).



**Q. [EXPECTED] [TRAP] What problem does a circular queue solve?**

- (a) Overflow
- (b) **Wastage of space at the front after repeated deletions  <-- CORRECT**
- (c) Underflow
- (d) Slow enqueue

> **Why:** In a simple linear queue, once front advances, the vacated cells at the start cannot be reused and the queue appears full while space remains. A **circular queue** wraps rear around to index 0.



**Q. [EXPECTED] In a priority queue, the element dequeued first is:**

- (a) the one inserted first
- (b) the one inserted last
- (c) **the one with the highest priority  <-- CORRECT**
- (d) a random element

> **Why:** Arrival order is irrelevant. Priority queues are normally implemented with a **heap**, giving O(log n) insert and O(log n) extract.



**Q. [EXPECTED] Which notation requires no parentheses and no precedence rules for evaluation?**

- (a) Infix
- (b) **Postfix  <-- CORRECT**
- (c) Both infix and prefix
- (d) None

> **Why:** **Postfix (Reverse Polish)** can be evaluated in one left-to-right pass with a single stack, which is why compilers convert infix expressions to postfix.



## 5.3 Trees and Graphs



> **WEIGHTAGE: 2-3 marks | Traversal order and BST properties recur | Priority HIGH**



### 5.3.1 Questions



**Q. [EXPECTED] [TRAP] Which traversal of a Binary Search Tree yields elements in sorted ascending order?**

- (a) Preorder
- (b) **Inorder  <-- CORRECT**
- (c) Postorder
- (d) Level order

> **Why:** **Inorder (Left, Root, Right)** on a BST always produces sorted output - a very frequently asked property. Memory hook: the word tells you where the ROOT goes - **Pre**order root first, **In**order root in between, **Post**order root last. Left always precedes right.



**Q. [EXPECTED] [NUMERICAL] For the tree with root A, left child B, right child C, and B having children D and E, the preorder traversal is:**

- (a) D B E A C
- (b) **A B D E C  <-- CORRECT**
- (c) D E B C A
- (d) A B C D E

> **Why:** Preorder = Root, Left subtree, Right subtree: A, then B's subtree (B, D, E), then C = **A B D E C**. (Inorder would be D B E A C; postorder D E B C A; level order A B C D E.)



**Q. [EXPECTED] [NUMERICAL] The maximum number of nodes in a binary tree of height 3 (root at level 0) is:**

- (a) 8
- (b) **15  <-- CORRECT**
- (c) 16
- (d) 7

> **Why:** Maximum nodes = **2^(h+1) - 1** = 2^4 - 1 = **15**. Maximum nodes at a single level l is 2^l. A tree with n nodes always has exactly **n - 1 edges**.



**Q. [EXPECTED] [TRAP] The worst-case time complexity of searching in a Binary Search Tree is:**

- (a) O(log n) always
- (b) **O(n) when the tree is skewed  <-- CORRECT**
- (c) O(1)
- (d) O(n log n)

> **Why:** Inserting keys in **sorted order** degenerates a BST into a linked list, making search O(n). **Self-balancing trees** fix this: AVL and Red-Black guarantee O(log n).



**Q. [EXPECTED] In an AVL tree, the balance factor of every node must be:**

- (a) 0 only
- (b) **-1, 0 or +1  <-- CORRECT**
- (c) between -2 and +2
- (d) equal for all nodes

> **Why:** Balance factor = height(left) - height(right). Violations are repaired by **rotations** (LL, RR, LR, RL). AVL is more strictly balanced than Red-Black, so lookups are faster but insertions cost more rotations.



**Q. [EXPECTED] [TRAP] Which tree structure is standard for database indexing?**

- (a) AVL tree
- (b) Binary search tree
- (c) **B+ tree  <-- CORRECT**
- (d) Heap

> **Why:** **B+ trees** keep all data in linked leaf nodes, which makes **range queries** efficient, and their high branching factor minimises **disk reads** - the dominant cost in databases. B-trees and B+ trees are designed around disk block size.



**Q. [EXPECTED] In a max heap, the largest element is located:**

- (a) at the last leaf
- (b) **at the root  <-- CORRECT**
- (c) at the middle
- (d) anywhere

> **Why:** Max heap: every parent is at least as large as its children, so the maximum sits at the root and can be read in **O(1)**. Insert and delete-root are O(log n); building a heap from n elements is **O(n)**.



**Q. [EXPECTED] [NUMERICAL] For a node at index i in a 0-based array heap, the left child is at:**

- (a) 2i
- (b) **2i + 1  <-- CORRECT**
- (c) 2i + 2
- (d) i/2

> **Why:** Left = 2i+1, right = 2i+2, parent = (i-1)/2. (In 1-based indexing it is 2i and 2i+1 with parent i/2.)



**Q. [PYQ] [NUMERICAL] What are the articulation points in the given graph (vertices 1-10, with 9 and 10 hanging off 3, and 6 hanging off 5)?**

- (a) 1, 2 and 3
- (b) 2, 3 and 4
- (c) 3, 4 and 5
- (d) **2, 3 and 5  <-- CORRECT**

> **Why:** Remove each vertex and check whether the graph splits. Removing **3** isolates 9 and 10; removing **2** separates the left cluster from the right; removing **5** isolates 6. Vertices 1 and 4 leave the graph connected. **A leaf can never be an articulation point**, and any vertex that is the sole gateway to a region always is.



**Q. [PYQ] [NUMERICAL] In a path-graph having n vertices where n > 2, ______ is the number of vertices with degree 2.**

- (a) 3
- (b) **n - 2  <-- CORRECT**
- (c) 2
- (d) 0

> **Why:** A path is a straight line v1-v2-...-vn. The **two end vertices have degree 1**; every one of the remaining **n - 2** middle vertices has degree 2. Check with n=5: degrees are 1,2,2,2,1, so three vertices of degree 2 = 5-2.



**Q. [EXPECTED] [NUMERICAL] How many edges does a complete graph with 6 vertices have?**

- (a) 30
- (b) **15  <-- CORRECT**
- (c) 12
- (d) 36

> **Why:** **n(n-1)/2** = 6 x 5 / 2 = **15** for an undirected complete graph. The same formula gives the number of links in a full mesh network topology.



**Q. [EXPECTED] [TRAP] Which algorithm finds the shortest path in a graph with NEGATIVE edge weights?**

- (a) Dijkstra
- (b) Prim
- (c) **Bellman-Ford  <-- CORRECT**
- (d) Kruskal

> **Why:** **Dijkstra fails with negative weights** because its greedy choice becomes invalid. **Bellman-Ford** handles them and additionally detects negative cycles, at O(VE). Prim and Kruskal build minimum spanning trees, not shortest paths.



**Q. [EXPECTED] A minimum spanning tree of a graph with V vertices has exactly:**

- (a) V edges
- (b) **V - 1 edges  <-- CORRECT**
- (c) V + 1 edges
- (d) E - V edges

> **Why:** Any spanning tree on V vertices is a tree, so it has **V - 1** edges and no cycles. Prim and Kruskal are the two standard greedy algorithms.



**Q. [EXPECTED] Which representation is preferable for a sparse graph?**

- (a) Adjacency matrix
- (b) **Adjacency list  <-- CORRECT**
- (c) Incidence matrix
- (d) Edge weight matrix

> **Why:** Adjacency **list** costs O(V + E) space and lists a vertex's neighbours quickly. Adjacency **matrix** costs O(V^2) regardless of edge count but answers "is there an edge u-v?" in O(1) - better for dense graphs.



## 5.4 Searching, Sorting and Design Techniques



> **WEIGHTAGE: 2-4 marks | Sorting complexity is the most repeated fact in this topic | Priority CRITICAL**



### 5.4.1 Questions



**Q. [PYQ] What is the best case and worst-case complexity of selection sort?**

- (a) O(n log n)
- (b) O(n)
- (c) **O(n^2)  <-- CORRECT**
- (d) O(log n)

> **Why:** Selection sort always scans the whole unsorted portion to find the minimum, so the comparison count n(n-1)/2 is **independent of the input order**. Contrast with bubble and insertion sort, which do have an O(n) best case on already-sorted data.



**Q. [PYQ] What is the average case time complexity of merge sort?**

- (a) **O(n log n)  <-- CORRECT**
- (b) O(n)
- (c) O(1)
- (d) O(n^2 log n)

> **Why:** Merge sort always splits exactly in half, so **best = average = worst = O(n log n)**. Its one weakness is needing **O(n) extra space**, so it is not in-place.



**Q. [EXPECTED] [TRAP] Which sorting algorithm has the worst case O(n^2) but is usually fastest in practice for arrays?**

- (a) Merge sort
- (b) Heap sort
- (c) **Quick sort  <-- CORRECT**
- (d) Bubble sort

> **Why:** **Quick sort** degrades to O(n^2) when the pivot is always the smallest or largest element (e.g. sorted input with a first-element pivot), but its low constant factors and cache friendliness make it the practical winner. Cure the worst case with a random or median-of-three pivot.



**Q. [PYQ] [TRAP] Which sorting technique is best for sorting a linked list with n elements?**

- (a) Insertion sort
- (b) Bubble sort
- (c) **Merge sort  <-- CORRECT**
- (d) Selection sort

> **Why:** Quick sort needs **random access** to reach the pivot, which a linked list cannot provide. Merge sort only ever traverses sequentially and relinks pointers - and on a linked list it needs **no extra array**, so its auxiliary space drops to O(1). It is also stable.



**Q. [EXPECTED] Which of the following sorting algorithms is NOT stable?**

- (a) Insertion sort
- (b) Merge sort
- (c) Bubble sort
- (d) **Quick sort  <-- CORRECT**

> **Why:** **Stable** (equal elements keep relative order): bubble, insertion, merge, counting, radix. **Unstable**: selection, quick, heap.



**Q. [EXPECTED] Which comparison-based sorting algorithm has O(n log n) worst case AND O(1) auxiliary space?**

- (a) Merge sort
- (b) Quick sort
- (c) **Heap sort  <-- CORRECT**
- (d) Insertion sort

> **Why:** **Heap sort** is the only common algorithm achieving both. Merge sort needs O(n) space; quick sort's worst case is O(n^2).



**Q. [EXPECTED] The theoretical lower bound for any comparison-based sorting algorithm is:**

- (a) O(n)
- (b) **O(n log n)  <-- CORRECT**
- (c) O(log n)
- (d) O(n^2)

> **Why:** No comparison sort can beat O(n log n) in the worst case. **Counting, radix and bucket sort** appear to beat it only because they do not compare elements - they use the key values directly.



**Q. [PYQ] Which of the following algorithm design techniques is used in the merge sort algorithm?**

- (a) Greedy algorithm
- (b) Backtracking
- (c) **Divide and conquer  <-- CORRECT**
- (d) Divide and conquer, backtracking and greedy algorithm

> **Why:** Merge sort divides into halves, conquers recursively, then combines - the textbook three steps.



**Q. [PYQ] [TRAP] Which of the following is NOT the application of Divide and Conquer?**

- (a) Binary Search
- (b) **All Pairs Shortest Path Problem  <-- CORRECT**
- (c) Quick Sort
- (d) Strassen's Matrix Multiplication

> **Why:** All-pairs shortest path is solved by **Floyd-Warshall**, which is **dynamic programming** - its subproblems **overlap** and are stored and reused. Divide and conquer requires **independent** subproblems. That overlap is the exact dividing line between the two techniques.



**Q. [EXPECTED] [TRAP] Which technique solves problems with overlapping subproblems by storing results?**

- (a) Divide and conquer
- (b) Greedy
- (c) **Dynamic programming  <-- CORRECT**
- (d) Backtracking

> **Why:** DP uses **memoisation or tabulation** to compute each subproblem once. Classic DP: Floyd-Warshall, Bellman-Ford, **0/1 knapsack**, longest common subsequence, matrix chain multiplication.



**Q. [EXPECTED] [TRAP] The fractional knapsack problem is solved optimally by which technique?**

- (a) Dynamic programming
- (b) **Greedy  <-- CORRECT**
- (c) Backtracking
- (d) Branch and bound

> **Why:** **Fractional** knapsack yields to a greedy choice (highest value-to-weight ratio first). The **0/1** knapsack does **not** - it needs dynamic programming. This pair is a favourite discriminator.



**Q. [EXPECTED] Which technique abandons a partial solution as soon as it cannot lead to a valid answer?**

- (a) Greedy
- (b) Dynamic programming
- (c) **Backtracking  <-- CORRECT**
- (d) Divide and conquer

> **Why:** **Backtracking** prunes the search tree. Classic problems: N-Queens, Sudoku, **sum of subsets**, graph colouring, Hamiltonian cycle, maze solving.



**Q. [PYQ] [NUMERICAL] What are the solutions for the sum of subset problem w[1:5] = {2,7,8,9,15}, sum required 17?**

- (a) 11100; 10101; 00110
- (b) **11100; 10001; 00110  <-- CORRECT**
- (c) 11000; 10001; 00110
- (d) 11100; 10101; 00111

> **Why:** Map each bit onto the weights and add. **11100** = 2+7+8 = 17; **10001** = 2+15 = 17; **00110** = 8+9 = 17. Check a rejected option: 10101 = 2+8+15 = 25, not 17. **Do not run the backtracking tree - just add up the selected weights.**



**Q. [EXPECTED] Which of the following uses a greedy strategy?**

- (a) Floyd-Warshall
- (b) 0/1 Knapsack
- (c) **Huffman coding  <-- CORRECT**
- (d) Longest common subsequence

> **Why:** Greedy algorithms: **Dijkstra, Prim, Kruskal, Huffman coding, fractional knapsack, activity selection, job sequencing**. Greedy makes one locally best choice and never reconsiders - fast, but only optimal for problems with the greedy-choice property.



**Q. [EXPECTED] The average-case time complexity of searching in a hash table is:**

- (a) O(n)
- (b) O(log n)
- (c) **O(1)  <-- CORRECT**
- (d) O(n log n)

> **Why:** Hashing computes the index directly. The **worst case is O(n)** if every key collides into one slot. Collision resolution: **separate chaining** (linked list per slot) or **open addressing** (linear probing, quadratic probing, double hashing).



**Q. [EXPECTED] [TRAP] Which collision resolution technique suffers from primary clustering?**

- (a) Separate chaining
- (b) **Linear probing  <-- CORRECT**
- (c) Double hashing
- (d) Quadratic probing

> **Why:** **Linear probing** checks index+1, index+2, ... so occupied slots coalesce into long runs, lengthening every subsequent probe. **Quadratic probing** reduces primary clustering; **double hashing** distributes best.

