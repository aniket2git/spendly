
---

# PART H - Web Technologies, XML, PHP and E-Commerce

> *HTML, CSS, JavaScript, AJAX, XML and e-commerce models. Four to eight marks, and almost entirely syntax recall.*



## H1 How the Web Works



### H1.1 The client-server story


When you type an address in your browser, this is what happens:


*A web request from start to finish*
```
1. You type  www.example.com/page.html  in the BROWSER (the CLIENT).
2. DNS translates "www.example.com" into an IP address.
3. The browser opens a TCP connection to that IP on port 80 (or 443).
4. It sends an HTTP request:   GET /page.html HTTP/1.1
5. The WEB SERVER (Apache, Nginx, IIS) receives the request.
6. If the page is STATIC, the server just returns the file.
   If it is DYNAMIC, the server runs a program (PHP, ASP.NET, servlet),
   which may query a DATABASE, and returns the generated HTML.
7. The server sends an HTTP response:  200 OK  + the HTML.
8. The browser PARSES the HTML, fetches CSS/JS/images, and RENDERS the page.
```


- **Web browser** - The CLIENT program whose primary function is **to display and navigate web pages**. It also acts as the **universal front end** for database applications reached over the internet. Examples: Chrome, Firefox, Edge, Safari.
- **Web server** - Software that stores web content and serves it in response to HTTP requests. Apache, Nginx, IIS, Tomcat.
- **Rendering engine** - The part of the browser that turns HTML and CSS into pixels: Blink (Chrome), Gecko (Firefox), WebKit (Safari).
- **Static web page** - Same content for everyone; a plain file.
- **Dynamic web page** - Content generated at request time, often personalised.
- **Client-side scripting** - Runs in the browser: JavaScript. Fast, no server round trip, but visible to the user.
- **Server-side scripting** - Runs on the server: PHP, ASP.NET, JSP, Node.js, Python. Code is hidden, can access databases.


> **NOTE: Two direct PYQs**
>
> "What is the primary function of a web browser?" Answer: **To display and navigate web pages.** It does not create websites (that needs an editor), does not primarily store data, and does not send email (that needs a mail client).
>
> "______ are a database applications' universal front end that connects to the back end via the internet." Answer: **Web browsers**. The reasoning: whatever the database or platform, the *same* browser can act as the user interface - that universality is the point. A "web server" is the middle tier, and a "web application" is what runs *inside* the browser.



### H1.2 HTTP


- **HTTP** - **HyperText Transfer Protocol** - the application-layer protocol defining how clients and servers exchange web resources. It is **stateless**: each request is independent and the server remembers nothing between requests.


| HTTP method | Purpose |
|---|---|
| GET | Retrieve a resource. Parameters appear in the URL, so they are visible and length-limited. Should not change server state |
| POST | Submit data in the request BODY. Hidden from the URL, no length limit. Used for forms and file uploads |
| PUT | Create or replace a resource |
| DELETE | Remove a resource |
| HEAD | Like GET but returns only the headers |
| PATCH | Partially update a resource |



| Status code | Meaning |
|---|---|
| 1xx | Informational |
| 2xx | Success. 200 OK, 201 Created |
| 3xx | Redirection. 301 Moved Permanently, 304 Not Modified |
| 4xx | CLIENT error. 400 Bad Request, 401 Unauthorised, 403 Forbidden, 404 NOT FOUND |
| 5xx | SERVER error. 500 Internal Server Error, 502 Bad Gateway, 503 Service Unavailable |


- **Cookie** - A small text file the server asks the browser to store, sent back on later requests. This is how a stateless protocol can "remember" a logged-in user.
- **Session** - Server-side storage of user state, usually keyed by a session ID held in a cookie.
- **CGI** - **Common Gateway Interface** - the original standard defining how a web server passes a request to an external program and receives its output. Largely replaced by faster approaches (FastCGI, modules, servlets).


> **NOTE: PYQ worked out - note the answer-key discrepancy**
>
> "________ is the standard that defines how web servers and application programs communicate." Options: JDBC, ODBC, CGI, HTTP. The official key gave **HTTP**.
>
> Strictly speaking, the standard that defines how a **web server** hands a request to an **external application program** is **CGI (Common Gateway Interface)** - that is CGI's textbook definition, word for word. **HTTP** defines how a **browser and a web server** communicate.
>
> For the exam: if the question mentions "web server and application program", the theoretically correct answer is **CGI**; if it mentions "client/browser and web server", it is **HTTP**. This paper chose HTTP, so be alert - read whether the pairing is browser-to-server (HTTP) or server-to-program (CGI).



### H1.3 Database connectivity from applications



| Standard | Full form | Used by |
|---|---|---|
| ODBC | Open Database Connectivity | A language-independent, largely Microsoft/C-based API for connecting to any database through a driver |
| JDBC | Java Database Connectivity | The Java-specific API for the same purpose |
| ADO.NET | - | The .NET data access technology |



> **NOTE: Direct PYQ**
>
> "Communication between an application program and a database server occur via:" Answer: **ODBC OR JDBC**.
>
> Why not the others: an "API" is too general a term; a "web server" serves web pages, not database queries; and "HTTP" is a web transfer protocol, not a database interface. ODBC and JDBC are the actual **driver-based standards** that let application code issue SQL to a database engine.



## H2 HTML



### H2.1 Structure of an HTML document


- **HTML** - **HyperText Markup Language** - the markup language that describes the *structure* of a web page using tags. It is not a programming language.


*The basic skeleton*
```
<!DOCTYPE html>
<html>
  <head>
    <title>Page title shown on the browser tab</title>
    <meta charset="UTF-8">
    <link rel="stylesheet" type="text/css" href="style.css">
  </head>
  <body>
    <h1>A heading</h1>
    <p>A paragraph of text.</p>
  </body>
</html>
```


- **Tag** - A keyword in angle brackets: `<p>`. Most tags come in pairs with a closing tag `</p>`.
- **Empty / void tag** - Has no closing tag: `<br>`, `<hr>`, `<img>`, `<input>`, `<meta>`, `<link>`.
- **Attribute** - Extra information inside the opening tag: `<img src="a.jpg" alt="text">`.
- **Element** - The opening tag, the content and the closing tag together.


### H2.2 Essential tags



| Tag | Purpose |
|---|---|
| h1 to h6 | Headings, h1 largest |
| p | Paragraph |
| br | Line break |
| hr | Horizontal rule |
| b / strong | Bold / semantically important |
| i / em | Italic / emphasis |
| u | Underline |
| sub / sup | Subscript / superscript |
| a | ANCHOR - creates a hyperlink |
| img | Image |
| ul / ol / li | Unordered list / ordered list / list item |
| dl / dt / dd | Definition list, term, description |
| table / tr / th / td | Table, row, header cell, data cell |
| form / input / select / textarea / button | Form controls |
| div | A block-level generic container |
| span | An inline generic container |
| iframe | Embeds another document |



### H2.3 Hyperlinks - the anchor tag



*Creating a link*
```
<a href="https://example.com" target="_blank">Visit Example</a>

  href   = Hypertext REFerence - the DESTINATION URL. This is the
           attribute that actually creates the hyperlink.
  target = where to open it
```



> **NOTE: Direct PYQ**
>
> "Which of the following parameters is used to create a hyperlink in HTML?" Options: Link, url, Path, **Href**. Answer: **Href**.
>
> The `<a>` tag by itself does nothing without `href`. There is no `link`, `url` or `path` attribute on an anchor tag. `href` stands for **Hypertext REFerence**.



#### Values of the target attribute


| Value | Where the linked document opens |
|---|---|
| _self | In the SAME frame / tab (this is the default) |
| _blank | In a NEW window or tab |
| _parent | In the PARENT frame |
| _top | In the FULL BODY of the window - it breaks out of ALL frames and uses the entire window |
| framename | In the named frame |



> **NOTE: PYQ worked out**
>
> "Which of the following opens the linked document in the windows full body among the target values?" Answer: **_top**.
>
> The phrase "**full body of the window**" is the definition of `_top` - it escapes every enclosing frameset and takes over the whole window. Distinguish it from `_parent`, which climbs only ONE level up, and `_blank`, which opens a brand-new window rather than reusing the current one.



### H2.4 Forms



*A simple form*
```
<form action="/submit.php" method="post">
  <input type="text"     name="username" placeholder="Name">
  <input type="password" name="pwd">
  <input type="radio"    name="gender" value="M">     <!-- pick ONE      -->
  <input type="checkbox" name="hobby"  value="music"> <!-- pick MANY     -->
  <select name="city"><option value="dl">Delhi</option></select>
  <textarea name="msg" rows="4"></textarea>
  <input type="submit" value="Send">
</form>
```


- **action** - The URL that will process the submitted data.
- **method** - GET (data in the URL) or POST (data in the body).
- **name** - The key under which each field's value is sent.
- **Radio button vs checkbox** - Radio buttons sharing a name allow only **one** selection; checkboxes allow **many**.


### H2.5 HTML5 additions


- **Semantic tags** - `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`, `figure` - they describe *meaning*, which helps search engines and screen readers.
- **Media tags** - `audio`, `video` - native playback without plugins.
- **canvas** - A drawing surface scripted with JavaScript.
- **svg** - Scalable Vector Graphics.
- **New input types** - email, url, number, range, date, color, search - with built-in validation.
- **Storage** - localStorage (persists) and sessionStorage (cleared when the tab closes).
- **Others** - Geolocation API, Web Workers, WebSockets, Drag and Drop.


## H3 CSS



### H3.1 What CSS does


- **CSS** - **Cascading Style Sheets** - describes how HTML elements should be *presented*: colour, font, spacing, layout. It separates presentation from structure.


*Anatomy of a CSS rule*
```
   selector  {  property : value ;  }

   h1 { color: blue; font-size: 24px; }
   |    |      |
   |    |      +-- declaration
   |    +--------- property and value
   +-------------- selector: which elements this applies to
```



### H3.2 The three ways to apply CSS



| Method | How | Priority |
|---|---|---|
| Inline | A `style` attribute on the element itself: `<p style="color:red">` | HIGHEST |
| Internal / Embedded | A `<style>` block inside `<head>` | Medium |
| EXTERNAL | A separate .css file linked with `<link>` in `<head>` | Lowest, but BEST PRACTICE - one file styles the whole site |



*The correct syntax for external CSS*
```
<link rel="stylesheet" type="text/css" href="style.css">

Break it down:
   <link>     the tag used inside <head> to attach an external resource
   rel        the RELATIONSHIP - here "stylesheet"
   type       the MIME type - "text/css"
   href       the path to the file

COMMON WRONG FORMS SEEN IN EXAMS:
   <style rel="stylesheet" ... >     WRONG - <style> is for INTERNAL CSS
   <style href="style.css"></style>  WRONG - <style> has no href attribute
   <a href="style.css" rel="...">    WRONG - <a> creates a hyperlink
```



> **NOTE: Direct PYQ**
>
> "Which of the following is the syntax to write an external CSS?" Answer: **`<link rel="stylesheet" type="text/css" href="style.css">`**.
>
> The single distinguishing point is the **`<link>`** tag. Anything using `<style>` is internal CSS; anything using `<a>` is a hyperlink. Memorise the full line exactly as written above.



### H3.3 Selectors



| Selector | Syntax | Selects |
|---|---|---|
| Element / Type | `p { }` | All p elements |
| Class | `.warning { }` | All elements with class="warning". Reusable, many per page |
| ID | `#header { }` | The single element with id="header". Must be UNIQUE |
| Universal | `* { }` | Everything |
| Descendant | `div p { }` | Any p inside a div |
| Child | `div > p { }` | Only direct children |
| Grouping | `h1, h2 { }` | Several selectors sharing one rule |
| Attribute | `input[type="text"] { }` | By attribute value |
| Pseudo-class | `a:hover { }` | A state: hover, active, visited, focus, first-child, nth-child |
| Pseudo-element | `p::first-line { }` | A part of an element: first-line, first-letter, before, after |



#### Specificity - which rule wins

From strongest to weakest: **inline style > ID > class / attribute / pseudo-class > element**. The `!important` flag overrides everything. When two rules have equal specificity, the **later** one wins - that is the "cascading" in CSS.


### H3.4 The box model



*Every element is a box*
```
   +-------------------------------------------+
   |               MARGIN                      |  space OUTSIDE the border
   |   +-----------------------------------+   |
   |   |            BORDER                 |   |
   |   |   +---------------------------+   |   |
   |   |   |         PADDING           |   |   |  space INSIDE the border
   |   |   |   +-------------------+   |   |   |
   |   |   |   |     CONTENT       |   |   |   |  width x height
   |   |   |   +-------------------+   |   |   |
   |   |   +---------------------------+   |   |
   |   +-----------------------------------+   |
   +-------------------------------------------+
```


- **Total width** - content width + left/right padding + left/right border + left/right margin (in the default `content-box` model).
- **box-sizing: border-box** - Makes the declared width include padding and border - much easier to reason about.


### H3.5 Display, position and filters



| Property | Values and meaning |
|---|---|
| display | block (full width, new line), inline (flows in text, ignores width/height), inline-block (flows but accepts size), none (removed entirely), flex, grid |
| position | static (default), relative (offset from its normal place), absolute (positioned relative to the nearest positioned ancestor), fixed (relative to the viewport, stays on scroll), sticky |
| float | left, right - takes the element out of normal flow |
| z-index | Stacking order for overlapping positioned elements |



#### CSS filters


*PYQ: making all images black and white*
```
img { filter: grayscale(100%); }

Points to notice:
  - the property is  filter
  - the function is  grayscale  (American spelling, NOT "graycolor")
  - the value is NOT quoted

WRONG FORMS OFFERED IN THE EXAM:
  img { filter: graycolor(100%); }      -> no such function
  img { graycolor(100%); }              -> not a property at all
  img { filter: "grayscale(100%)"; }    -> quotes are invalid here
```



> **NOTE: Direct PYQ**
>
> "How to change all images to black and white (100% grey)?" Answer: **`img { filter: grayscale(100%);}`**
>
> Other useful filter functions worth knowing: `blur(5px)`, `brightness(150%)`, `contrast(200%)`, `invert(100%)`, `opacity(50%)`, `sepia(100%)`, `saturate(0%)`.



## H4 JavaScript, DHTML and AJAX



### H4.1 JavaScript basics


- **JavaScript** - A **client-side** (and now also server-side) scripting language that makes web pages interactive. It is interpreted, dynamically typed and case-sensitive. It has nothing to do with Java despite the name.


*Variables, types and output*
```
var  x = 10;      // function-scoped, old style
let  y = 20;      // block-scoped, modern
const z = 30;     // block-scoped constant

// Data types: Number, String, Boolean, Undefined, Null, Object, Symbol, BigInt

console.log("message");        // writes to the developer console
document.write("text");        // writes directly into the document
alert("popup");                // modal popup box
```



*PYQ traced: a simple if-else*
```
let x = 10;
if (x > 5) {
    console.log("Greater");
} else {
    console.log("Smaller");
}

  x is 10, and 10 > 5 is true, so the if branch runs.
OUTPUT: "Greater"
```



### H4.2 document.write and escape sequences



> **NOTE: PYQ worked out - a genuinely tricky one**
>



*PYQ*
```
<script>
document.write("Hello")
document.write("\nIndia")
</script>

WHAT THE ANSWER KEY SAYS: Hello India

THE REASONING THE EXAMINER WANTS:
  document.write outputs into the HTML document. In HTML, a newline
  character (\n) is NOT rendered as a line break - HTML COLLAPSES all
  whitespace (newlines, tabs, multiple spaces) into a SINGLE SPACE.

  So the \n does not start a new line, but it does not vanish either -
  it becomes one space. Result:  Hello India

  To get a real line break in HTML you must write <br>:
      document.write("Hello<br>India")

REMEMBER THE PRINCIPLE:
  \n works in a console, in an alert box, and in a plain text file.
  \n does NOT create a visible line break in rendered HTML.
```



### H4.3 The DOM and DHTML


- **DOM** - **Document Object Model** - a tree representation of the page that JavaScript can read and modify. Every tag becomes a node.
- **DHTML** - **Dynamic HTML** - not a language, but the *combination* of HTML + CSS + JavaScript + DOM used to change a page after it has loaded, without fetching a new page.


| Task | Code |
|---|---|
| Find an element by id | `document.getElementById("myDiv")` |
| Find by class | `document.getElementsByClassName("box")` |
| Find by tag | `document.getElementsByTagName("p")` |
| Modern query | `document.querySelector(".box")` , `querySelectorAll()` |
| Change the content | `element.innerHTML = "new text"` |
| Change a style | `element.style.backgroundColor = "red"` |
| Change an attribute | `element.setAttribute("src", "b.jpg")` |
| Create an element | `document.createElement("div")` |
| Add to the page | `parent.appendChild(child)` |
| Attach an event | `element.addEventListener("click", myFunction)` |
| Resize the window | `window.resizeTo(800, 600)` |
| Open a new window | `window.open("url")` |
| Redirect | `window.location.href = "url"` |



> **NOTE: Two direct PYQs on DHTML methods**
>
> "Which of the following DHTML methods is used to change the style of an HTML element using CSS dynamically?" Answer: **`element.style.backgroundColor = "red"`**.
>
> Explanation: every DOM element exposes a `style` object whose properties correspond to CSS properties. Note the naming rule - CSS `background-color` (with a hyphen) becomes JavaScript `backgroundColor` (camelCase), because hyphens are not legal in JavaScript identifiers. The distractors are invented: there is no `setCSS()` method; `createElement("style")` makes a new style tag rather than changing an element; and `addEventListener("resize")` merely listens for an event.
>
> "Which of the following DHTML methods is used to control the browser window size, such as resizing it dynamically via JavaScript?" Answer: **`window.resizeTo()`**. There is no `window.setSize()`, `window.changeSize()` or `document.resizeWindow()`. Related genuine methods: `window.resizeBy()` (resize by a relative amount), `window.moveTo()`, `window.scrollTo()`.



#### Common JavaScript events

onclick, ondblclick, onmouseover, onmouseout, onkeydown, onkeyup, onchange, onsubmit, onfocus, onblur, onload, onunload, onresize.


### H4.4 AJAX


- **AJAX** - **Asynchronous JavaScript And XML**. A technique for exchanging small amounts of data with the server **in the background**, so a page can update part of itself **without reloading the whole page**.


#### Why AJAX matters

- **Reduced bandwidth consumption** - it sends and retrieves only the small piece of data that is actually needed, instead of the entire page with all its HTML, CSS and images.
- **Faster, smoother user experience** - no full-page flash.
- **Asynchronous** - the user can keep interacting while the request is in flight.


*How AJAX works*
```
1. A user action fires a JavaScript function.
2. The script creates an XMLHttpRequest (or calls fetch()).
3. The request goes to the server IN THE BACKGROUND.
4. The server responds with a small payload - today usually JSON,
   originally XML.
5. A JavaScript callback updates just the relevant part of the DOM.

The page never reloads. Examples: Google search suggestions, live
cricket scores, infinite scrolling, form validation as you type.
```



> **NOTE: Direct PYQ**
>
> "Which advantage of AJAX helps in reducing bandwidth consumption?" Answer: **AJAX sends and retrieves only small amounts of data from the server.**
>
> The other options are simply false: AJAX does not "use less JavaScript" (it uses more), it does not "only load images", and it certainly does not "increase data transfer" - the whole point is to *decrease* it.


- **Drawbacks of AJAX** - The browser back button and bookmarking break unless handled; content may not be indexed by search engines; it depends on JavaScript being enabled.
- **JSON** - **JavaScript Object Notation** - a lightweight, human-readable data format of key-value pairs. It has largely replaced XML in AJAX because it is smaller and parses natively in JavaScript.


### H4.5 jQuery


- **jQuery** - A JavaScript library that simplifies DOM traversal, event handling, animation and AJAX. Its slogan is "write less, do more". The `$` symbol is the jQuery function.


| jQuery method | Effect |
|---|---|
| $("#id") , $(".class") | Select elements (CSS-style selectors) |
| .hide() , .show() , .toggle() | Visibility |
| .fadeIn() , .fadeOut() , .fadeToggle() | Fading effects |
| .slideDown() , .slideUp() , .slideToggle() | SLIDING effects - slideDown reveals an element by sliding it down |
| .html() , .text() , .val() | Get or set content |
| .css() | Get or set styles |
| .addClass() , .removeClass() | Class manipulation |
| .append() , .prepend() | Insert content |
| .click() , .on() | Event binding |
| $.ajax() , $.get() , $.post() | AJAX requests |



> **NOTE: Direct PYQ**
>
> "Which of the following methods is used to slide down an element?" Options: **slideDown()**, moveBelow(), moveDown(), slideBelow(). Answer: **slideDown()**.
>
> The jQuery sliding family is exactly three methods: `slideDown()`, `slideUp()` and `slideToggle()`. There is no `moveBelow`, `moveDown` or `slideBelow` in jQuery. When in doubt, remember that jQuery effect names come in **Down / Up / Toggle** and **In / Out / Toggle** triplets.



### H4.6 AngularJS directives


- **Directive** - A special attribute starting with `ng-` that tells AngularJS to attach behaviour to a DOM element.


| Directive | Purpose |
|---|---|
| ng-app | Marks the root element of the application |
| ng-init | Initialises application data |
| ng-MODEL | BINDS the value of an HTML control (input, select, textarea) to a property on the application data - two-way DATA BINDING between MODEL and VIEW |
| ng-bind | One-way binding of data into the element's text |
| ng-repeat | Repeats an element once per item in a collection |
| ng-if , ng-show , ng-hide | Conditional rendering / visibility |
| ng-click | Click handler |
| ng-controller | Attaches a controller to the view |



> **NOTE: Direct PYQ**
>
> "Which directive is used for binding the model data to the view?" Options: ng-model-view, ng-model-app, **ng-model**, ng-app-model. Answer: **ng-model**.
>
> `ng-model` provides **two-way data binding**: type in the input and the model updates; change the model in code and the input updates. The other three options are invented names - AngularJS has no `ng-model-view`, `ng-model-app` or `ng-app-model`.



## H5 XML



### H5.1 What XML is and how it differs from HTML


- **XML** - **eXtensible Markup Language** - a language for **storing and transporting data** in a self-describing, platform-independent, text-based format. It does not display anything.


| Point | HTML | XML |
|---|---|---|
| Purpose | To DISPLAY data | To STORE and TRANSPORT data |
| Tags | A fixed, predefined set | You DEFINE YOUR OWN tags - it is extensible |
| Case sensitive | No | YES |
| Closing tags | Some are optional | MANDATORY for every element |
| Attribute quotes | Optional | MANDATORY |
| Whitespace | Collapsed | PRESERVED |
| Root element | Implicit | Exactly ONE root element is required |
| Well-formedness | Browsers tolerate errors | Errors cause a parse failure |



*A well-formed XML document*
```
<?xml version="1.0" encoding="UTF-8"?>
<school>
  <student id="1">
    <name>Asha</name>
    <marks>88</marks>
  </student>
  <student id="2">
    <name>Ravi</name>
    <marks>91</marks>
  </student>
</school>
```


- **Well-formed XML** - Obeys all syntax rules: one root, every tag closed, correct nesting, quoted attributes, case-matched tags.
- **Valid XML** - Well-formed **and** conforms to a DTD or XML Schema.
- **CDATA section** - `<![CDATA[ ... ]]>` - text the parser should not interpret as markup.
- **Entity references** - `&lt;` for <, `&gt;` for >, `&amp;` for &, `&quot;` for ", `&apos;` for '.
- **Namespace** - `xmlns:prefix="URI"` - prevents element-name clashes between vocabularies.


### H5.2 The XML processor and parsers


- **XML processor (XML parser)** - The software component that **READS an XML document and provides access to its content and structure** to an application. It also checks well-formedness.


> **NOTE: Direct PYQ**
>
> "______ reads XML documents and provides access to their content and structure." Options: XML schema, XML pre-processor, **XML processor**, XML codes. Answer: **XML processor**.
>
> Note the distinction: an **XML schema** *describes* what a valid document looks like; it does not read anything. "XML pre-processor" and "XML codes" are not real terms.



| Parser | Type | Characteristics |
|---|---|---|
| DOM | Tree-based | Loads the WHOLE document into memory as a tree. Random access, can modify and write back. Memory-hungry for large files |
| SAX | Event-based | Streams through the document firing events (startElement, endElement, characters). Very memory-efficient, but READ-ONLY and forward-only |
| StAX | Pull-based | The application pulls events as needed |
| JDOM / dom4j | Java tree APIs | Easier Java-friendly alternatives to DOM |



> **NOTE: Direct PYQ**
>
> "Which of the following is NOT an XML Parser?" Options: **Shell**, JDOM, DOM, SAX. Answer: **Shell**.
>
> A **shell** is a command-line interpreter in an operating system (bash, csh, ksh) - it has nothing to do with XML. DOM, SAX and JDOM are all genuine XML parsers/APIs.



### H5.3 DTD and XML Schema


- **DTD** - **Document Type Definition** - the older way to declare the legal structure of an XML document: which elements exist, their order, and their attributes. Written in its own non-XML syntax and has no data types.
- **XSD (XML Schema Definition)** - The modern replacement. Written **in XML itself**, supports **data types** (integer, date, decimal), namespaces, and much richer constraints.


*Internal vs external DTD*
```
INTERNAL DTD - declared inside the document:
   <!DOCTYPE note [
     <!ELEMENT note (to, from, body)>
     <!ELEMENT to   (#PCDATA)>
   ]>

EXTERNAL DTD - kept in a separate file:
   <!DOCTYPE root-element SYSTEM "file-name">

   Break down the external form:
     <!DOCTYPE      the declaration keyword
     root-element   the name of the document's ROOT element - comes FIRST
     SYSTEM         keyword meaning "a private, local file follows"
     "file-name"    the path to the .dtd file, in quotes

   PUBLIC is used instead of SYSTEM for a widely published, standard DTD.
```



> **NOTE: Direct PYQ**
>
> "How to write the external DTD?" Answer: **`<!DOCTYPE root-element SYSTEM "file-name">`**
>
> The **order** is what is being tested. The root element name must come immediately after `<!DOCTYPE`, then `SYSTEM`, then the quoted filename. Every wrong option scrambles that order: `<!DOCTYPE SYSTEM "file-name">` omits the root element; `<!DOCTYPE element ROOT "file-name">` invents a ROOT keyword; `<!DOCTYPE SYSTEM "file-name" root-element>` puts the root element last.



#### Related XML technologies

- **XSL / XSLT** - eXtensible Stylesheet Language Transformations - transforms XML into HTML, text or other XML.
- **XPath** - A syntax for navigating to nodes in an XML document.
- **XQuery** - A query language for XML data.
- **XLink / XPointer** - Linking within and between XML documents.
- **SOAP** - Simple Object Access Protocol - an XML-based messaging protocol for web services.
- **WSDL** - Web Services Description Language - describes a web service in XML.
- **RSS** - An XML format for publishing frequently updated content.


## H6 PHP



### H6.1 PHP basics


- **PHP** - **PHP: Hypertext Preprocessor** (originally Personal Home Page) - an open-source **server-side** scripting language embedded in HTML. The code runs on the server and only the resulting HTML reaches the browser.


*PHP essentials*
```
<?php
  $name = "Asha";              // variables ALWAYS start with $
  $marks = 88;                 // loosely typed - no declaration needed
  echo "Hello $name";          // double quotes INTERPOLATE variables
  echo 'Hello $name';          // single quotes do NOT - prints literally
  $total = $marks + 10;
  echo "<br>" . $total;        // dot (.) is the STRING CONCATENATION operator
?>
```


- **echo vs print** - `echo` can take several arguments and returns nothing; `print` takes one argument and returns 1. `echo` is marginally faster.
- **Superglobals** - `$_GET`, `$_POST`, `$_REQUEST`, `$_SESSION`, `$_COOKIE`, `$_FILES`, `$_SERVER`.
- **include vs require** - Both insert another file. `include` gives a **warning** and continues if the file is missing; `require` gives a **fatal error** and stops. The `_once` variants prevent double inclusion.


### H6.2 PHP arrays and sorting functions



| Array type | Example |
|---|---|
| Indexed | `$a = array("x", "y");` keys are 0, 1 |
| Associative | `$a = array("name" => "Asha", "marks" => 88);` |
| Multidimensional | Arrays inside arrays |


This sorting table is asked directly, so learn the two dimensions: **what is sorted (values or keys)** and **whether the key association survives**.


| Function | Sorts by | Order | Preserves key-value association? |
|---|---|---|---|
| sort() | VALUE | Ascending | NO - keys are reindexed 0,1,2... |
| rsort() | VALUE | Descending | NO - keys are reindexed |
| ASORT() | VALUE | ASCENDING | YES - keys stay attached to their values |
| arsort() | VALUE | Descending | YES |
| ksort() | KEY | Ascending | YES |
| krsort() | KEY | Descending | YES |
| usort() | VALUE, via a user function | Custom | NO |
| uasort() | VALUE, via a user function | Custom | YES |



> **NOTE: Direct PYQ**
>
> "Which of the following PHP functions is used to sort an array in ascending order without affecting the keys?" Options: ksort(), array_sort(), **asort()**, sort(). Answer: **asort()**.
>
> Decode the names and you never need to memorise the table:
> - plain **sort** - sorts values, throws keys away
> - prefix **a** (associative) - keeps the key-value pairing
> - prefix **k** - sorts by key instead of value
> - prefix **r** (reverse) - descending
> - prefix **u** - user-defined comparison
>
> So "ascending, values, keys preserved" = a + sort = **asort()**. Note that `array_sort()` does not exist in PHP at all, and `ksort()` would sort by key rather than value.



#### Other useful PHP functions

count(), array_push(), array_pop(), array_merge(), in_array(), array_keys(), array_values(), implode(), explode(), strlen(), strtoupper(), str_replace(), trim(), substr(), date(), isset(), empty(), unset().


## H7 E-Commerce



### H7.1 What e-commerce is


- **E-commerce** - **Electronic commerce** - buying and selling goods, services and information over electronic networks, principally the internet.
- **E-business** - A broader term including all electronic business processes - supply chain, CRM, internal operations - not just buying and selling.
- **Commerce** - The activity that **primarily deals with buying and selling, particularly on a large scale.** (Distinguish from *trade*, which is narrower, and from *distribution* or *supply chain*, which are logistics functions.)


> **NOTE: Direct PYQ**
>
> "______ primarily deals with buying and selling, particularly on a large scale." Options: **Commerce**, Finance, Supply chain, Distribution. Answer: **Commerce**. Finance deals with money and capital; supply chain and distribution deal with moving goods; only *commerce* is defined by the act of buying and selling at scale.



### H7.2 E-commerce business models



| Model | Meaning | Example |
|---|---|---|
| B2B - Business to Business | One business sells to another | IndiaMART, Alibaba, a manufacturer selling to a wholesaler |
| B2C - Business to Consumer | A business sells directly to the end consumer | Amazon, Flipkart, Myntra |
| C2C - Consumer to Consumer | CONSUMERS SELL TO OTHER CONSUMERS through a third-party platform | OLX, Quikr, eBay, Facebook Marketplace |
| C2B - Consumer to Business | Individuals offer products/services to businesses | Freelancers on Upwork, stock photo contributors, influencers |
| B2G / B2A - Business to Government | Businesses sell to government bodies | GeM (Government e-Marketplace), e-tenders |
| G2C - Government to Citizen | Government provides services to citizens | Income tax e-filing, Passport Seva, DigiLocker |



> **NOTE: Direct PYQ**
>
> "The ______ E-commerce segment(s) is/are represented by OLX." Options: C2C, B2C and B2B / B2B / **C2C** / B2C. Answer: **C2C**.
>
> Reasoning: on OLX an **individual** lists a used phone or a sofa and **another individual** buys it. OLX itself does not own or sell the goods - it merely provides the platform. That is the textbook definition of Consumer-to-Consumer. Compare Amazon, which is primarily B2C because Amazon (or a business seller) sells to consumers.



### H7.3 Revenue models



| Revenue model | How money is made |
|---|---|
| Advertising | Free content funded by ads. Google, Facebook, YouTube |
| SUBSCRIPTION | A FIXED SUM PAID BY CUSTOMERS FOR A SERVICE, typically on a MONTHLY, QUARTERLY OR ANNUAL basis. Netflix, Spotify, newspapers |
| Transaction fee | A commission on each transaction. eBay, Uber, payment gateways |
| Sales | Direct sale of goods or services |
| Affiliate | Earning a referral commission for sending buyers to another site |
| Licensing | Charging for the right to use software or content |
| Freemium | A free basic tier with paid premium features |



> **NOTE: Direct PYQ**
>
> "A fixed sum that is paid by customers for a service, typically on a monthly, quarterly or annual basis, is called ______ in electronic commerce." Options: licensing, affiliate, marketing, **subscription**. Answer: **subscription**.
>
> The trigger words are "**fixed sum**" and "**monthly/quarterly/annual**" - recurring payment for continued access is the definition of a subscription. *Licensing* is a one-time or per-seat right to use; *affiliate* is commission for referrals; *marketing* is not a revenue model at all.



### H7.4 E-commerce infrastructure and payments


- **Payment gateway** - A service that authorises and processes online card/UPI payments securely. Razorpay, PayU, Stripe.
- **Digital wallet / e-wallet** - Stored value on a phone or website. Paytm, PhonePe, Google Pay.
- **UPI** - Unified Payments Interface - India's instant real-time bank-to-bank payment system, built by NPCI.
- **Electronic Data Interchange (EDI)** - The structured, computer-to-computer exchange of standard business documents (purchase orders, invoices) between organisations - a pre-internet forerunner of B2B e-commerce.
- **SSL / HTTPS** - Encrypts the connection so card details cannot be intercepted. The padlock in the address bar.
- **Digital signature and certificate** - Authenticate the parties in an online transaction (see Part G).
- **Cash on Delivery (COD)** - Payment collected at the door - very important in the Indian market.
- **M-commerce** - Commerce conducted through mobile devices.
- **Web surfing** - **The process of visiting different web sites on the internet** hosted by various companies, organisations, educational institutions, magazines and individuals. (Distinguish from *searching*, which is looking for something specific, and *chatting*.)


> **NOTE: Two more direct PYQs**
>
> "______ is the process of visiting different web sites on the internet hosted by various companies, organisations, educational institutions, magazines, individuals, etc." Answer: **Web surfing**. "Webbing" is not a term; "searching" implies a specific query; "chatting" is real-time messaging.
>
> "Who is the father of e-commerce in India?" Answer: **K Vaitheeswaran** - founder of Fabmart/Indiaplaza, India's first e-commerce venture (1999). Note for contrast: **Michael Aldrich** (a distractor in the same question) is credited with inventing **online shopping / teleshopping worldwide** in 1979 - so he is the father of e-commerce *globally*, not in India. Examiners like to swap these two.



### H7.5 Advantages, limitations and security concerns



| Advantages | Limitations |
|---|---|
| Open 24 x 7, no geographic limits | Cannot physically inspect the product before buying |
| Lower operating cost, no showroom needed | Requires internet access and digital literacy |
| Wider customer reach, global market | Security and privacy fears |
| Easy price comparison for buyers | Delivery delays and shipping costs |
| Personalisation and recommendations | Difficult returns and after-sales service |
| Faster transactions, digital records | Lack of personal touch; trust issues with unknown sellers |


- **Main security requirements** - Confidentiality, integrity, authentication, non-repudiation, availability - exactly the goals covered in Part G.
- **IT Act 2000** - The Indian law giving legal recognition to electronic records and digital signatures, and defining cybercrimes.
