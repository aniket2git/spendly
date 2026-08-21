
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
