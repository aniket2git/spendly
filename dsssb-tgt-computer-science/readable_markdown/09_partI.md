
---

# PART I - Software Engineering, Computer Graphics and Management Information Systems

> *Three medium-weight topics grouped together. Together they contribute six to twelve marks.*



## I1 Software Engineering Fundamentals



### I1.1 Why software engineering exists


One person can build a doghouse with a hammer and no plan. A hundred people cannot build a skyscraper that way - they need drawings, schedules, inspections and standards.

Software is the same. A 200-line program needs no process. A 200,000-line banking system does. **Software engineering** is the application of a systematic, disciplined, measurable approach to the development, operation and maintenance of software.

- **Software crisis** - The historical realisation that projects were routinely late, over budget, unreliable and unmaintainable - which gave birth to software engineering as a discipline.
- **Software** - Computer programs plus the associated documentation and configuration data.


#### Software characteristics

Software is **developed / engineered**, not manufactured. It does not **wear out**, but it does **deteriorate** through repeated modification. It is **flexible** and largely **custom-built** rather than assembled from existing components.


### I1.2 Functional vs non-functional requirements


- **Functional requirement** - **WHAT the system must DO** - a specific behaviour or feature. "The system shall allow a user to log in with an email and password." These describe the **core work tasks** the system must perform - they are **mandatory**.
- **Non-functional requirement** - **HOW WELL** the system must do it - a quality attribute. Performance, security, usability, reliability, portability, scalability, maintainability, availability. Often called "quality requirements" or "constraints".


> **NOTE: PYQ worked out**
>
> "______ activities are at the very core of project completion work tasks, whereas ______ activities are not mandatory." Answer: **Functional, non-functional**.
>
> The logic: functional requirements define the actual work the software must do - without them the project is not complete at all. Non-functional requirements describe desirable qualities; a system can technically function (though badly) without meeting them, so in this framing they are "not mandatory".
>
> Note the distractor "Framework, umbrella". In Pressman's model, **umbrella activities** are the ones that run *across* the whole process - project tracking, risk management, quality assurance, configuration management, measurement - while **framework activities** are the main phases (communication, planning, modelling, construction, deployment). Do not confuse the two pairs.



### I1.3 Levels of design



| Design level | Abstraction | What it produces |
|---|---|---|
| SYSTEM design | HIGHEST abstraction | A high-level view of the complete system as a whole - the overall concept, inputs, outputs and major components |
| ARCHITECTURAL design | Middle | Breaks the concept into LESS-ABSTRACTED sub-systems and defines the relationships between them |
| DETAILED design | LOWEST abstraction | Shows the IMPLEMENTATION at MODULE LEVEL - algorithms, data structures, interfaces of each module |



> **NOTE: PYQ worked out**
>
> "The ______ design is high-abstraction version of a system that is followed by ______ design that breaks the concept into less-abstracted view of sub-systems and later the ______ design showcases the implementation at module-level."
>
> Answer: **system, architectural, detailed.**
>
> The sequence always runs from most abstract to most concrete: **System to Architectural to Detailed**. A memory hook: you first picture the whole *system*, then draw its *architecture*, then fill in the *details*.



### I1.4 Coupling and cohesion - a guaranteed question


These two words are the heart of good software design, and examiners love them because students mix them up.

- **Coupling** - The degree of **interdependence BETWEEN different modules**. How much one module needs to know about another.
- **Cohesion** - The degree to which the elements **INSIDE a single module** belong together and work toward one single purpose.

**The design rule: coupling should be LOW, cohesion should be HIGH.**

Analogy: think of school departments. **Low coupling** means the science department can change its lab timetable without the music department needing to be informed. **High cohesion** means everything inside the science department genuinely relates to science - not a random mix of science, accounts and sports.


> **NOTE: PYQ worked out**
>
> "In building software, ______ should preferably be lower and ______ is preferred to be on the higher side." Answer: **coupling among components, cohesion in bonding components**.
>
> Why low coupling and high cohesion are good: low coupling means a change in one module does not ripple through the system, so maintenance is easier and modules can be tested and reused independently. High cohesion means each module has a single, clear responsibility, which makes it understandable and reliable.
>
> Watch the distractors in that question - "inheritance from parent class" and "aggregation with peer components" are OOP relationship terms, not the design-quality pair the question is asking for.



| Coupling type (worst to best) | Description |
|---|---|
| Content coupling (worst) | One module directly modifies or relies on the internal contents of another |
| Common coupling | Modules share global data |
| External coupling | Modules share an externally imposed format or protocol |
| Control coupling | One module passes a flag that controls the other's logic |
| Stamp coupling | A whole data structure is passed when only part is needed |
| Data coupling (best) | Only the simple parameters actually needed are passed |
| Message coupling | Communication only through public interfaces / messages - loosest of all |



| Cohesion type (best to worst) | Description |
|---|---|
| Functional cohesion (best) | Every element contributes to one single well-defined task |
| Sequential cohesion | Output of one element is input to the next |
| Communicational cohesion | Elements operate on the same data |
| Procedural cohesion | Elements follow a certain sequence of execution |
| Temporal cohesion | Elements are grouped because they happen at the same time (e.g. all start-up code) |
| Logical cohesion | Elements do similar kinds of things, selected by a flag |
| Coincidental cohesion (worst) | Elements are grouped for no meaningful reason at all |



## I2 Software Development Life Cycle Models



### I2.1 The phases common to all models



*The generic SDLC*
```
1. REQUIREMENT gathering and analysis  ->  produces the SRS document
2. SYSTEM DESIGN                       ->  architecture and detailed design
3. IMPLEMENTATION / CODING             ->  source code
4. TESTING                             ->  test reports, defect logs
5. DEPLOYMENT                          ->  the software in live use
6. MAINTENANCE                         ->  fixes and enhancements
```


- **SRS** - **Software Requirement Specification** - the formal document recording all functional and non-functional requirements. It is the contract between customer and developer. A good SRS is correct, complete, consistent, unambiguous, verifiable and traceable.
- **Feasibility study** - Checks technical, economic, legal, operational and schedule viability before committing.


### I2.2 The Waterfall model


The oldest and simplest model. Each phase must be **fully completed** before the next begins, and the flow is strictly downward - like water falling over steps.


| Advantages | Disadvantages |
|---|---|
| Simple, easy to understand and manage | VERY RIGID - you cannot go back to a previous phase |
| Clear, well-documented phases with defined deliverables | Requirement changes cannot be accommodated. UNSUITABLE when requirements alter during development |
| Works well when requirements are fixed and clearly understood | Working software appears only very LATE |
| LOW COST for small, well-understood projects | HIGH RISK because problems surface only at the testing stage |
| Easy to schedule and assign responsibilities | No customer feedback until the end; LONG DURATION for large projects |



> **NOTE: PYQ worked out**
>
> "Which of the following is NOT true about the Waterfall model?" Options: Long duration, **High cost**, High-risk involvement, Low cost. Answer: **High cost**.
>
> Reasoning: the waterfall model is generally described as a **low-cost** model - it needs no repeated prototyping, no elaborate risk analysis and minimal customer interaction, so its process overhead is small. Its genuine drawbacks are long duration and high risk. The trap is that the option list contains **both** "High cost" and "Low cost"; you must pick the one that is NOT true, which is High cost.



### I2.3 All the SDLC models compared



| Model | Core idea | Best suited when |
|---|---|---|
| Waterfall (Linear sequential) | Strictly sequential phases, no going back | Requirements are FIXED and fully known upfront |
| V-Model (Verification and Validation) | Each development phase has a matching testing phase, forming a V shape. Testing is planned in parallel with development | Requirements are clear and the system is safety-critical |
| Incremental | The product is built and delivered in successive increments, each adding functionality | The core requirements are clear but the full feature set can evolve |
| Iterative | A rough version is built, then repeatedly refined through cycles | Requirements are expected to be refined over time |
| PROTOTYPE model | A working mock-up is built quickly, shown to the user, and refined based on feedback before real development | Requirements are UNCLEAR or the user cannot articulate them |
| SPIRAL model | Iterative development combined with explicit RISK ANALYSIS in every loop. Four quadrants: planning, risk analysis, engineering, evaluation | LARGE, EXPENSIVE, HIGH-RISK projects |
| RAD (Rapid Application Development) | Very fast development using component reuse, powerful tools and parallel teams | Small-to-medium projects with a tight deadline, modular design and available components |
| AGILE | Short iterations (sprints), continuous customer collaboration, working software over documentation, welcomes changing requirements | Requirements are VOLATILE and the customer is available for continuous feedback |
| Big Bang | Little planning; just start coding | Tiny projects or academic exercises |



> **NOTE: PYQ worked out - which model cannot handle change**
>
> "Within software engineering, which prescriptive model is INCOMPATIBLE with circumstances in which the requirements alter throughout development?" Options: **Linear models**, Evolutionary models, Agile models, Incremental models. Answer: **Linear models**.
>
> Reasoning: "Linear model" is another name for the **Waterfall** approach - each phase is frozen once complete, so a requirement change discovered during coding cannot be fed back into the design. By contrast, evolutionary, agile and incremental models are all specifically designed to absorb changing requirements through repeated cycles and customer feedback.



### I2.4 RAD model phases



| RAD phase | What happens |
|---|---|
| Business modelling | What information flows between business functions |
| Data modelling | The information flow is refined into a set of data objects and their attributes |
| Process modelling | Data objects are transformed to implement the business functions - the processing descriptions |
| Application generation | Automated tools and reusable components build the working software |
| Testing and turnover | New components are tested; already-reused components need less testing |



> **NOTE: PYQ worked out**
>
> "Which of the following is NOT a phase of the RAD model?" Options: **Development modelling**, Business modelling, Process modelling, Data modelling. Answer: **Development modelling**.
>
> The four genuine "modelling" phases in RAD are **Business, Data, Process** and then **Application Generation** followed by **Testing and Turnover**. "Development modelling" is not one of them - it is an invented name. Memory hook: **B**usiness, **D**ata, **P**rocess, **A**pplication, **T**esting.



### I2.5 Agile


- **Agile Manifesto values** - Individuals and interactions over processes and tools; **working software over comprehensive documentation**; customer collaboration over contract negotiation; **responding to change over following a plan**.
- **Sprint** - A short fixed-length iteration, typically 2 to 4 weeks, producing a potentially shippable increment.
- **Scrum** - The most popular agile framework. Roles: **Product Owner** (owns the backlog and priorities), **Scrum Master** (facilitator, removes impediments), **Development Team**.
- **Artefacts** - Product backlog, sprint backlog, increment, burndown chart.
- **Ceremonies** - Sprint planning, daily stand-up (15 minutes), sprint review, sprint retrospective.
- **Extreme Programming (XP)** - Agile practices including pair programming, test-driven development, continuous integration, small releases and refactoring.
- **User story** - A requirement written from the user's point of view: "As a student, I want to see my marks so that I can track my progress."
- **Kanban** - Visualising work on a board and limiting work-in-progress.


### I2.6 Software testing



| Type | Description |
|---|---|
| Unit testing | Testing the smallest individual module in isolation. Usually done by the developer |
| Integration testing | Testing how modules work together. Approaches: big-bang, top-down (needs STUBS), bottom-up (needs DRIVERS), sandwich |
| System testing | Testing the complete integrated system against the requirements |
| Acceptance testing | Testing by the customer to decide whether to accept the product. ALPHA testing is done at the developer's site by internal staff; BETA testing is done at the customer's site by real users |
| Regression testing | Re-running old tests after a change, to make sure nothing that used to work has broken |
| Smoke / Sanity testing | A quick check that the build is stable enough to test properly |
| Performance / Load / Stress testing | Behaviour under expected load, heavy load and beyond breaking point |
| Security testing | Looks for vulnerabilities |
| Usability testing | How easy the software is to use |



| Approach | Also called | Tester knows the internal code? | Focus |
|---|---|---|---|
| Black box testing | Functional testing | NO | Inputs and outputs only. Techniques: equivalence partitioning, boundary value analysis, decision tables, state transition |
| White box testing | Structural / glass box testing | YES | Internal logic, paths, branches. Techniques: statement coverage, branch coverage, path coverage, cyclomatic complexity |
| Grey box testing | - | Partially | A mixture of both |


- **Verification** - "Are we building the product **right**?" Checks conformance to the specification, without executing the code - reviews, walkthroughs, inspections.
- **Validation** - "Are we building the **right** product?" Checks that the software actually meets the user's needs, usually by executing it.
- **Error, Fault, Failure** - An **error** is a human mistake; it introduces a **fault (defect/bug)** into the code; when executed, the fault causes a **failure** - incorrect behaviour.
- **Test case** - A set of inputs, execution conditions and expected results.
- **Cyclomatic complexity** - McCabe's metric: V(G) = E - N + 2, where E is edges and N is nodes of the control flow graph. It equals the number of independent paths, and hence the minimum number of test cases for branch coverage. Also equal to (number of decision points + 1).


### I2.7 CMM - Capability Maturity Model


- **CMM** - **Capability Maturity Model** - a framework developed by the Software Engineering Institute (SEI) at Carnegie Mellon to assess and improve the maturity of an organisation's software process. Its successor is **CMMI** (Capability Maturity Model Integration).


| Level | Name | Characteristics |
|---|---|---|
| 1 | INITIAL | Ad hoc, chaotic. Success depends on individual heroics. No defined process |
| 2 | REPEATABLE (Managed) | Basic project management exists. Costs and schedules are tracked. Earlier successes on similar projects can be repeated |
| 3 | DEFINED | The process is documented and standardised organisation-wide, and tailored per project |
| 4 | MANAGED (Quantitatively Managed) | The process and product quality are MEASURED quantitatively and controlled statistically |
| 5 | OPTIMISING | CONTINUOUS process improvement driven by quantitative feedback and innovation. Defect prevention |



> **NOTE: Direct PYQ**
>
> "CMM stands for:" Options: Cognitive Modularity Model, Capability Modularity Model, Cognitive Measurable Model, **Capability Maturity Model**. Answer: **Capability Maturity Model**.
>
> Both words matter: **Capability** (what the organisation is able to do) and **Maturity** (how disciplined and repeatable its process is). Memory hook for the five levels: **I**nitial, **R**epeatable, **D**efined, **M**anaged, **O**ptimising - "**I R**eally **D**o **M**y **O**wn work."



### I2.8 Project management and estimation


- **COCOMO** - **COnstructive COst MOdel** by Barry Boehm - estimates effort in person-months from the size in KLOC. Three modes: **Organic** (small team, familiar problem), **Semi-detached** (medium), **Embedded** (tight constraints, complex).
- **Function Point analysis** - Estimates size from functionality (inputs, outputs, enquiries, files, interfaces) rather than lines of code, so it is language-independent.
- **LOC / KLOC** - Lines of code / thousands of lines of code.
- **Gantt chart** - A bar chart showing tasks against a calendar timeline.
- **PERT chart** - **Program Evaluation and Review Technique** - a network diagram showing task dependencies, used to compute the **critical path** (the longest path, which determines the minimum project duration).
- **Risk management** - Identify risks, analyse their probability and impact, plan responses, and monitor. Response strategies: **avoid, accept, transfer, mitigate**.
- **Software Configuration Management (SCM)** - Controlling change: version control, baselines, change control board, build management.
- **Software maintenance types** - **Corrective** (fixing faults), **Adaptive** (adjusting to a new environment), **Perfective** (improving performance or maintainability), **Preventive** (reducing future deterioration).


### I2.9 Pseudo-code, algorithms and flowcharts


- **Algorithm** - A finite, ordered set of unambiguous steps to solve a problem. Language-independent, written in plain English.
- **Pseudo-code** - A semi-formal notation that mixes natural language with programming-language structures (IF, WHILE, FOR). Because its structure already mirrors code, it is the **easiest to transform into an actual computer program**.
- **Flowchart** - A **diagrammatic** representation of an algorithm using standard symbols.


> **NOTE: Direct PYQ**
>
> "Which of the following is the easiest to be transformed into a computer program?" Options: **Pseudo-code**, Algorithm, Flowchart, None of the above. Answer: **Pseudo-code**.
>
> Reasoning: pseudo-code already uses programming constructs - loops, conditionals, assignment - written in a code-like layout. Converting it to C or Java is nearly a line-by-line translation. A plain-English algorithm is more abstract, and a flowchart is graphical, so both need more interpretation.



#### Flowchart symbols - asked directly


| Symbol | Meaning |
|---|---|
| Oval / Rounded rectangle (Terminal) | START or STOP |
| Parallelogram | INPUT or OUTPUT (read / print) |
| RECTANGLE | PROCESSING - a computation or assignment step |
| DIAMOND / Rhombus | DECISION - a yes/no or true/false branch |
| CIRCLE | CONNECTOR - joins parts of the program / flowchart, especially across pages |
| Arrow / Flow line | Direction of flow |
| Hexagon | Preparation or loop initialisation |
| Cylinder | Storage / database |



> **NOTE: PYQ worked out**
>
> "Program links with other parts of the program in a flowchart are represented by ______." Options: rectangles, **circles**, trapezoids, rhombuses. Answer: **circles**.
>
> Reasoning: the **connector** symbol is a small circle, used to link one part of a flowchart to another - typically when the diagram must break across pages or when several flow lines converge. Rectangles are processing steps, rhombuses (diamonds) are decisions, and trapezoids are sometimes used for manual operations.



## I3 Computer Graphics



### I3.1 Basic concepts


- **Computer graphics** - The creation, storage and manipulation of pictures and drawings using a computer.
- **Pixel** - **Picture element** - the smallest addressable dot on a screen.
- **Resolution** - The number of pixels, e.g. 1920 x 1080.
- **Frame buffer / Refresh buffer** - The area of memory holding the intensity value of every pixel on the screen.
- **Bit depth / Colour depth** - Bits used per pixel. 1 bit = monochrome, 8 bits = 256 colours, 24 bits = true colour.
- **Aspect ratio** - Width divided by height.
- **Raster / Bitmap graphics** - The image is stored as a grid of pixels. Loses quality when enlarged. Formats: BMP, JPEG, PNG, GIF.
- **Vector graphics** - The image is stored as mathematical descriptions of lines and curves. Scales to any size with no quality loss. Formats: SVG, AI, EPS.
- **Rasterisation** - The process of converting vector shapes into pixels for display.
- **Aliasing** - The jagged "staircase" appearance of a diagonal line drawn on a pixel grid. **Anti-aliasing** smooths it by varying pixel intensity.


### I3.2 Line and circle drawing algorithms



| Algorithm | Description |
|---|---|
| DDA (Digital Differential Analyser) | Computes each next point by adding a constant increment. Uses FLOATING POINT arithmetic and rounding, so it is slower and accumulates round-off error |
| BRESENHAM's line algorithm | Uses only INTEGER arithmetic (addition, subtraction and bit shifting) with a decision parameter. Faster and more accurate than DDA. The standard line algorithm |
| Mid-point circle algorithm | Draws a circle using a decision parameter and eight-way symmetry |
| Bresenham's circle algorithm | Integer-only circle drawing |
| Scan-line polygon fill | Fills a polygon by finding the intersections of each horizontal scan line with the polygon edges |
| Boundary fill / Flood fill | Recursively fills an area from a seed point outward |



### I3.3 Clipping


- **Clipping** - Discarding the parts of a picture that lie **outside** a specified region (the clipping window), so only the visible portion is drawn.


| Algorithm | Clips |
|---|---|
| Cohen-Sutherland | LINES. Assigns a 4-bit region code (outcode) to each endpoint and uses bitwise tests to trivially accept or reject |
| LIANG-BARSKY | LINES. Uses a parametric representation of the line and computes entry/exit parameters. More efficient than Cohen-Sutherland because it does fewer intersection calculations |
| Cyrus-Beck | Lines, against any convex polygon window |
| Nicholl-Lee-Nicholl | Lines, fewest intersections of all |
| Sutherland-Hodgman | POLYGONS, against each window edge in turn |
| Weiler-Atherton | Concave polygons |



> **NOTE: Direct PYQ**
>
> "Which of the following is a clipping algorithm?" Options: Simple DDA, **Liang Barsky's algorithm**, Bresenham's algorithm, Mid-point Algorithm. Answer: **Liang Barsky's algorithm**.
>
> The others are all **drawing** (scan-conversion) algorithms: DDA and Bresenham draw lines, and the mid-point algorithm draws circles. Only Liang-Barsky is a clipping algorithm. If Cohen-Sutherland ever appears as an option, it is also a clipping algorithm.



### I3.4 Two-dimensional transformations


**Transformations** change the position, size or orientation of an object. This is exactly the machinery that produces animation.


| Transformation | Effect | Matrix note |
|---|---|---|
| Translation | Moves an object by (tx, ty) without changing its shape | Addition, or a matrix with tx, ty in the last column using homogeneous coordinates |
| Scaling | Changes the size by factors (sx, sy). Uniform if sx = sy | Multiplication by a diagonal matrix |
| Rotation | Rotates by an angle about a point | Uses sin and cos |
| Reflection | Produces a mirror image about an axis or line | Scaling with negative factors |
| Shearing | Slants the shape; a rectangle becomes a parallelogram | Off-diagonal terms |


- **Homogeneous coordinates** - A point (x, y) is written as (x, y, 1) so that **translation also becomes a matrix multiplication**. This lets several transformations be combined into ONE matrix by multiplying them - called **composite transformation** or **concatenation**.
- **Rigid body transformation** - Preserves shape and size: translation, rotation, reflection.
- **Animation** - Achieved by applying a sequence of transformations to objects over successive frames.


> **NOTE: PYQ worked out**
>
> "In order to move objects in computer graphics that generate animation effects which of the following is necessary?" Answer: **Various transformation operations**.
>
> Reasoning: motion is nothing more than repeatedly changing an object's position, orientation or size between frames - that is, applying **translation, rotation and scaling**. The distractors belong elsewhere: "line rasterisation sequencing" is about drawing a single line onto pixels, the "Phong model of lighting" is about shading and illumination, and "eigen value computations" belong to linear algebra generally (used in some simulations, but not the mechanism of animation).



### I3.5 Three-dimensional viewing and projections


**Projection** maps a 3D object onto a 2D viewing plane.


| Projection | Description |
|---|---|
| PARALLEL projection | Projectors are PARALLEL to each other. Preserves relative dimensions and parallel lines, but looks less realistic. Used in engineering drawings |
| -- Orthographic | Projectors are PERPENDICULAR to the view plane. Gives the standard front, top and side views |
| -- Oblique | Projectors meet the plane at an angle. Cavalier and Cabinet projections |
| PERSPECTIVE projection | Projectors converge at a single point (the centre of projection / eye). Distant objects appear SMALLER - realistic, like the human eye or a camera. Introduces vanishing points |


- **Isometric projection** - An orthographic projection where all three axes are equally foreshortened.
- **Vanishing point** - The point at which parallel lines appear to converge in perspective projection. One-point, two-point and three-point perspective.
- **Standard orthographic views** - Front view, top view (plan) and side view (elevation) - together they fully describe an object.


> **NOTE: PYQ worked out**
>
> "______ and ______ views cannot be framed together for rendering a computer visual appropriately." Answer key: **Orthogonal projection, horizontal view**.
>
> The reasoning behind this style of question: certain view pairs are mutually incompatible in a single rendering because they use different projection geometry or would show the same information redundantly. An **orthographic (orthogonal)** projection uses parallel projectors perpendicular to the plane, so it cannot simultaneously present a **horizontal** viewing direction in the same frame - the two definitions conflict.
>
> Note that the tempting option "Parallel projection, perspective projection" is a genuinely incompatible pair in principle (you cannot use both projection types for one image), so if you meet a similar question with slightly different options, reason from **which two views define contradictory projector geometry**.



### I3.6 Lighting, shading and hidden surface removal


- **Illumination model** - Computes the colour of a point on a surface from the light sources and surface properties.
- **Ambient light** - Uniform background light with no direction.
- **Diffuse reflection** - Light scattered equally in all directions from a dull surface. Depends on the angle between the light and the surface normal (Lambert's law).
- **Specular reflection** - The shiny highlight from a glossy surface. Depends on the viewer's position.
- **PHONG lighting model** - Combines ambient + diffuse + specular components. The specular term uses a shininess exponent.


#### Parameters that influence lighting

The appearance of a lit surface depends on: the **light source** (position, colour, intensity), the **surface** (material, colour, normal direction, roughness), and the **position of the observer** (needed for specular highlights).


> **NOTE: PYQ worked out**
>
> "Which of these is NOT a parameter upon which the influence of lighting is based?" Options: Light Source, Position of Observer, **Rendering Algorithm**, Surface. Answer: **Rendering Algorithm**.
>
> Reasoning: the physical inputs to an illumination calculation are the light source, the surface properties and the observer's position. The **rendering algorithm** is the *method used to compute* the image - it is the process, not a parameter of the lighting itself. This is the same kind of distinction as "the recipe is not an ingredient".



| Shading method | Description |
|---|---|
| Flat / Constant shading | One colour for an entire polygon. Fastest, shows faceting |
| Gouraud shading | Intensity is computed at the vertices and INTERPOLATED across the polygon. Smooth, but can miss specular highlights inside a polygon |
| Phong shading | The surface NORMAL is interpolated and lighting is computed per pixel. Slower but much better highlights |



| Hidden surface removal | Method |
|---|---|
| Z-buffer (depth buffer) | Stores a depth value per pixel; the nearest surface wins. Simple and very widely used |
| Back-face detection | Discards polygons facing away from the viewer |
| Painter's algorithm (depth sort) | Draws polygons from farthest to nearest |
| Scan-line method | Resolves visibility one scan line at a time |
| Ray tracing | Traces rays from the eye through each pixel into the scene. Very realistic (reflections, refractions, shadows) but computationally expensive |



### I3.7 Virtual reality and image editing


- **Virtual Reality (VR)** - **The construction of computer-generated simulations that simulate real-world activities using interactive graphics software and hardware.** The user is immersed in and can interact with a synthetic 3D environment, usually via a head-mounted display, motion tracking and haptic gloves.
- **Augmented Reality (AR)** - Overlays computer-generated content onto the real world rather than replacing it.
- **Immersion, interaction, imagination** - The "three I's" of virtual reality.


> **NOTE: Direct PYQ**
>
> "The construction of computer-generated simulations that simulate real-world activities using interactive graphics software and hardware is called:" Answer: **virtual reality systems**.
>
> The other options belong to Artificial Intelligence: **genetic algorithms** are optimisation techniques modelled on natural selection; **fuzzy neural networks** combine fuzzy logic with neural networks; **hybrid systems** combine two or more AI techniques. Only virtual reality involves *simulating real-world activity with interactive graphics*.



#### Image editing (Photoshop-style) terms asked in the papers


| Term | Meaning |
|---|---|
| Adjustments panel | The Photoshop panel used to alter BRIGHTNESS, CONTRAST, levels, curves, hue and saturation - the standard place for tonal correction |
| Healing brush tool | Repairs blemishes by blending in nearby pixels |
| Paint bucket tool | Fills an area with a colour |
| Selection tools | Marquee, lasso, magic wand - define the area to work on |
| Cutting / Crop tool | REMOVES PARTS OF THE IMAGE |
| Layers | Stacked transparent sheets that can be edited independently |
| Resolution | Pixels per inch; changing it resizes or resamples |
| Filters | Effects applied to pixels: blur, sharpen, distort |



| Format | Best used for |
|---|---|
| PNG | LOSSLESS compression with TRANSPARENCY support. The standard choice for EXPORTING IMAGES FOR THE WEB, especially logos and graphics with sharp edges |
| JPEG / JPG | Lossy compression, small files, ideal for photographs on the web. No transparency |
| GIF | 256 colours, supports simple animation and transparency |
| SVG | Vector, infinitely scalable, ideal for icons and logos on the web |
| WebP | Modern web format, better compression than JPEG/PNG |
| PSD | Adobe Photoshop's NATIVE working file - keeps layers, but is huge and not viewable in browsers |
| TIFF | High-quality lossless format for printing and archiving. Very large files, not for the web |
| BMP | Uncompressed Windows bitmap. Enormous files, not for the web |



> **NOTE: Two direct PYQs on image editing**
>
> "Which tool is used to adjust the brightness and contrast of an image in Adobe Photoshop?" Answer: **Adjustments panel**.
>
> "Which of the following formats is commonly used for exporting images for the web?" Options: **PNG**, PSD, BMP, TIFF. Answer: **PNG**. PSD is Photoshop's editable working format, while BMP and TIFF produce very large files - none of the three is suitable for web delivery, where small size matters.
>
> "What is the main function of the 'cutting' tool in image editing?" Answer: **To remove parts of the image.** It does not change resolution, apply colour effects or resize.



## I4 Management Information Systems and Knowledge Management



### I4.1 Data, information, knowledge


- **Data** - Raw unprocessed facts. "45".
- **Information** - Processed, organised data that has meaning in a context. "The student scored 45 out of 100."
- **Knowledge** - Information combined with experience, judgement and understanding, enabling action. "A score of 45 in this subject usually means the student needs remedial help in fractions."
- **Wisdom** - Knowing which knowledge to apply and why.


### I4.2 What an information system is


- **Information system** - **A set of interrelated components that collect (or retrieve), process, store and distribute information to support decision-making and control in an organisation.**
- **Information technology** - The hardware, software and networks - the *tools*. An information *system* is broader: it includes the people and the procedures too.


> **NOTE: Direct PYQ**
>
> "______ is a set of interrelated components that collect (or retrieve), process, store and distribute information to support decision-making and control in an organisation." Answer: **An information system**.
>
> The distractor "An information technology" is deliberately close. Remember: **IT is the technology; an IS is technology + people + processes working together toward an organisational purpose.** The other options ("mini model / max model of a processed system") are not real terms.



#### The components of an information system

- **Hardware, Software, Data, People, Procedures, Networks** - The six classic components.
- **Organisation, Management, Technology** - The three dimensions of an information system in Laudon's framework. The **ORGANISATION** is the **formal social unit devoted to attaining specified goals**.


> **NOTE: Direct PYQ**
>
> "In a management information system, what is/are the formal social unit that is/are devoted to attaining specified goals?" Options: Organisation, management and marketing / **Organisation** / Management / Marketing. Answer: **Organisation**.
>
> Definition to memorise: an **organisation** is a stable, formal social structure that takes resources from the environment and processes them to produce outputs, coordinated toward specified goals. **Management** is the *function* of planning and directing; **marketing** is a business *activity*. Only "organisation" is the social *unit*.



### I4.3 Types of information system by management level



| System | Full form | Users | Purpose |
|---|---|---|---|
| TPS | Transaction Processing System | Operational staff | Records day-to-day routine transactions - payroll, order entry, billing |
| OAS | OFFICE AUTOMATION SYSTEM | All office workers | Supports clerical and communication work: WORD PROCESSING, ELECTRONIC FILING, ELECTRONIC MAIL, MESSAGE SWITCHING, DATA STORAGE, DATA AND VOICE COMMUNICATION, desktop publishing, scheduling |
| KWS | Knowledge Work System | Engineers, designers, analysts | Supports the creation of new knowledge - CAD, simulation |
| MIS | Management Information System | Middle management | Produces routine summary and exception REPORTS from TPS data, for monitoring and control |
| DSS | DECISION SUPPORT SYSTEM | Middle and senior management | A computer program application used to IMPROVE A COMPANY'S DECISION-MAKING CAPABILITIES. Analyses semi-structured problems using models, what-if analysis and simulation |
| ESS / EIS | Executive Support / Information System | Top executives | Highly summarised, graphical, strategic view with drill-down. Handles unstructured decisions |
| CRM | Customer Relationship Management | Sales and marketing | Manages all customer interactions |
| ERP | Enterprise Resource Planning | Whole organisation | One integrated system across finance, HR, manufacturing, supply chain |
| SCM | Supply Chain Management | Logistics | Manages suppliers, inventory and distribution |



> **NOTE: Two direct PYQs on system types**
>
> "DSS is a computer program application used to improve a company's ______ capabilities." Answer: **decision-making capabilities**. The name says it: **D**ecision **S**upport **S**ystem.
>
> "Which of the following systems comprises word processing, electronic filing, electronic mail, message switching, data storage and data and voice communication?" Answer: **Office Automation Systems**.
>
> Every item in that list is a routine *office* function - documents, filing, mail, messaging. An ESS gives executives strategic dashboards, a DSS runs analytical models, and CRM manages customers. Only OAS is about general office productivity and communication.



> **TIP: MIS vs DSS - the distinction examiners test**
>
> **MIS** answers "**what happened?**" with fixed, routine reports on structured data. **DSS** answers "**what if?**" and "**what is best?**" with flexible, interactive models on semi-structured problems. **ESS** answers "**what should we do strategically?**" with highly summarised external and internal data.



### I4.4 Knowledge management


- **Knowledge Management (KM)** - **The set of processes developed in an organisation to create, gather, store, transfer and apply knowledge.**


#### Purposes of a KM system

Driving strategy, integration of knowledge across the organisation, sharing of knowledge, capturing and codifying expertise, improving decisions, reducing duplicated effort, and retaining knowledge when employees leave.

Note that **portability** is *not* a purpose of a knowledge management system - it is a software quality attribute.


> **NOTE: Two direct PYQs on KM**
>
> "The set of processes developed in an organisation to create, gather, store, transfer and apply knowledge best describes:" Answer: **knowledge management**. ("Knowledge asset" is the *thing* being managed; "organisational memory" is the *store*; "organisational learning" is the *outcome*.)
>
> "Which of the following is NOT the purpose of knowledge management system?" Options: Driving strategy, Integration, Sharing of knowledge, **Portability**. Answer: **Portability**. Portability means software running on different platforms - a technical quality, unrelated to the goals of KM.



### I4.5 Tacit and explicit knowledge



| Type | Description | Example |
|---|---|---|
| TACIT knowledge | Personal, EXPERIENCE-BASED knowledge that is difficult to write down or formalise. It resides in a person's head and is acquired through practice. It **results from an individual's shared experience** | Knowing how to ride a bicycle; a master craftsman's feel for the material; an experienced teacher's classroom instinct |
| Explicit knowledge | Codified, documented knowledge that can easily be written, stored and transmitted | A manual, a textbook, a database, a written procedure |


- **SECI model (Nonaka and Takeuchi)** - The four modes of knowledge conversion: **Socialisation** (tacit to tacit), **Externalisation** (tacit to explicit), **Combination** (explicit to explicit), **Internalisation** (explicit to tacit).


> **NOTE: Direct PYQ**
>
> "An individual's shared experience results in ______." Options: systematic knowledge, shared knowledge, **tacit knowledge**, all three. Answer: **tacit knowledge**.
>
> The key phrase is "**individual's experience**". Knowledge gained personally through doing and experiencing, which is hard to articulate, is by definition **tacit**. Systematic and explicit knowledge is what you get from documents and formal training.



### I4.6 Other KM terms


- **Best practices** - **A particular organisation's or industry's most successful solutions or problem-solving methods** - the proven approaches worth reusing. (Note: one DSSSB paper asked this and the official key gave "knowledge management" rather than "best practices". Strictly, the phrase describes **best practices**; be alert if both options appear.)
- **Knowledge asset** - The intellectual resources an organisation owns - patents, documented processes, employee expertise.
- **Knowledge warehouse** - A repository storing organisational knowledge.
- **Organisational learning** - The process by which an organisation as a whole adapts and improves from experience.
- **Organisational memory** - The accumulated stored knowledge of an organisation.
- **Communities of practice** - Informal groups sharing a professional interest, used to spread tacit knowledge.


#### Building a KM system - cost


> **NOTE: Direct PYQ**
>
> "The lowest cost solution to developing a KM system is:" Options: **in-house development**, outsourcing, development by end users, off-the-shelf solution. Answer: **in-house development**.
>
> The reasoning the examiner expects: building it internally uses existing staff and existing infrastructure, avoiding vendor fees, licence costs and consultancy charges. Outsourcing and buying a packaged product both involve paying an external party.



### I4.7 Qualitative and quantitative measures


- **Quantitative** - Measurable in numbers: revenue, response time, number of users, infrastructure count.
- **Qualitative** - Descriptive, subjective, hard to put a number on: **value**, satisfaction, morale, brand reputation, culture, trust.


> **NOTE: Direct PYQ**
>
> "Which qualitative statistic is difficult to quantify precisely?" Options: Model, Infrastructure, **Value**, Decision making. Answer: **Value**.
>
> Reasoning: "value" is inherently subjective - the value a knowledge system delivers depends on perception, context and long-term effects, so it resists precise measurement. Infrastructure can be counted, models can be specified, and decision-making can be measured through outcomes and cycle times.

