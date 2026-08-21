
---

# PART 6 - Database Management Systems and SQL

> *Weightage: 5 to 8 marks in DSSSB, 5 to 10 expected. A compact, highly memorisable syllabus - among the most reliable marks available.*



## 6.1 DBMS Concepts, Keys and the ER Model



> **WEIGHTAGE: 2-4 marks | Schema/instance and key definitions are near-certain | Priority HIGH**



### 6.1.1 Topic checklist

- DBMS vs file system, advantages, data independence
- Three-schema architecture, schema vs instance, metadata
- Database models, relational model terminology, degree and cardinality
- All key types and integrity constraints
- ER model symbols, cardinality, descriptive attributes, generalisation


### 6.1.2 Questions



**Q. [PYQ] What is the overall design of a database called?**

- (a) **Database Schema  <-- CORRECT**
- (b) Database Instance
- (c) Database Table
- (d) Database Model

> **Why:** **Schema** = structure (defined once, rarely changes). **Instance** = the actual data at a moment (changes constantly). The analogy to hold: **schema is to instance as a class is to an object**, or as a variable's type is to its value.



**Q. [PYQ] What makes a database relational?**

- (a) **Tables  <-- CORRECT**
- (b) Field
- (c) Records
- (d) Tuple

> **Why:** The defining feature of the relational model (E. F. Codd, 1970) is organising all data into **tables (relations)**. Fields, records and tuples are merely the *parts* of a table - and "record" and "tuple" mean the same thing, so neither could be the distinguishing answer.



**Q. [EXPECTED] [TRAP] In relational terminology, degree and cardinality refer to:**

- (a) rows and columns respectively
- (b) **columns and rows respectively  <-- CORRECT**
- (c) keys and attributes
- (d) tables and views

> **Why:** **Degree = number of COLUMNS (attributes). Cardinality = number of ROWS (tuples).** Memory hook: "**D**egree for **D**escriptions - columns describe; **C**ardinality for **C**ount of records."



**Q. [EXPECTED] Which key can accept NULL values?**

- (a) Primary key
- (b) Candidate key
- (c) **Foreign key  <-- CORRECT**
- (d) Super key

> **Why:** A **primary key can never be NULL** (entity integrity). A **foreign key may be NULL**, meaning "no related row yet". A **candidate key** is a minimal super key, one of which is chosen as primary.



**Q. [EXPECTED] A minimal super key is called:**

- (a) Primary key
- (b) **Candidate key  <-- CORRECT**
- (c) Foreign key
- (d) Composite key

> **Why:** A **super key** is any uniquely identifying attribute set, possibly with redundant attributes. Remove the redundancy and you have a **candidate key**. The designer promotes one candidate key to **primary**; the rest become **alternate** keys.



**Q. [EXPECTED] Referential integrity is enforced by which constraint?**

- (a) Primary key
- (b) **Foreign key  <-- CORRECT**
- (c) NOT NULL
- (d) CHECK

> **Why:** A foreign key value must either match an existing primary key in the referenced table or be NULL. Related actions: **ON DELETE CASCADE / SET NULL / RESTRICT**.



**Q. [PYQ] Descriptive attributes are used to:**

- (a) **record the information about relationships  <-- CORRECT**
- (b) record the information about attributes
- (c) record the information about participating entities
- (d) record the information about data

> **Why:** A **descriptive attribute belongs to a RELATIONSHIP**, not to either entity. In "Student ENROLS IN Course", the *grade* and *date of enrolment* describe the enrolment itself, not the student or the course.



**Q. [EXPECTED] In an ER diagram, a weak entity is represented by:**

- (a) A single rectangle
- (b) **A double rectangle  <-- CORRECT**
- (c) A diamond
- (d) A double ellipse

> **Why:** **Double rectangle** = weak entity (no key of its own, only a partial key; identified through an owner entity via a **double diamond** identifying relationship). Single rectangle = entity, ellipse = attribute, **double ellipse = multivalued attribute**, dashed ellipse = derived attribute, diamond = relationship.



**Q. [EXPECTED] [TRAP] Generalisation in the ER model is:**

- (a) a top-down process splitting an entity into sub-entities
- (b) **a bottom-up process combining similar entities into a higher-level entity  <-- CORRECT**
- (c) the same as aggregation
- (d) used only for weak entities

> **Why:** **Generalisation is BOTTOM-UP** (Car and Truck become Vehicle). **Specialisation is TOP-DOWN** (Employee becomes Engineer, Manager, Clerk). **Aggregation** treats a whole relationship as one higher-level entity.



**Q. [EXPECTED] A many-to-many relationship, when converted to tables, requires:**

- (a) two tables only
- (b) **a separate junction/bridge table  <-- CORRECT**
- (c) a single merged table
- (d) no change

> **Why:** The junction table holds the primary keys of both participants as a composite key, plus any descriptive attributes of the relationship.



**Q. [EXPECTED] Logical data independence means:**

- (a) storage structure can change without affecting the logical schema
- (b) **the logical schema can change without affecting application programs  <-- CORRECT**
- (c) data can be stored in any format
- (d) indexes can be added freely

> **Why:** **Physical** independence: change *how* data is stored without touching the logical schema (easier to achieve). **Logical** independence: change the logical schema without rewriting applications - achieved largely through **views**.



## 6.2 Functional Dependencies and Normalisation



> **WEIGHTAGE: 1-3 marks | Normal-form definitions and Armstrong's axioms recur | Priority HIGH**



### 6.2.1 Questions



**Q. [PYQ] [TRAP] Which of the following DBMS scenarios will NOT really follow Armstrong's Axiom?**

- (a) Reflexivity rule
- (b) **Pseudo transitivity rule  <-- CORRECT**
- (c) Transitivity rule
- (d) Armstrong's axioms

> **Why:** Armstrong's axioms **proper** are exactly three: **Reflexivity, Augmentation, Transitivity**. Union, decomposition, **pseudo-transitivity** and composition are *derived* rules - they follow from the axioms but are not themselves axioms. Memorise the three-word list.



**Q. [PYQ] [NUMERICAL] Consider R(PQRSTU) with F = {P to RT, Q to S, R to PS, QS to TU}. Find the closure of PQ.**

- (a) PQRST
- (b) PQRTU
- (c) PQRSU
- (d) **PQRSTU  <-- CORRECT**

> **Why:** Start with {P, Q}. `P to RT` adds R and T. `Q to S` adds S. Now we hold Q and S, so `QS to TU` adds **U**. Result is all six attributes = **PQRSTU**, which means PQ is a superkey. **Method: loop through the FD list repeatedly until one full pass adds nothing new.**



**Q. [EXPECTED] A relation is in 1NF if:**

- (a) it has no transitive dependency
- (b) it has no partial dependency
- (c) **every attribute holds a single atomic value  <-- CORRECT**
- (d) every determinant is a super key

> **Why:** **1NF = atomic values** (no repeating groups or multi-valued cells). **2NF** removes **partial** dependencies; **3NF** removes **transitive** dependencies; **BCNF** requires every determinant to be a **super key**.



**Q. [EXPECTED] [TRAP] Removing partial dependency achieves which normal form?**

- (a) 1NF
- (b) **2NF  <-- CORRECT**
- (c) 3NF
- (d) BCNF

> **Why:** A partial dependency exists when a non-key attribute depends on only **part of a composite** primary key - so 2NF is only an issue when the key is composite. Hook: "**One is Atomic, Two is Partial, Three is Transitive, BC is Super.**"



**Q. [EXPECTED] A relation in 3NF where every determinant is a super key is in:**

- (a) 2NF
- (b) **BCNF  <-- CORRECT**
- (c) 4NF
- (d) 5NF

> **Why:** BCNF is **stricter than 3NF** and handles anomalies arising from overlapping candidate keys. Important caveat: **BCNF decomposition may fail to preserve dependencies**, whereas a lossless *and* dependency-preserving 3NF decomposition always exists.



**Q. [EXPECTED] The purpose of normalisation is primarily to:**

- (a) speed up queries
- (b) **reduce redundancy and eliminate update, insert and delete anomalies  <-- CORRECT**
- (c) reduce the number of tables
- (d) improve security

> **Why:** Normalisation usually **increases** the number of tables and can slow reads by requiring joins. That is why data warehouses deliberately **denormalise** (star schema) for query speed.



## 6.3 SQL



> **WEIGHTAGE: 2-4 marks | Command classification and NULL logic are recurring | Priority HIGH**



### 6.3.1 Questions



**Q. [PYQ] Which of the following is used to define the structure of a relation as well as delete relations and relate schemas?**

- (a) Integrity constraint
- (b) View
- (c) DML (Data Manipulation Language)
- (d) **DDL (Data Definition Language)  <-- CORRECT**

> **Why:** Every verb in the question - define the structure, delete relations, relate schemas - is **structural**, which is DDL's domain (CREATE, ALTER, DROP, TRUNCATE). DML only touches the rows inside an existing structure.



**Q. [PYQ] Which SQL statement is used to update data in a table?**

- (a) CHANGE
- (b) MODIFY
- (c) **UPDATE  <-- CORRECT**
- (d) SET

> **Why:** `CHANGE` and `MODIFY` are clauses used **inside ALTER TABLE** to rename or retype a column; `SET` is a clause **inside UPDATE**. Only **UPDATE** is a standalone data-modification statement.



**Q. [EXPECTED] [TRAP] Which of the following is a DDL command that cannot normally be rolled back?**

- (a) DELETE
- (b) **TRUNCATE  <-- CORRECT**
- (c) UPDATE
- (d) INSERT

> **Why:** **TRUNCATE** is DDL, removes all rows, takes no WHERE clause, is very fast and is normally not rollback-able. **DELETE** is DML, accepts WHERE, logs each row and **can** be rolled back. **DROP** removes the table structure entirely.



**Q. [PYQ] Select the correct SQL statement to insert a new row into Customer specifying only CustomerID, Name and Product (other columns allow NULL).**

- (a) INSERT Customer SET CustomerID=101, Name='Alice', Product='Pen';
- (b) INSERT INTO Customer VALUES (101, 'Alice', 'Pen');
- (c) INSERT INTO Customer (101, 'Alice', 'Pen');
- (d) **INSERT INTO Customer (CustomerID, Name, Product) VALUES (101, 'Alice', 'Pen');  <-- CORRECT**

> **Why:** **To insert into a subset of columns you must name the columns AND use VALUES.** The bare `VALUES` form supplies values for *all* columns in order and would fail here. The `SET` form is MySQL-specific, and the third option omits `VALUES` entirely.



**Q. [PYQ] [TRAP] Which of the following SQL expressions evaluates to TRUE, according to SQL-99?**

- (a) NULL <= NULL returns UNKNOWN
- (b) NULL >= NULL returns UNKNOWN
- (c) NULL IS NULL returns FALSE
- (d) **NULL IS NULL returns TRUE  <-- CORRECT**

> **Why:** Read the question precisely - it asks which **expression evaluates to TRUE**. The first two statements are *factually accurate* but the expressions themselves evaluate to UNKNOWN, not TRUE. **Golden rule: never test NULL with = or <>; use IS NULL / IS NOT NULL.**



**Q. [EXPECTED] [TRAP] What does COUNT(*) do differently from COUNT(column)?**

- (a) They are identical
- (b) **COUNT(*) counts all rows including NULLs; COUNT(column) ignores NULLs  <-- CORRECT**
- (c) COUNT(*) is slower always
- (d) COUNT(column) counts distinct values

> **Why:** All aggregate functions except `COUNT(*)` **ignore NULLs**. This is why `AVG(col)` is not the same as `SUM(col)/COUNT(*)` when NULLs are present.



**Q. [EXPECTED] [TRAP] Which clause filters groups after aggregation?**

- (a) WHERE
- (b) **HAVING  <-- CORRECT**
- (c) GROUP BY
- (d) ORDER BY

> **Why:** **WHERE filters individual rows BEFORE grouping** and cannot contain aggregate functions. **HAVING filters groups AFTER aggregation** and can. Execution order: FROM, WHERE, GROUP BY, HAVING, SELECT, ORDER BY.



**Q. [EXPECTED] Which join returns all rows from the left table plus matching rows from the right?**

- (a) INNER JOIN
- (b) **LEFT OUTER JOIN  <-- CORRECT**
- (c) RIGHT OUTER JOIN
- (d) CROSS JOIN

> **Why:** Unmatched right-side columns come back as NULL. **INNER JOIN** returns only matches; **FULL OUTER** returns everything from both; **CROSS JOIN** is the Cartesian product.



**Q. [PYQ] [TRAP] __________ is NOT allowed in a SQL:1999 view definition.**

- (a) Use of subqueries
- (b) Use of nested queries
- (c) Use of aggregate formulas
- (d) **Use of ORDER BY clause  <-- CORRECT**

> **Why:** A view is defined to be a **relation**, and a relation is an **unordered set of tuples** - so ordering has no meaning in the definition. Apply ORDER BY when you SELECT *from* the view. Subqueries and aggregates are legal (they merely make the view read-only).



**Q. [EXPECTED] A view is best described as:**

- (a) a physical copy of a table
- (b) **a virtual table produced by a stored query  <-- CORRECT**
- (c) an index
- (d) a backup

> **Why:** A standard view stores **no data** - rows are generated when queried. A **materialised view** does store results physically and must be refreshed, trading freshness for speed.



**Q. [EXPECTED] Which of the following is NOT a benefit of using views?**

- (a) Security by hiding columns
- (b) Simplifying complex joins
- (c) Logical data independence
- (d) **Faster write performance on the base tables  <-- CORRECT**

> **Why:** Views do nothing for write speed and can complicate updates. Their genuine benefits are security, simplification and logical independence.



**Q. [EXPECTED] [TRAP] How many clustered indexes can a table have?**

- (a) Unlimited
- (b) **One  <-- CORRECT**
- (c) Two
- (d) None

> **Why:** A **clustered index determines the physical row order**, so there can be only **one** per table (usually on the primary key). **Non-clustered** indexes are separate structures and many are permitted.



## 6.4 Transactions and Concurrency Control



> **WEIGHTAGE: 1-3 marks | ACID and serialisability appear regularly | Priority HIGH**



### 6.4.1 Questions



**Q. [EXPECTED] Which ACID property guarantees that a transaction is all-or-nothing?**

- (a) Consistency
- (b) **Atomicity  <-- CORRECT**
- (c) Isolation
- (d) Durability

> **Why:** **Atomicity** = all operations complete or none do (partial work is rolled back). **Consistency** = valid state to valid state. **Isolation** = concurrent transactions do not interfere. **Durability** = committed changes survive a crash.



**Q. [EXPECTED] Which ACID property is ensured by write-ahead logging?**

- (a) Atomicity
- (b) Consistency
- (c) Isolation
- (d) **Durability  <-- CORRECT**

> **Why:** The log record is forced to stable storage **before** the data change, so committed work can always be reconstructed after a crash. WAL supports both durability and atomicity (via UNDO).



**Q. [EXPECTED] [TRAP] Reading a value written by an uncommitted transaction is called:**

- (a) Lost update
- (b) **Dirty read  <-- CORRECT**
- (c) Unrepeatable read
- (d) Phantom read

> **Why:** **Dirty read** - if the writer later rolls back, the reader has used data that never officially existed. **Unrepeatable read**: same row read twice gives different values. **Phantom read**: a range query returns extra rows the second time. **Lost update**: one transaction's write overwrites another's.



**Q. [EXPECTED] Two operations conflict if they belong to different transactions, access the same data item, and:**

- (a) both are reads
- (b) **at least one is a write  <-- CORRECT**
- (c) both are writes
- (d) they occur simultaneously

> **Why:** **Read-read never conflicts.** Only read-write, write-read and write-write pairs do. This definition is the foundation of conflict serialisability.



**Q. [PYQ] [NUMERICAL] Which of the following is a conflict serializable schedule? S1: R1(A); R1(B); R2(A); R2(B); W2(B); W1(A) and S2: R1(A); R2(A); R2(B); W2(B); R1(B); W1(A)**

- (a) S1 is conflict serializable but S2 is not.
- (b) **S1 is not conflict serializable but S2 is conflict serializable.  <-- CORRECT**
- (c) Both are not conflict serializable.
- (d) Both are conflict serializable.

> **Why:** Build the **precedence graph**. In **S1**: on item A, R2(A) precedes W1(A) giving edge T2 to T1; on item B, R1(B) precedes W2(B) giving edge T1 to T2 - both directions exist, so there is a **cycle** and S1 fails. In **S2**: R2(A) before W1(A) gives T2 to T1, and W2(B) before R1(B) also gives T2 to T1 - all edges point one way, **no cycle**, so S2 is conflict serialisable (equivalent to running T2 then T1). **A schedule is conflict serialisable if and only if its precedence graph is acyclic.**



**Q. [EXPECTED] In two-phase locking, once a transaction releases its first lock it:**

- (a) may acquire more locks
- (b) **may not acquire any new locks  <-- CORRECT**
- (c) must commit immediately
- (d) must abort

> **Why:** 2PL has a **growing phase** (acquire only) and a **shrinking phase** (release only). This guarantees serialisability but can still deadlock. **Conservative (static) 2PL** acquires all locks upfront and is **deadlock free**.



**Q. [EXPECTED] [TRAP] Which lock type allows several transactions to read the same item concurrently?**

- (a) Exclusive lock
- (b) **Shared lock  <-- CORRECT**
- (c) Update lock
- (d) Binary lock

> **Why:** Multiple **shared (S)** locks can coexist for reading. An **exclusive (X)** lock permits no other lock of any kind - required for writing.



**Q. [EXPECTED] Which concurrency control method never causes deadlock?**

- (a) Two-phase locking
- (b) Strict 2PL
- (c) **Timestamp ordering  <-- CORRECT**
- (d) Rigorous 2PL

> **Why:** **Timestamp ordering** resolves conflicts by comparing timestamps and aborting offenders rather than making them wait, so no waiting cycle can form. Conservative 2PL is also deadlock free (it avoids hold-and-wait).



**Q. [EXPECTED] [TRAP] What is the difference between OLTP and OLAP?**

- (a) OLTP is for analysis, OLAP for transactions
- (b) **OLTP handles many short read/write transactions; OLAP handles few complex read-only analytical queries  <-- CORRECT**
- (c) Both are identical
- (d) OLAP is highly normalised

> **Why:** **OLTP** = day-to-day operations, highly normalised, current detailed data (booking a ticket). **OLAP** = decision support, **denormalised** star/snowflake schema, historical summarised data ("compare quarterly sales by region over five years").



**Q. [EXPECTED] A data warehouse is characterised as subject-oriented, integrated, time-variant and:**

- (a) volatile
- (b) **non-volatile  <-- CORRECT**
- (c) normalised
- (d) transactional

> **Why:** Bill Inmon's four adjectives: **subject-oriented, integrated, time-variant, non-volatile**. Non-volatile means data is loaded and read but not updated in place.



**Q. [EXPECTED] The 5 Vs of Big Data are Volume, Velocity, Variety, Veracity and:**

- (a) Validity
- (b) Visibility
- (c) **Value  <-- CORRECT**
- (d) Version

> **Why:** **Value** - data is worthless unless insight can be extracted from it. Related: **ETL** (Extract, Transform, Load) moves data into the warehouse; **fact tables** hold measures and **dimension tables** hold context.

