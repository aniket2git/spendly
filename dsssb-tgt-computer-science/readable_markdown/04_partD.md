
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

