
---

# PART 8 - Web Technologies, XML, PHP and E-Commerce

> *Weightage: 4 to 8 marks in DSSSB, 3 to 8 expected. Almost entirely syntax recall - the cheapest marks in the Computer Science half.*



## 8.1 Web Architecture and HTTP



> **WEIGHTAGE: 1-2 marks | Priority HIGH**



### 8.1.1 Questions



**Q. [PYQ] What is the primary function of a web browser?**

- (a) To store large amounts of data
- (b) To send and receive emails
- (c) To create websites
- (d) **To display and navigate web pages  <-- CORRECT**

> **Why:** A browser **renders and navigates**. Creating sites needs an editor; email needs a mail client.



**Q. [PYQ] ________ are a database applications' universal front end that connects to the back end via the internet.**

- (a) **Web browsers  <-- CORRECT**
- (b) Web server
- (c) Software programs
- (d) Web application

> **Why:** Whatever the database or platform, the **same browser** can act as the interface - that universality is exactly the point of the question.



**Q. [PYQ] [TRAP] ________ is the standard that defines how web servers and application programs communicate.**

- (a) JDBC
- (b) ODBC
- (c) CGI
- (d) **HTTP  <-- CORRECT**

> **Why:** **KEY NOTE.** This paper's key said HTTP. Textbook theory: **CGI (Common Gateway Interface)** is the standard defining how a web *server* passes a request to an external *application program*; **HTTP** defines *browser-to-server* communication. Judge by the pairing named in the question.



**Q. [PYQ] Communication between an application program and a database server occurs via:**

- (a) **ODBC OR JDBC  <-- CORRECT**
- (b) API
- (c) web server
- (d) HTTP

> **Why:** **ODBC** is the language-independent driver standard; **JDBC** is its Java equivalent. "API" is too general; a web server serves pages, not SQL.



**Q. [EXPECTED] [TRAP] Which HTTP method sends data in the request body rather than the URL?**

- (a) GET
- (b) **POST  <-- CORRECT**
- (c) HEAD
- (d) OPTIONS

> **Why:** **GET** puts parameters in the URL - visible, bookmarkable and length-limited. **POST** puts them in the body - hidden from the URL and unlimited in size, so it is used for forms, passwords and file uploads.



**Q. [EXPECTED] Which HTTP status code range indicates a client error?**

- (a) 2xx
- (b) 3xx
- (c) **4xx  <-- CORRECT**
- (d) 5xx

> **Why:** **1xx** informational, **2xx** success (200 OK), **3xx** redirection (301, 304), **4xx** client error (**400, 401, 403, 404**), **5xx** server error (500, 502, 503).



## 8.2 HTML and CSS



> **WEIGHTAGE: 1-3 marks | Exact syntax is tested, so memorise the strings | Priority HIGH**



### 8.2.1 Questions



**Q. [PYQ] Which of the following parameters is used to create a hyperlink in HTML?**

- (a) Link
- (b) url
- (c) Path
- (d) **Href  <-- CORRECT**

> **Why:** `href` = **Hypertext REFerence**. The `<a>` tag does nothing without it. There is no `link`, `url` or `path` attribute on an anchor.



**Q. [PYQ] [TRAP] Which of the following opens the linked document in the window's full body among the target values?**

- (a) _self
- (b) **_top  <-- CORRECT**
- (c) _blank
- (d) _parent

> **Why:** "**Full body of the window**" defines **_top** - it escapes *all* enclosing framesets. **_parent** climbs only **one** level; **_blank** opens a brand-new tab; **_self** (the default) reuses the current frame.



**Q. [PYQ] Which of the following is the syntax to write an external CSS?**

- (a) <style rel="stylesheet" type="text/css" href="style.css">
- (b) <style> href="style.css" </style>
- (c) **<link rel="stylesheet" type="text/css" href="style.css">  <-- CORRECT**
- (d) <a href="style.css" rel="stylesheet" type="text/css">

> **Why:** The decisive element is the **`<link>`** tag placed inside `<head>`. Anything using `<style>` is **internal** CSS; `<a>` creates a hyperlink. Memorise the full line exactly.



**Q. [EXPECTED] [TRAP] Which CSS declaration has the highest priority?**

- (a) An element selector
- (b) A class selector
- (c) An ID selector
- (d) **An inline style attribute  <-- CORRECT**

> **Why:** Specificity order: **inline style > ID > class/attribute/pseudo-class > element**, with `!important` overriding everything. When specificity ties, the **later** rule wins - that is the "cascading" in CSS.



**Q. [PYQ] How to change all images to black and white (100% grey)?**

- (a) img { filter: graycolor(100%);}
- (b) **img { filter: grayscale(100%);}  <-- CORRECT**
- (c) img { graycolor(100%);}
- (d) img { filter: "grayscale(100%)";}

> **Why:** The property is **filter**, the function is **grayscale** (American spelling, not "graycolor"), and the value is **not quoted**. Other useful filters: blur, brightness, contrast, invert, opacity, sepia.



**Q. [EXPECTED] In the CSS box model, the order from innermost outward is:**

- (a) margin, border, padding, content
- (b) **content, padding, border, margin  <-- CORRECT**
- (c) content, border, padding, margin
- (d) padding, content, border, margin

> **Why:** **Padding is inside the border; margin is outside it.** With the default `content-box` model, declared width excludes padding and border - which is why `box-sizing: border-box` is so widely used.



**Q. [EXPECTED] Which HTML tag is an empty (void) element?**

- (a) <p>
- (b) <div>
- (c) **<br>  <-- CORRECT**
- (d) <span>

> **Why:** Void elements have no closing tag: **`<br>`, `<hr>`, `<img>`, `<input>`, `<meta>`, `<link>`**.



**Q. [EXPECTED] [TRAP] Which input type allows selecting only ONE option from a group?**

- (a) checkbox
- (b) **radio  <-- CORRECT**
- (c) select multiple
- (d) text

> **Why:** **Radio buttons sharing the same `name`** permit exactly one selection; **checkboxes** allow many. A `<select>` without `multiple` also allows one, but radio is the canonical answer.



## 8.3 JavaScript, DHTML, AJAX and jQuery



> **WEIGHTAGE: 2-4 marks | DOM methods and AJAX benefits recur | Priority HIGH**



### 8.3.1 Questions



**Q. [PYQ] What is the output of: `let x = 10; if (x > 5) console.log("Greater"); else console.log("Smaller");`**

- (a) "Smaller"
- (b) "undefined"
- (c) **"Greater"  <-- CORRECT**
- (d) Error

> **Why:** 10 > 5 is true.



**Q. [PYQ] [TRAP] What will the output be? `document.write("Hello")` then `document.write("\nIndia")`**

- (a) Hello
- (b) HelloIndia
- (c) India
- (d) **Hello India  <-- CORRECT**

> **Why:** **HTML collapses all whitespace** - newlines, tabs and multiple spaces - into a **single space**. So `\n` does not create a line break but does not vanish either. For a real break you must write `<br>`. Note `\n` *does* work in a console, an alert box, or a plain text file.



**Q. [PYQ] Which DHTML method is used to change the style of an HTML element using CSS dynamically?**

- (a) document.createElement("style")
- (b) document.getElementById("element").setCSS()
- (c) **element.style.backgroundColor = "red"  <-- CORRECT**
- (d) window.addEventListener("resize")

> **Why:** Every DOM element exposes a `style` object. Note the naming rule: CSS `background-color` (hyphenated) becomes JavaScript **`backgroundColor`** (camelCase), because hyphens are illegal in identifiers. There is no `setCSS()` method.



**Q. [PYQ] Which DHTML method is used to control the browser window size?**

- (a) **window.resizeTo()  <-- CORRECT**
- (b) window.setSize()
- (c) window.changeSize()
- (d) document.resizeWindow()

> **Why:** Only `resizeTo()` and `resizeBy()` exist; the other three names are invented. Related real methods: `window.open()`, `window.moveTo()`, `window.scrollTo()`.



**Q. [EXPECTED] Which method selects a single element by its id?**

- (a) document.getElementsByClassName()
- (b) **document.getElementById()  <-- CORRECT**
- (c) document.createElement()
- (d) document.write()

> **Why:** Note the singular/plural distinction: `getElementById` returns **one** element; `getElementsByClassName` and `getElementsByTagName` return **collections**. Modern equivalents: `querySelector()` and `querySelectorAll()`.



**Q. [EXPECTED] DHTML is best described as:**

- (a) a programming language
- (b) a markup language
- (c) **the combination of HTML, CSS, JavaScript and the DOM used to change a page after it loads  <-- CORRECT**
- (d) a server-side technology

> **Why:** DHTML is **not a language** - it is the technique of combining those four to make a page dynamic without fetching a new page.



**Q. [PYQ] Which advantage of AJAX helps in reducing bandwidth consumption?**

- (a) AJAX uses less JavaScript.
- (b) AJAX only loads images on the page.
- (c) AJAX increases data transfer.
- (d) **AJAX sends and retrieves only small amounts of data from the server.  <-- CORRECT**

> **Why:** Only the needed fragment is exchanged instead of a full page with all its HTML, CSS and images. AJAX = **Asynchronous JavaScript And XML**, though today the payload is usually **JSON**.



**Q. [EXPECTED] [TRAP] What is the main drawback of AJAX?**

- (a) It is slower than page reloads
- (b) **The browser back button and bookmarking break unless specially handled  <-- CORRECT**
- (c) It cannot access servers
- (d) It requires Java

> **Why:** Because the URL does not change, history and bookmarks break by default. AJAX content may also be invisible to search engines, and it fails entirely if JavaScript is disabled.



**Q. [PYQ] Which of the following methods is used to slide down an element?**

- (a) **slideDown()  <-- CORRECT**
- (b) moveBelow()
- (c) moveDown()
- (d) slideBelow()

> **Why:** jQuery effects come in triplets: **slideDown/slideUp/slideToggle** and **fadeIn/fadeOut/fadeToggle**. There is no `moveBelow` or `slideBelow`.



**Q. [PYQ] Which directive is used for binding the model data to the view?**

- (a) ng-model-view
- (b) ng-model-app
- (c) **ng-model  <-- CORRECT**
- (d) ng-app-model

> **Why:** **`ng-model`** provides AngularJS **two-way data binding** - type in the input and the model updates, change the model and the input updates. The other three names do not exist.



## 8.4 XML



> **WEIGHTAGE: 1-3 marks | Parsers and DTD syntax recur | Priority HIGH**



### 8.4.1 Questions



**Q. [PYQ] ______ reads XML documents and provides access to their content and structure.**

- (a) XML schema
- (b) XML pre-processor
- (c) **XML processor  <-- CORRECT**
- (d) XML codes

> **Why:** An **XML schema** *describes* what a valid document looks like; it reads nothing. The **processor (parser)** does the reading and also checks well-formedness.



**Q. [PYQ] Which of the following is NOT an XML Parser?**

- (a) **Shell  <-- CORRECT**
- (b) JDOM
- (c) DOM
- (d) SAX

> **Why:** A **shell** is an OS command interpreter (bash, csh, ksh). DOM, SAX and JDOM are genuine XML parsers.



**Q. [EXPECTED] [TRAP] Which XML parser loads the entire document into memory as a tree?**

- (a) SAX
- (b) StAX
- (c) **DOM  <-- CORRECT**
- (d) JDOM

> **Why:** **DOM** builds a full in-memory tree - allows random access and modification, but is memory-hungry. **SAX** is **event-based**, streaming through the document firing events; it is very memory-efficient but **read-only and forward-only**.



**Q. [PYQ] How to write the external DTD?**

- (a) <!DOCTYPE SYSTEM "file-name">
- (b) <!DOCTYPE element ROOT "file-name">
- (c) <!DOCTYPE SYSTEM "file-name" root-element>
- (d) **<!DOCTYPE root-element SYSTEM "file-name">  <-- CORRECT**

> **Why:** **Order is what is being tested**: `<!DOCTYPE`, then the **root element name**, then `SYSTEM`, then the quoted filename. Use `PUBLIC` instead of `SYSTEM` for a widely published standard DTD.



**Q. [EXPECTED] [TRAP] Which of the following is TRUE of XML but not of HTML?**

- (a) Tags are predefined
- (b) Closing tags are optional
- (c) **It is case sensitive and every tag must be closed  <-- CORRECT**
- (d) Whitespace is collapsed

> **Why:** XML is **case sensitive**, requires **every** tag to be closed, requires **quoted** attribute values, **preserves** whitespace, and needs exactly **one root element**. HTML is forgiving on all these counts.



**Q. [EXPECTED] XSD is preferred over DTD because XSD:**

- (a) is shorter
- (b) **is written in XML itself and supports data types and namespaces  <-- CORRECT**
- (c) is older
- (d) needs no parser

> **Why:** DTD uses its own non-XML syntax and has **no data types**. **XSD** (XML Schema Definition) is written in XML, supports integer/date/decimal types, namespaces and far richer constraints.



## 8.5 PHP



> **WEIGHTAGE: 0-2 marks | Array sorting functions are the classic question | Priority MEDIUM**



### 8.5.1 Questions



**Q. [PYQ] Which PHP function is used to sort an array in ascending order without affecting the keys?**

- (a) ksort()
- (b) array_sort()
- (c) **asort()  <-- CORRECT**
- (d) sort()

> **Why:** Decode the naming scheme and you never memorise the table: plain **sort** sorts values and discards keys; prefix **a** (associative) **preserves the key-value pairing**; prefix **k** sorts by **key**; prefix **r** means reverse (descending); prefix **u** means a user-defined comparison. So "ascending, by value, keys preserved" = **asort()**. Note `array_sort()` does not exist in PHP.



**Q. [EXPECTED] In PHP, which operator concatenates two strings?**

- (a) +
- (b) **.  <-- CORRECT**
- (c) &
- (d) ++

> **Why:** PHP uses the **dot** for concatenation (`$a . $b`); `+` is strictly arithmetic. (JavaScript and Java use `+`, which is a common source of confusion.)



**Q. [EXPECTED] [TRAP] What is the difference between include and require in PHP?**

- (a) They are identical
- (b) **include gives a warning and continues if the file is missing; require gives a fatal error and stops  <-- CORRECT**
- (c) require is faster
- (d) include cannot be used twice

> **Why:** Use **require** for files the script genuinely cannot run without. The `_once` variants prevent accidental double inclusion.



**Q. [EXPECTED] In PHP, variables enclosed in which quotes are interpolated (substituted)?**

- (a) Single quotes
- (b) **Double quotes  <-- CORRECT**
- (c) Backticks
- (d) Either

> **Why:** `"Hello $name"` substitutes the value; `'Hello $name'` prints the literal text. PHP variables always begin with **$**.



## 8.6 E-Commerce



> **WEIGHTAGE: 1-3 marks in DSSSB | Business-model classification is the standard question | Priority MEDIUM**



### 8.6.1 Questions



**Q. [PYQ] ______ primarily deals with buying and selling, particularly on a large scale.**

- (a) **Commerce  <-- CORRECT**
- (b) Finance
- (c) Supply chain
- (d) Distribution

> **Why:** Commerce is *defined* by buying and selling at scale. Finance concerns money and capital; supply chain and distribution are logistics functions.



**Q. [PYQ] The ______ E-commerce segment(s) is/are represented by OLX.**

- (a) C2C, B2C and B2B
- (b) B2B
- (c) **C2C  <-- CORRECT**
- (d) B2C

> **Why:** On OLX an **individual sells to another individual** and the platform merely connects them - textbook **Consumer-to-Consumer**. Compare Amazon (mainly **B2C**), IndiaMART (**B2B**) and GeM (**B2G**).



**Q. [EXPECTED] [TRAP] A freelancer offering services to a company on Upwork is an example of:**

- (a) B2C
- (b) C2C
- (c) **C2B  <-- CORRECT**
- (d) B2B

> **Why:** **C2B (Consumer-to-Business)** - an individual supplies value to a business. Also covers stock-photo contributors and influencer marketing. It is the least-known model and therefore a favourite distractor.



**Q. [PYQ] A fixed sum paid by customers for a service, typically on a monthly, quarterly or annual basis, is called ______ in electronic commerce.**

- (a) licensing
- (b) affiliate
- (c) marketing
- (d) **subscription  <-- CORRECT**

> **Why:** "**Fixed sum**" plus "**monthly/quarterly/annual**" defines a recurring **subscription** (Netflix, Spotify). *Licensing* is a right-to-use fee; *affiliate* is referral commission.



**Q. [PYQ] ______ is the process of visiting different web sites on the internet hosted by various companies, organisations, educational institutions, magazines, individuals, etc.**

- (a) Webbing
- (b) Searching
- (c) Chatting
- (d) **Web surfing  <-- CORRECT**

> **Why:** **Surfing** = browsing around generally; **searching** implies a specific query. "Webbing" is not a term.



**Q. [PYQ] [TRAP] Who is the father of e-commerce in India?**

- (a) Bryan Eisenberg
- (b) Michael Aldrich
- (c) **K Vaitheeswaran  <-- CORRECT**
- (d) Tim Ferris

> **Why:** **K Vaitheeswaran** founded Fabmart/Indiaplaza in 1999, India's first e-commerce venture. **Michael Aldrich** invented online shopping **globally** in 1979 - examiners deliberately place both in the same question, so read whether it asks about India or the world.



**Q. [EXPECTED] EDI stands for:**

- (a) Electronic Data Integration
- (b) **Electronic Data Interchange  <-- CORRECT**
- (c) Electronic Document Indexing
- (d) Encrypted Data Interface

> **Why:** **EDI** is the structured computer-to-computer exchange of standard business documents (purchase orders, invoices) between organisations - a pre-internet forerunner of B2B e-commerce.



**Q. [EXPECTED] Which of the following is NOT a security requirement of an e-commerce transaction?**

- (a) Confidentiality
- (b) Integrity
- (c) Non-repudiation
- (d) **Portability  <-- CORRECT**

> **Why:** The security goals are confidentiality, integrity, authentication, **non-repudiation** and availability. **Portability** is a software quality attribute. Note **non-repudiation** - the sender cannot later deny sending - is achieved by digital signatures.

