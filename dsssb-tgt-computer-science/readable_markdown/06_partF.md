
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
