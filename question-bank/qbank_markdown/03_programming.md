
---

# PART 4 - Programming: C, C++, OOP and Java

> *Weightage: 9 to 15 marks in DSSSB, 8 to 16 expected. Output-tracing questions dominate. This is the one topic you cannot cram - practise daily.*



## 4.1 C Language - Basics, Operators and Control Flow



> **WEIGHTAGE: 4-7 marks | "What is the output" questions are guaranteed | Priority CRITICAL**



### 4.1.1 Topic checklist

- Data types and sizes, format specifiers, header files
- Operators and full precedence table, associativity
- if/else, switch rules, all three loops, break/continue/goto
- Functions, call by value vs reference, actual vs formal parameters
- Storage classes and their default values
- Arrays, strings, pointers, structures, unions, file handling


### 4.1.2 Questions



**Q. [PYQ] scanf() is a predefined function in which of the following header files?**

- (a) ctype.h
- (b) **stdio.h  <-- CORRECT**
- (c) unistd.h
- (d) string.h

> **Why:** Both `printf` and `scanf` are declared in **stdio.h**. Other essentials: **stdlib.h** (malloc, free, exit, atoi), **string.h** (strlen, strcpy, strcmp), **math.h** (sqrt, pow), **stdarg.h** (va_list for variable arguments).



**Q. [PYQ] Which arithmetic operator has the highest precedence in C?**

- (a) -
- (b) =
- (c) +
- (d) **%  <-- CORRECT**

> **Why:** The group **`* / %`** sits above `+ -`. All three of `*`, `/`, `%` share the same level, so if `*` were offered it would be equally valid. `=` has almost the lowest precedence of all operators.



**Q. [EXPECTED] Which operators in C are right-to-left associative?**

- (a) Arithmetic operators
- (b) Relational operators
- (c) **Unary, ternary and assignment operators  <-- CORRECT**
- (d) Bitwise operators

> **Why:** Only three groups associate right-to-left: **unary** (`!`, `~`, `++`, `--`, `sizeof`, type casts), the **ternary** `?:`, and **assignment** (`=`, `+=`). Everything else is left-to-right - which is exactly what makes `a > b > c` evaluate as `((a>b)>c)`.



**Q. [PYQ] [TRAP] Output of: `int a = 5, b = 3, c = 0; if (a > b > c) printf("True"); else printf("False");`**

- (a) compile time error
- (b) undefined behavior
- (c) **TRUE  <-- CORRECT**
- (d) FALSE

> **Why:** Relational operators are **left-to-right**, so this is `((a>b)>c)`. Step 1: `5 > 3` gives **1**. Step 2: `1 > 0` gives **1**, which is true. Prints **True**. Never read chained comparisons as mathematics.



**Q. [PYQ] [TRAP] Output of: `int x = -1, y = 0, z = 1; int result = (x > 0) ? x : (y == 0) ? z : y;`**

- (a) compile time error
- (b) -1
- (c) **1  <-- CORRECT**
- (d) 0

> **Why:** `?:` is **right-associative**, so it reads `(x>0) ? x : ((y==0) ? z : y)`. `x > 0` is false, so evaluate the inner ternary: `y == 0` is true, giving **z = 1**.



**Q. [EXPECTED] Output of: `int a = 10, b = 20; int max = (a > b) ? a : b; printf("%d", max);`**

- (a) 30
- (b) compile time error
- (c) 10
- (d) **20  <-- CORRECT**

> **Why:** `10 > 20` is false, so `b` is selected. The ternary is shorthand for a complete if-else expression.



**Q. [PYQ] [TRAP] Output of: `int i = 5; do { printf("%d ", i); i--; } while (i > 5);`**

- (a) No output printed
- (b) Infinite loop
- (c) 5 4 3 2 1
- (d) **5  <-- CORRECT**

> **Why:** A **do-while executes its body at least once** before testing. It prints 5, decrements to 4, then tests `4 > 5` which is false and exits. This is the single most-asked loop trap.



**Q. [PYQ] Which of the following causes an infinite loop?**

- (a) for (int i = 10; i > 5; i--) { }
- (b) do { } while (0);
- (c) **while (1) { }  <-- CORRECT**
- (d) for (int i = 0; i < 10; i++) { }

> **Why:** `while(1)` never terminates. The others run 5 times, exactly once, and 10 times respectively. Other infinite forms: `for(;;){}` and `do{}while(1);`.



**Q. [PYQ] Which of the following is true about the for loop in C?**

- (a) A for loop cannot be nested inside another for loop.
- (b) **The condition in a for loop is optional, and it can result in an infinite loop if omitted.  <-- CORRECT**
- (c) A for loop must always have all three components.
- (d) The increment/decrement part of the for loop is mandatory.

> **Why:** **All three parts of a for loop are optional** - `for(;;)` is perfectly legal. Nesting is also allowed, so the first option is false too.



**Q. [PYQ] [NUMERICAL] How many times will the innermost loop execute? `for(i=0;i<3;i++) for(j=0;j<2;j++) printf(...)`**

- (a) **6 times  <-- CORRECT**
- (b) 3 times
- (c) 5 times
- (d) 2 times

> **Why:** Multiply the iteration counts: 3 x 2 = **6**. Printed output would be `0 0 1 1 2 2`.



**Q. [PYQ] Which of the following will terminate the loop immediately in C?**

- (a) **When a break statement is encountered  <-- CORRECT**
- (b) When the loop variable reaches a certain value
- (c) When a continue statement is encountered
- (d) When the loop condition is not given

> **Why:** `break` exits the innermost loop or switch at once. `continue` only skips the remainder of the current iteration and jumps to the next test.



**Q. [PYQ] Which of the following is true about nested switch statements in C?**

- (a) Both inner and outer switch statements must have a default case.
- (b) A switch statement cannot contain another switch.
- (c) Inner switch cases should not contain break statement
- (d) **A switch statement can contain another switch statement inside any of its cases.  <-- CORRECT**

> **Why:** Nesting is allowed and each switch is independent - an inner `break` exits only the inner switch. `default` is always optional.



**Q. [EXPECTED] [TRAP] Which data type is NOT allowed in a switch expression?**

- (a) int
- (b) char
- (c) short
- (d) **float  <-- CORRECT**

> **Why:** A switch expression must be an **integral** type (int, char, short, long, enum). **Floating-point values and strings are illegal** because case labels must be exact constant integers.



**Q. [EXPECTED] What happens if `break` is omitted from a case in a switch?**

- (a) Compilation error
- (b) The switch exits
- (c) **Execution falls through into the next case  <-- CORRECT**
- (d) The default case runs

> **Why:** **Fall-through** is deliberate C behaviour, sometimes used intentionally to let several cases share code.



**Q. [PYQ] [NUMERICAL] Output of: `int a = 4; int b = 3; result = a ^ b; printf("%d", result);`**

- (a) 0
- (b) 3
- (c) 4
- (d) **7  <-- CORRECT**

> **Why:** `^` is **bitwise XOR**, not exponentiation. 4 = 100, 3 = 011; XOR gives 111 = **7**. (For powers you need `pow()` from math.h.)



**Q. [EXPECTED] [NUMERICAL] What is the value of `x` after `int x = 5; x = x << 2;`?**

- (a) 10
- (b) **20  <-- CORRECT**
- (c) 25
- (d) 7

> **Why:** Left shift by n multiplies by 2^n: 5 x 4 = **20**. Right shift divides. Compilers use shifts because they are far cheaper than multiplication.



**Q. [PYQ] [NUMERICAL] Given `int a, b, c; a = b = c = 15; c = c + 10;` what is the value of c?**

- (a) Undefined
- (b) 10
- (c) **25  <-- CORRECT**
- (d) 15

> **Why:** Assignment is **right-to-left**, so c, b and a all become 15; then `c = 15 + 10 = 25`.



**Q. [PYQ] [TRAP] Output of nested blocks: outer `int x=10, y=20;` inner block declares `int y = 40;` then does `x++; y++;` and after the inner block ends we print x and y.**

- (a) x = 11, y = 41
- (b) x = 10, y = 41
- (c) x = 10, y = 20
- (d) **x = 11, y = 20  <-- CORRECT**

> **Why:** The inner `y` is a **new variable that shadows** the outer one and dies when the block ends, so the outer y is untouched at 20. `x` has no inner declaration, so `x++` modifies the outer x, giving 11.



**Q. [PYQ] [NUMERICAL] Output of: `int a[5]; for(i=0;i<5;i++) a[i] = i*i - 2*i + 1;` then printing the array.**

- (a) 1 0 2 4 9
- (b) **1 0 1 4 9  <-- CORRECT**
- (c) 1 1 2 4 9
- (d) 1 2 3 4 9

> **Why:** Recognise the identity: `i*i - 2i + 1 = (i-1)^2`. For i = 0..4 that gives 1, 0, 1, 4, **9**. Spotting the algebraic form is faster and less error-prone than substituting each value.



**Q. [PYQ] [NUMERICAL] Output of: `char buffer[50]; int n = sprintf(buffer, "Hello, World!"); printf("%d %s", n, buffer);`**

- (a) Prints '13 Hello'
- (b) Prints '12 Hello'
- (c) Prints '12 Hello, World!'
- (d) **Prints '13 Hello, World!'  <-- CORRECT**

> **Why:** `sprintf` writes formatted text **into the buffer** (it prints nothing itself) and **returns the character count excluding the terminating '\0'**. "Hello, World!" has 13 characters including the comma and space.



**Q. [PYQ] Which of the following techniques can be used to modify the actual variable passed to a function?**

- (a) Use a local variable instead of passing any parameters.
- (b) Pass a copy of the actual parameter to function.
- (c) Standard C has no options for modifying actual variables passed to a function.
- (d) **Pass the address of the actual parameters to function.  <-- CORRECT**

> **Why:** C is call-by-value by default, so a copy cannot affect the original. Passing the **address** (a pointer) lets the function write through to the caller's variable.



**Q. [PYQ] Which of the following options is correct about the functions in C language?**

- (a) Actual parameters are declared in the function definition.
- (b) Actual parameters are always variables.
- (c) Actual parameters are used to define the function signature.
- (d) **Actual parameters are the values that are passed to a function when it is called.  <-- CORRECT**

> **Why:** **Actual parameters** are the values supplied at the call site (and may be literals or expressions, e.g. `add(3, x+2)`). **Formal parameters** are the variables declared in the definition that receive them.



**Q. [PYQ] [TRAP] Which of the following statements is INCORRECT about the storage classes in C?**

- (a) The scope of a variable in automatic storage class is local to the block in which it is defined.
- (b) **In Register storage class, the default initial value of the variable is zero.  <-- CORRECT**
- (c) In static storage class, the default initial value of the variable is zero.
- (d) In Register storage class, the storage of a variable is CPU register.

> **Why:** `register` variables, like `auto`, start with **garbage**. Only **static** and **extern** are guaranteed to be zero-initialised. Also note you cannot take the address of a register variable with `&`.



**Q. [EXPECTED] A static local variable inside a function:**

- (a) is destroyed when the function returns
- (b) **retains its value between function calls  <-- CORRECT**
- (c) is visible to other files
- (d) is stored on the stack

> **Why:** `static` gives the variable **program lifetime** but keeps its **block scope**. It lives in the data segment, initialised to 0, and is why returning a pointer to a static array is safe.



**Q. [PYQ] [TRAP] [NUMERICAL] A function returns a pointer to a `static int arr[5] = {1,2,3,4,5};` and main loops five times printing `*ptr` without ever incrementing ptr. Output?**

- (a) 1 1 3 4 1
- (b) 2 3 4 5 0
- (c) 1 2 3 4 5
- (d) **1 1 1 1 1  <-- CORRECT**

> **Why:** `ptr` is **never advanced**, so `*ptr` dereferences the first element every time; the loop variable only counts. To print all five you would need `*(ptr+i)` or `ptr++`. Note `static` is what makes returning the array's address legal.



**Q. [PYQ] Which of the following is NOT a correct way of declaring and initializing array in C?**

- (a) char arr[6] = {2};
- (b) char arr[ ] = "consultancy";
- (c) **char arr[6]; arr = "consultancy";  <-- CORRECT**
- (d) char arr[6] = { };

> **Why:** An **array name is not a modifiable lvalue**, so it cannot be assigned after declaration - you must use `strcpy`. Independently, "consultancy" needs 12 bytes and `arr` has only 6.



**Q. [PYQ] What do the first and second dimensions represent in a two-dimensional character array?**

- (a) The first stores the length of each name, the second the number of names.
- (b) **The first represents the number of names, and the second the maximum length of each name.  <-- CORRECT**
- (c) The first is the maximum length, the second the number of names.
- (d) The first holds the total characters, the second the number of names.

> **Why:** `char names[5][20]` = **5 names, each up to 20 characters**. Think "how many, then how long".



**Q. [EXPECTED] [NUMERICAL] How many bytes does the string "HELLO" occupy in C?**

- (a) 5
- (b) **6  <-- CORRECT**
- (c) 7
- (d) 10

> **Why:** A C string is terminated by the null character `'\0'`, so 5 characters need **6 bytes**. `strlen("HELLO")` returns 5, but `sizeof("HELLO")` returns 6 - a favourite distinction.



**Q. [EXPECTED] [TRAP] Which is the correct way to compare two strings in C?**

- (a) if (s1 == s2)
- (b) **if (strcmp(s1, s2) == 0)  <-- CORRECT**
- (c) if (s1.equals(s2))
- (d) if (s1 = s2)

> **Why:** `==` on char arrays compares **addresses**, not contents. `strcmp` returns **0 when equal**, negative if s1 < s2 and positive if s1 > s2. (`.equals()` is Java, not C.)



**Q. [EXPECTED] `p+1` on a pointer `int *p` advances the address by:**

- (a) 1 byte
- (b) 2 bytes
- (c) **sizeof(int) bytes  <-- CORRECT**
- (d) 8 bytes

> **Why:** Pointer arithmetic is scaled by the **pointed-to type's size**, which is why `a[i]` is exactly equivalent to `*(a + i)`.



**Q. [EXPECTED] [TRAP] Which function allocates memory and initialises it to zero?**

- (a) malloc()
- (b) **calloc()  <-- CORRECT**
- (c) realloc()
- (d) free()

> **Why:** **calloc(count, size)** zeroes the memory; **malloc(n)** leaves it with garbage. `realloc` resizes; `free` releases. Forgetting `free` causes a **memory leak**.



**Q. [EXPECTED] [TRAP] What is the difference between a structure and a union?**

- (a) They are identical
- (b) **In a structure each member has its own memory; in a union all members share the same memory  <-- CORRECT**
- (c) A union can hold more members
- (d) Structures cannot be nested

> **Why:** Structure size = sum of members (plus padding); **union size = size of the largest member**, and only one member is valid at a time. Unions save memory when only one field is needed.



**Q. [EXPECTED] Which file mode erases the existing contents of a file?**

- (a) "r"
- (b) **"w"  <-- CORRECT**
- (c) "a"
- (d) "r+"

> **Why:** `"w"` truncates or creates. `"a"` appends without destroying. `"r"` requires the file to exist and cannot write.



## 4.2 C++ and Object Oriented Programming



> **WEIGHTAGE: 2-4 marks | OOP pillar definitions are near-certain | Priority CRITICAL**



### 4.2.1 Questions



**Q. [PYQ] What is the objective of encapsulation in object-oriented programming?**

- (a) To create multiple instances of a class
- (b) To enable one class to inherit from another class
- (c) To allow objects to take multiple forms
- (d) **To combine data and methods that operate on that data within a single unit  <-- CORRECT**

> **Why:** The distractors each define a *different* concept - instantiation, inheritance and polymorphism. Learn one crisp phrase per pillar so you can tell them apart instantly.



**Q. [EXPECTED] [TRAP] Which OOP concept hides complexity and shows only essential features?**

- (a) Encapsulation
- (b) **Abstraction  <-- CORRECT**
- (c) Inheritance
- (d) Polymorphism

> **Why:** **Abstraction hides COMPLEXITY** (design level - "what it does"); **encapsulation hides DATA** (implementation level - "how it is stored"). A car's steering wheel is abstraction; the sealed engine block is encapsulation.



**Q. [PYQ] [TRAP] What feature of OOP allows an instance of a class to take on many forms?**

- (a) Operator overriding
- (b) Multiple inheritance
- (c) Nested class
- (d) **Operator overloading  <-- CORRECT**

> **Why:** The concept is **polymorphism**; since that word was not offered, the mechanism implementing it is **operator overloading**. Note that "operator overriding" is not a real term - operators are *overloaded*, methods are *overridden*.



**Q. [EXPECTED] [TRAP] Function overloading is resolved at:**

- (a) run time
- (b) **compile time  <-- CORRECT**
- (c) link time
- (d) load time

> **Why:** **Overloading** = same name, different parameter lists = **compile-time (static / early) binding**. **Overriding** = same signature in a subclass = **run-time (dynamic / late) binding**, achieved through virtual functions.



**Q. [EXPECTED] A class that cannot be instantiated is called:**

- (a) Final class
- (b) Static class
- (c) **Abstract class  <-- CORRECT**
- (d) Nested class

> **Why:** In C++ a class containing a **pure virtual function** (`virtual void f() = 0;`) becomes abstract. It exists only to be inherited from and may still contain concrete methods.



**Q. [EXPECTED] Which of the following is NOT supported for classes in Java but is supported in C++?**

- (a) Single inheritance
- (b) Encapsulation
- (c) **Multiple inheritance  <-- CORRECT**
- (d) Polymorphism

> **Why:** Java forbids multiple inheritance of **classes** to avoid the **Diamond Problem** ambiguity, providing **interfaces** instead. C++ allows it directly. Java also has no operator overloading.



**Q. [EXPECTED] A constructor differs from an ordinary method in that it:**

- (a) can be called explicitly any number of times
- (b) **has the same name as the class and no return type  <-- CORRECT**
- (c) must return void
- (d) cannot be overloaded

> **Why:** Constructors run automatically at object creation, share the class name, and have **no return type at all** (not even void). They **can** be overloaded. Destructors, by contrast, cannot be overloaded.



**Q. [PYQ] What does the code snippet `myObject.doActivity();` represent?**

- (a) **Calling a method named doActivity on the object myObject  <-- CORRECT**
- (b) Sending a message to the doActivity class
- (c) Creating an object myObject
- (d) Sending a message to the child class of myObject

> **Why:** `doActivity` is a **method**, not a class, and object creation requires `new`. This is the standard OOP notion of **message passing** to an object.



**Q. [EXPECTED] [TRAP] Which relationship describes "a Car HAS-A Engine"?**

- (a) Inheritance
- (b) **Composition / Aggregation  <-- CORRECT**
- (c) Polymorphism
- (d) Abstraction

> **Why:** **HAS-A = composition/aggregation**; **IS-A = inheritance**. Composition is a strong part-of relation (destroy the house and the rooms go too); aggregation is weaker (a department has professors who exist independently).



**Q. [PYQ] In C++ language, the instruction `ignore(x,y);` ________.**

- (a) skips the last x characters and stops if character y is encountered
- (b) skips the first y characters and stops if character x is encountered
- (c) **skips the first x characters and stops if character y is encountered  <-- CORRECT**
- (d) skips the last y characters and stops if character x is encountered

> **Why:** `cin.ignore(count, delimiter)` discards characters until it has removed **count** of them or has consumed the **delimiter**, whichever comes first. Its everyday use is `cin.ignore(1000, '\n')` to clear a leftover newline before `getline()`.



**Q. [EXPECTED] Which C++ feature allows a non-member function to access private members of a class?**

- (a) Inline function
- (b) Virtual function
- (c) **Friend function  <-- CORRECT**
- (d) Static function

> **Why:** A `friend` declaration grants specific external functions or classes access to private and protected members. It deliberately breaks encapsulation, so it should be used sparingly.



## 4.3 Java



> **WEIGHTAGE: 3-5 marks | Exception handling and access modifiers recur | Priority CRITICAL**



### 4.3.1 Questions



**Q. [EXPECTED] [TRAP] Java achieves platform independence through:**

- (a) Machine code
- (b) **Bytecode executed by the JVM  <-- CORRECT**
- (c) Assembly language
- (d) Direct hardware compilation

> **Why:** `javac` produces **bytecode** (a .class file), and any platform's **JVM** runs that same bytecode - "Write Once, Run Anywhere". **JDK** = development kit (includes compiler), **JRE** = runtime only, **JVM** = the executing engine.



**Q. [PYQ] ________ does NOT have any child ClassLoaders.**

- (a) BootStrap ClassLoader
- (b) Extension ClassLoader
- (c) Primordial ClassLoader
- (d) **System ClassLoader  <-- CORRECT**

> **Why:** The delegation hierarchy is **Bootstrap to Extension to System**, so the **System (Application) ClassLoader** sits at the bottom with nothing beneath it. Note the trap: "Primordial" is just another name for Bootstrap, which *does* have a child.



**Q. [PYQ] What does the super keyword in Java do?**

- (a) Refers to high performing objects
- (b) Refers to the current object
- (c) Used to define static variables
- (d) **Refers to the parent class  <-- CORRECT**

> **Why:** `super` accesses the **parent** class (`super.method()`, `super()` for the parent constructor); `this` refers to the **current object**. Do not swap them.



**Q. [PYQ] [TRAP] Which of the following statements is FALSE?**

- (a) **Final methods can be overridden.  <-- CORRECT**
- (b) "static public void main(String...abcd){}" is a valid statement.
- (c) Abstract classes cannot be instantiated.
- (d) Interface allows default method definitions.

> **Why:** A **final method is by definition one that cannot be overridden**. The others are all true: modifier order is free and varargs `String...` is legal for main; abstract classes cannot be instantiated; and since **Java 8** interfaces may contain `default` methods with bodies.



**Q. [EXPECTED] Applying `final` to a class means:**

- (a) its methods cannot be called
- (b) **it cannot be inherited from  <-- CORRECT**
- (c) its variables become static
- (d) it cannot be instantiated

> **Why:** **final class** = no subclass (e.g. `String`). **final method** = cannot be overridden. **final variable** = a constant. A class that cannot be *instantiated* is `abstract`, not final.



**Q. [PYQ] Which access modifier can be used to access members in a deriving class?**

- (a) Void
- (b) **Protected  <-- CORRECT**
- (c) Private
- (d) Public

> **Why:** `protected` is designed precisely for inheritance - visible in the same package **and** in subclasses in other packages. `private` blocks subclasses entirely, and `void` is a return type, not an access modifier.



**Q. [PYQ] Identify the descending order of strict access protection.**

- (a) Public, protected, private, package
- (b) **Private, protected, package, public  <-- CORRECT**
- (c) Public, private, protected, package
- (d) Private, package, protected, public

> **Why:** Look for the option beginning with **Private** and ending with **public**. Strictly, Java's order is private > default(package) > protected > public, because `protected` additionally admits subclasses in other packages - but this paper's key placed protected before package, so use the start/end test.



**Q. [PYQ] A Parent class has a `protected void protectedMethod()`; `Child extends Parent` and calls it from a public method; main creates a Child and calls that method. What happens?**

- (a) **The code will compile and print the message.  <-- CORRECT**
- (b) Compilation Error: protectedMethod is not visible in the Child class.
- (c) Compilation Error: childMethod is not visible due to access restrictions.
- (d) Runtime Error: Cannot access protectedMethod from the Child class.

> **Why:** A protected member is **fully accessible inside a subclass**, and `childMethod` is public so `main` may call it. Nothing here violates any access rule.



**Q. [PYQ] Select the true statement about try-catch blocks.**

- (a) A try block must have at least 1 catch to have a finally block.
- (b) A try block must have only 1 finally block for each catch block.
- (c) **A try block can have many catches but only 1 finally block.  <-- CORRECT**
- (d) A try block can have many catches and many finally blocks.

> **Why:** Many `catch` blocks, exactly **one** `finally`. A try may also have `finally` with **no** catch at all. Catch blocks must be ordered most-specific first, or the code will not compile.



**Q. [EXPECTED] [TRAP] When does a finally block NOT execute?**

- (a) When an exception is thrown
- (b) When the try block returns a value
- (c) When no exception occurs
- (d) **Practically never - only if the JVM exits via System.exit() or crashes  <-- CORRECT**

> **Why:** `finally` runs even when the try block executes `return` or throws. That reliability is why it is used for closing files and connections.



**Q. [PYQ] An `ExceptionTest` calls `calculate(10, 0)`. The inner catch catches ArithmeticException and throws `new Exception("Division by zero not allowed")`; both levels have finally blocks. Output?**

- (a) Inner finally block executed. General exception caught: / by zero In finally block.
- (b) **Inner finally executed / General exception caught: Division by zero not allowed / In finally block.  <-- CORRECT**
- (c) Inner finally executed. Result: 0 In finally block.
- (d) Inner finally executed. ArithmeticException caught: / by zero In finally block.

> **Why:** Two rules combine. (1) The **inner finally runs before control leaves** the method, even though an exception is propagating. (2) The re-thrown object's type is now plain **Exception**, so the `catch (ArithmeticException)` block does **not** match and the general `catch (Exception)` does - carrying the **new** message, not "/ by zero".



**Q. [PYQ] A `CustomException extends Exception`; `validateAge(15)` throws it because 15 < 18; main catches it and has a finally block. Output?**

- (a) Caught Exception: null / Execution finished.
- (b) Compilation error because custom exceptions cannot extend Exception.
- (c) Age is valid. / Execution finished.
- (d) **Caught Exception: Age must be 18 or above. / Execution finished.  <-- CORRECT**

> **Why:** The exception **is** thrown, so "Age is valid." never prints. `super(message)` passes the text up to Throwable, so `getMessage()` returns it rather than null. `finally` always runs.



**Q. [EXPECTED] [TRAP] Which of the following is a checked exception?**

- (a) NullPointerException
- (b) ArrayIndexOutOfBoundsException
- (c) **IOException  <-- CORRECT**
- (d) ArithmeticException

> **Why:** **Checked** exceptions are detected at compile time and must be caught or declared: IOException, SQLException, ClassNotFoundException. The other three are **unchecked** (subclasses of RuntimeException).



**Q. [PYQ] [TRAP] Output of: `int Integer = 24; char String = 'I'; System.out.print(Integer); System.out.print(String);`**

- (a) I
- (b) Compiler Error
- (c) Throws Exception
- (d) **24I  <-- CORRECT**

> **Why:** `Integer` and `String` are **class names, not reserved keywords**, so they are legal identifiers. `print()` adds no newline, so the outputs run together as **24I**.



**Q. [PYQ] Which of the following is FALSE about packages?**

- (a) **Packages cannot provide controlled access.  <-- CORRECT**
- (b) Packages are used to prevent naming conflicts.
- (c) Packages are considered data encapsulation.
- (d) Packages prevent naming conflicts and are considered data encapsulation.

> **Why:** Packages **do** provide controlled access, because `default` (package-private) and `protected` members are visible only within the package.



**Q. [PYQ] What is the name of the .NET collection class that enables an element to be accessed using a unique key?**

- (a) Linked list
- (b) **Hashtable  <-- CORRECT**
- (c) Double linked list
- (d) Array list

> **Why:** A **Hashtable** stores key-value pairs and retrieves values directly from the key by hashing, giving average **O(1)** access. Lists and arrays are accessed by position or traversal.



**Q. [EXPECTED] [TRAP] Which Java collection allows duplicate elements and maintains insertion order?**

- (a) HashSet
- (b) TreeSet
- (c) **ArrayList  <-- CORRECT**
- (d) HashMap

> **Why:** **List** implementations (ArrayList, LinkedList, Vector) are ordered and allow duplicates. **Set** forbids duplicates. **Map** stores key-value pairs and is not a Collection subinterface.



**Q. [EXPECTED] [TRAP] Which of the following is thread-safe (synchronised)?**

- (a) ArrayList
- (b) HashMap
- (c) **Vector  <-- CORRECT**
- (d) LinkedList

> **Why:** **Vector** and **Hashtable** are the legacy synchronised classes. `ArrayList` and `HashMap` are not synchronised and are therefore faster. Also: **HashMap allows one null key**, whereas **Hashtable allows none**.



## 4.4 .NET Framework



> **WEIGHTAGE: 1-3 marks in DSSSB | Appeared in all three papers supplied | Priority MEDIUM**



### 4.4.1 Questions



**Q. [PYQ] Which of the following is the execution engine for .NET applications and servers, acting as the interface between .NET applications and the operating system?**

- (a) Framework Class Library (FCL)
- (b) Common Type System (CTS)
- (c) Common Language Specifications (CLS)
- (d) **Common Language Runtime (CLR)  <-- CORRECT**

> **Why:** The **CLR** executes managed code and provides garbage collection, memory management, security, exception handling and thread management. FCL is a class library; CTS defines types; CLS defines cross-language rules. None of those *execute* anything.



**Q. [PYQ] ______ is a code that consists of CPU and platform-independent set of instructions, which can be easily converted to the native code.**

- (a) DLL
- (b) FCL
- (c) JIT
- (d) **MSIL  <-- CORRECT**

> **Why:** **MSIL** (Microsoft Intermediate Language, also CIL/IL) is the intermediate output of a .NET compiler; the **JIT** compiler is what *converts* it to native code at run time. A **DLL** is a compiled file; **FCL** is a library.



**Q. [PYQ] Which of the following is NOT a feature of ADO.net?**

- (a) Maintainability
- (b) Interoperability
- (c) **Reachability  <-- CORRECT**
- (d) Scalability

> **Why:** ADO.NET's stated features are **interoperability, maintainability, programmability, performance and scalability**. "Reachability" belongs to graph theory and garbage collection.



**Q. [PYQ] How to write the dot net server control?**

- (a) <asp:controlType ID="ControlID" runin="server" ...>
- (b) <asp:controlType ID="ControlID" runas="server" ...>
- (c) <asp:controlType ID="ControlID" run="server" ...>
- (d) **<asp:controlType ID="ControlID" runat="server" ...>  <-- CORRECT**

> **Why:** Every ASP.NET server control requires **`runat="server"`** - that attribute is what makes the framework process the tag on the server. Memorise the exact spelling: r-u-n-a-t. The distractors are `runin`, `runas` and `run`.



**Q. [EXPECTED] Which ADO.NET object provides fast, forward-only, read-only access to query results?**

- (a) DataSet
- (b) DataAdapter
- (c) **DataReader  <-- CORRECT**
- (d) Connection

> **Why:** **DataReader** streams rows while connected - fastest for read-only traversal. **DataSet** is a disconnected in-memory copy that can be modified and reconciled later via a **DataAdapter**.

