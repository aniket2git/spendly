
---

# PART 9 - Software Engineering, Graphics, MIS and Emerging Technology

> *Weightage: 8 to 18 marks combined. Chapter 9.4 on emerging technology is the one place where I am preparing you for a paper that may not look like the last one.*



## 9.1 Software Engineering



> **WEIGHTAGE: 3-5 marks in DSSSB, 3-6 expected | SDLC models and coupling/cohesion are near-certain | Priority MEDIUM-HIGH**



### 9.1.1 Questions



**Q. [PYQ] ______ activities are at the very core of project completion work tasks, whereas ______ activities are not mandatory.**

- (a) Requirements, arbitrary
- (b) Framework, umbrella
- (c) **Functional, non-functional  <-- CORRECT**
- (d) Non-functional, functional

> **Why:** **Functional** requirements define what the software must DO - without them the project is incomplete. **Non-functional** requirements are quality attributes (performance, security, usability). Do not confuse with the other pair: **framework** activities are the main phases, **umbrella** activities run across the whole project (risk management, quality assurance, configuration management).



**Q. [PYQ] The ______ design is a high-abstraction version of a system, followed by ______ design that breaks the concept into less-abstracted sub-systems, and later the ______ design showcases the implementation at module level.**

- (a) detailed, system, architectural
- (b) detailed, architectural, system
- (c) architectural, detailed, system
- (d) **system, architectural, detailed  <-- CORRECT**

> **Why:** Always most abstract to most concrete: **System, Architectural, Detailed.** You picture the whole *system*, draw its *architecture*, then fill in the *details*.



**Q. [PYQ] In building software, ______ should preferably be lower and ______ is preferred to be on the higher side.**

- (a) inheritance from parent class, dependency with peer classes
- (b) aggregation with peer components, composition among classes
- (c) none of the given answer
- (d) **coupling among components, cohesion in bonding components  <-- CORRECT**

> **Why:** **LOW coupling, HIGH cohesion** - the single most important design maxim. Low coupling means a change in one module does not ripple outward; high cohesion means each module has one clear responsibility.



**Q. [EXPECTED] [TRAP] Cohesion refers to:**

- (a) interdependence between modules
- (b) **how strongly the elements within a single module belong together  <-- CORRECT**
- (c) the number of modules
- (d) the depth of inheritance

> **Why:** **Coupling is BETWEEN modules; cohesion is WITHIN one module.** Best cohesion is **functional**; worst is **coincidental**. Best coupling is **data/message**; worst is **content**.



**Q. [PYQ] [TRAP] Within software engineering, which prescriptive model is INCOMPATIBLE with circumstances in which the requirements alter throughout development?**

- (a) **Linear models  <-- CORRECT**
- (b) Evolutionary models
- (c) Agile models
- (d) Incremental models

> **Why:** "Linear model" = **Waterfall**. Each phase is frozen once complete, so a change discovered during coding cannot flow back into design. Evolutionary, agile and incremental models are all built to absorb change.



**Q. [PYQ] [TRAP] Which of the following is NOT true about the Waterfall model?**

- (a) Long duration
- (b) **High cost  <-- CORRECT**
- (c) High-risk involvement
- (d) Low cost

> **Why:** Waterfall is described as a **low-cost** model - no prototyping, no repeated risk analysis, minimal customer interaction. Its genuine drawbacks are long duration, high risk and total rigidity. Note the option list contains both "high cost" and "low cost", signalling which is tested.



**Q. [PYQ] Which of the following is NOT a phase of the RAD model?**

- (a) **Development modelling  <-- CORRECT**
- (b) Business modelling
- (c) Process modelling
- (d) Data modelling

> **Why:** RAD phases: **Business modelling, Data modelling, Process modelling, Application Generation, Testing and Turnover.** "Development modelling" is invented.



**Q. [EXPECTED] [TRAP] Which SDLC model explicitly includes risk analysis in every iteration?**

- (a) Waterfall
- (b) RAD
- (c) **Spiral  <-- CORRECT**
- (d) V-Model

> **Why:** The **Spiral model** (Barry Boehm) has four quadrants per loop: planning, **risk analysis**, engineering and evaluation. It suits large, expensive, high-risk projects. The **V-Model** pairs each development phase with a matching test phase.



**Q. [EXPECTED] Which model is most appropriate when the customer cannot clearly state the requirements?**

- (a) Waterfall
- (b) V-Model
- (c) **Prototype model  <-- CORRECT**
- (d) Big Bang

> **Why:** A quick working mock-up is built, shown to the user, and refined from their reaction - the fastest way to surface requirements the user could not articulate in the abstract.



**Q. [EXPECTED] In Agile, a short fixed-length iteration producing a shippable increment is called a:**

- (a) phase
- (b) milestone
- (c) **sprint  <-- CORRECT**
- (d) baseline

> **Why:** A sprint is typically 2-4 weeks. Scrum roles: **Product Owner** (owns the backlog), **Scrum Master** (facilitator), **Development Team**. Agile values working software over documentation and welcomes changing requirements.



**Q. [PYQ] CMM stands for:**

- (a) Cognitive Modularity Model
- (b) Capability Modularity Model
- (c) Cognitive Measurable Model
- (d) **Capability Maturity Model  <-- CORRECT**

> **Why:** Both words matter: **Capability** (what the organisation can do) and **Maturity** (how disciplined its process is). Levels: **Initial, Repeatable, Defined, Managed, Optimising** - "**I R**eally **D**o **M**y **O**wn work."



**Q. [EXPECTED] [NUMERICAL] At which CMM level is the process quantitatively measured and statistically controlled?**

- (a) Level 2
- (b) Level 3
- (c) **Level 4  <-- CORRECT**
- (d) Level 5

> **Why:** **Level 4 = Managed (quantitatively managed)** - measurement and statistical control. **Level 5 = Optimising** adds continuous improvement and defect prevention.



**Q. [EXPECTED] [TRAP] Which type of testing requires knowledge of the internal code structure?**

- (a) Black box testing
- (b) **White box testing  <-- CORRECT**
- (c) Acceptance testing
- (d) Beta testing

> **Why:** **White box** (structural/glass box) examines internal logic - statement, branch and path coverage, cyclomatic complexity. **Black box** (functional) tests only inputs and outputs using equivalence partitioning and boundary value analysis.



**Q. [EXPECTED] [TRAP] Beta testing is performed:**

- (a) by developers at the development site
- (b) **by real users at the customer's site  <-- CORRECT**
- (c) only by the QA team
- (d) before unit testing

> **Why:** **Alpha testing** = at the developer's site by internal staff. **Beta testing** = at the customer's site by real users. Both are forms of **acceptance testing**.



**Q. [EXPECTED] Re-running previously passed tests after a code change is called:**

- (a) Unit testing
- (b) Smoke testing
- (c) **Regression testing  <-- CORRECT**
- (d) Stress testing

> **Why:** Regression testing confirms that a change has not broken something that used to work.



**Q. [EXPECTED] [NUMERICAL] If a control flow graph has 12 edges and 9 nodes, the cyclomatic complexity is:**

- (a) 3
- (b) 4
- (c) **5  <-- CORRECT**
- (d) 21

> **Why:** **V(G) = E - N + 2** = 12 - 9 + 2 = **5**. It equals the number of independent paths (and also decision points + 1), giving the minimum test cases for branch coverage.



**Q. [EXPECTED] [TRAP] Verification answers which question?**

- (a) Are we building the right product?
- (b) **Are we building the product right?  <-- CORRECT**
- (c) Will the customer accept it?
- (d) Is it fast enough?

> **Why:** **Verification** = conformance to specification, usually **without executing** the code (reviews, walkthroughs, inspections). **Validation** = does it meet the user's actual need, usually **by executing** it.



**Q. [PYQ] Which of the following is the easiest to be transformed into a computer program?**

- (a) **Pseudo-code  <-- CORRECT**
- (b) Algorithm
- (c) Flowchart
- (d) None of the above

> **Why:** Pseudo-code already uses programming constructs (IF, WHILE, assignment) in a code-like layout, so conversion is nearly line-by-line. A plain-English algorithm is more abstract; a flowchart is graphical.



**Q. [PYQ] Program links with other parts of the program in a flowchart are represented by ________.**

- (a) rectangles
- (b) **circles  <-- CORRECT**
- (c) trapezoids
- (d) rhombuses

> **Why:** The **connector** symbol is a circle, used to join parts of a flowchart across pages. **Rectangle** = processing, **diamond/rhombus** = decision, **parallelogram** = input/output, **oval** = start/stop.



**Q. [EXPECTED] COCOMO is used for:**

- (a) testing
- (b) **effort and cost estimation  <-- CORRECT**
- (c) configuration management
- (d) requirement gathering

> **Why:** **COnstructive COst MOdel** (Boehm) estimates effort in person-months from size in KLOC. Its three modes are **Organic, Semi-detached and Embedded**. The alternative, language-independent technique is **Function Point analysis**.



**Q. [EXPECTED] The longest path through a PERT network, which determines the minimum project duration, is called the:**

- (a) slack path
- (b) **critical path  <-- CORRECT**
- (c) Gantt path
- (d) baseline

> **Why:** Any delay on the **critical path** delays the whole project. A **Gantt chart** shows tasks against a calendar; **PERT** shows dependencies as a network.



## 9.2 Computer Graphics and Multimedia



> **WEIGHTAGE: 2-4 marks in DSSSB | Algorithms and projections recur | Priority MEDIUM**



### 9.2.1 Questions



**Q. [PYQ] In order to move objects in computer graphics that generate animation effects, which of the following is necessary?**

- (a) **Various transformation operations  <-- CORRECT**
- (b) Line rasterisation sequencing
- (c) Phong model of lighting
- (d) Eigen value computations

> **Why:** Motion is repeated **translation, rotation and scaling** between frames. Rasterisation draws a line onto pixels; the Phong model shades surfaces.



**Q. [EXPECTED] [TRAP] Why are homogeneous coordinates used in 2D transformations?**

- (a) To reduce memory
- (b) **So that translation can also be expressed as matrix multiplication  <-- CORRECT**
- (c) To support colour
- (d) To speed up rasterisation

> **Why:** Scaling and rotation are naturally multiplicative, but translation is additive. Writing a point as (x, y, **1**) makes translation multiplicative too, so several transformations can be **concatenated into a single composite matrix**.



**Q. [PYQ] Which of the following is a clipping algorithm?**

- (a) Simple DDA
- (b) **Liang Barsky's algorithm  <-- CORRECT**
- (c) Bresenham's algorithm
- (d) Mid-point Algorithm

> **Why:** **DDA** and **Bresenham** draw lines; **mid-point** draws circles. **Liang-Barsky** and **Cohen-Sutherland** clip lines; **Sutherland-Hodgman** clips polygons.



**Q. [EXPECTED] [TRAP] Bresenham's line algorithm is preferred over DDA because it:**

- (a) draws thicker lines
- (b) **uses only integer arithmetic, making it faster and free of round-off error  <-- CORRECT**
- (c) supports colour
- (d) works in 3D

> **Why:** DDA uses **floating-point** addition and rounding, which is slower and accumulates error. Bresenham uses an integer decision parameter with only addition, subtraction and bit shifts.



**Q. [PYQ] [TRAP] ______ and ______ views cannot be framed together for rendering a computer visual appropriately.**

- (a) **Orthogonal projection, horizontal view  <-- CORRECT**
- (b) Vertical view, rear projection
- (c) Front-side, rear-side
- (d) Parallel projection, perspective projection

> **Why:** Orthographic projection uses projectors **perpendicular** to the view plane, which conflicts with simultaneously presenting a horizontal viewing direction in the same frame. Note that "parallel projection, perspective projection" is also a genuinely incompatible pair in principle - reason from **which two views demand contradictory projector geometry**.



**Q. [EXPECTED] In which projection do distant objects appear smaller?**

- (a) Orthographic
- (b) Oblique
- (c) **Perspective  <-- CORRECT**
- (d) Isometric

> **Why:** **Perspective** projectors converge at a centre of projection, producing vanishing points and realism - like the eye or a camera. **Parallel/orthographic** projection preserves true dimensions and is used for engineering drawings.



**Q. [PYQ] [TRAP] Which of these is NOT a parameter upon which the influence of lighting is based?**

- (a) Light Source
- (b) Position of Observer
- (c) **Rendering Algorithm  <-- CORRECT**
- (d) Surface

> **Why:** The physical inputs to an illumination calculation are the **light source**, the **surface** properties and the **observer's position** (needed for specular highlights). The **rendering algorithm** is the *method of computing* the image, not a parameter of the lighting - the recipe is not an ingredient.



**Q. [EXPECTED] Which shading method interpolates the surface normal and computes lighting per pixel?**

- (a) Flat shading
- (b) Gouraud shading
- (c) **Phong shading  <-- CORRECT**
- (d) Constant shading

> **Why:** **Gouraud** interpolates *intensity* computed at the vertices - fast but can miss highlights inside a polygon. **Phong** interpolates the *normal* and lights each pixel - slower but far better highlights.



**Q. [EXPECTED] Which hidden surface removal technique stores a depth value for every pixel?**

- (a) Back-face detection
- (b) Painter's algorithm
- (c) **Z-buffer algorithm  <-- CORRECT**
- (d) Ray tracing

> **Why:** The **Z-buffer (depth buffer)** keeps the nearest surface per pixel - simple and universally used in hardware. **Ray tracing** is far more realistic (reflection, refraction, shadows) but computationally expensive.



**Q. [PYQ] The construction of computer-generated simulations that simulate real-world activities using interactive graphics software and hardware is called:**

- (a) **virtual reality systems  <-- CORRECT**
- (b) hybrid systems
- (c) genetic algorithms
- (d) fuzzy neural networks

> **Why:** The other three are **Artificial Intelligence** techniques. VR's "three I's" are **Immersion, Interaction, Imagination**; **AR** overlays content on the real world rather than replacing it.



**Q. [PYQ] Which tool is used to adjust the brightness and contrast of an image in Adobe Photoshop?**

- (a) Healing brush tool
- (b) Paint bucket tool
- (c) **Adjustments panel  <-- CORRECT**
- (d) Selection tool

> **Why:** The **Adjustments panel** holds brightness/contrast, levels, curves, hue/saturation. The **healing brush** repairs blemishes; the **paint bucket** fills areas.



**Q. [PYQ] Which of the following formats is commonly used for exporting images for the web?**

- (a) **PNG  <-- CORRECT**
- (b) PSD
- (c) BMP
- (d) TIFF

> **Why:** **PNG** = lossless with transparency, ideal for logos and sharp-edged graphics. **PSD** is Photoshop's editable working file; **BMP** is uncompressed; **TIFF** is for print/archival - all far too large for the web. For photographs, **JPEG** is preferred.



**Q. [EXPECTED] [TRAP] Which image format scales to any size without loss of quality?**

- (a) JPEG
- (b) PNG
- (c) GIF
- (d) **SVG  <-- CORRECT**

> **Why:** **SVG** is **vector** - stored as mathematical descriptions of shapes. JPEG, PNG, GIF and BMP are **raster** (a fixed pixel grid) and blur when enlarged.



**Q. [PYQ] What is the main function of the 'cutting' tool in image editing?**

- (a) **To remove parts of the image  <-- CORRECT**
- (b) To change the image resolution
- (c) To apply color effects
- (d) To resize the image

> **Why:** Cutting/cropping removes content; it does not resample or recolour.



## 9.3 Management Information Systems and Knowledge Management



> **WEIGHTAGE: 3-6 marks in DSSSB | Appeared in all three papers supplied | Priority MEDIUM-HIGH**



### 9.3.1 Questions



**Q. [PYQ] ______ is a set of interrelated components that collect (or retrieve), process, store and distribute information to support decision-making and control in an organisation.**

- (a) An information technology
- (b) Mini model of a processed system
- (c) Max model of a processed system
- (d) **An information system  <-- CORRECT**

> **Why:** **IT is the technology; an information SYSTEM is technology + people + processes** working toward an organisational purpose. The distractor "information technology" is deliberately close.



**Q. [PYQ] In a management information system, what is/are the formal social unit that is/are devoted to attaining specified goals?**

- (a) Organisation, management and marketing
- (b) **Organisation  <-- CORRECT**
- (c) Management
- (d) Marketing

> **Why:** An **organisation** is the formal social structure that takes in resources and produces outputs toward stated goals. **Management** is a *function*; **marketing** is an *activity*. Only organisation is the social *unit*.



**Q. [PYQ] DSS is a computer program application used to improve a company's ______ capabilities.**

- (a) **decision-making capabilities  <-- CORRECT**
- (b) marketing capabilities
- (c) delegation capabilities
- (d) resources utilisation capabilities

> **Why:** The name states it: **D**ecision **S**upport **S**ystem. It analyses semi-structured problems with models and what-if analysis.



**Q. [PYQ] Which of the following systems comprises word processing, electronic filing, electronic mail, message switching, data storage and data and voice communication?**

- (a) Executive Support Systems
- (b) **Office Automation Systems  <-- CORRECT**
- (c) Customer Relationship Management
- (d) Decision Support Systems

> **Why:** Every item listed is a routine **office** function. An ESS gives executives strategic dashboards; a DSS runs analytical models; CRM manages customers.



**Q. [EXPECTED] [TRAP] Which system answers "what happened?" with routine, fixed-format reports?**

- (a) TPS
- (b) **MIS  <-- CORRECT**
- (c) DSS
- (d) ESS

> **Why:** **TPS** records raw transactions. **MIS** summarises them into routine reports - "what happened?". **DSS** answers "what if?" and "what is best?". **ESS** answers strategic questions with highly summarised internal and external data.



**Q. [PYQ] The set of processes developed in an organisation to create, gather, store, transfer and apply knowledge best describes:**

- (a) **knowledge management  <-- CORRECT**
- (b) organisational learnings
- (c) knowledge asset
- (d) organisational memory

> **Why:** A **knowledge asset** is the thing being managed; **organisational memory** is the store; **organisational learning** is the outcome. Only **KM** is the set of processes.



**Q. [PYQ] Which of the following is NOT the purpose of knowledge management system?**

- (a) Driving strategy
- (b) Integration
- (c) Sharing of knowledge
- (d) **Portability  <-- CORRECT**

> **Why:** **Portability** is a software quality attribute (running on different platforms), unrelated to KM goals.



**Q. [PYQ] An individual's shared experience results in __________.**

- (a) systematic knowledge
- (b) shared knowledge
- (c) **tacit knowledge  <-- CORRECT**
- (d) tacit, systematic and shared knowledge

> **Why:** **Tacit** knowledge is personal, experience-based and hard to write down - knowing how to ride a bicycle, or an experienced teacher's classroom instinct. **Explicit** knowledge is codified in manuals and databases.



**Q. [EXPECTED] [TRAP] In the SECI model, converting tacit knowledge into explicit knowledge is called:**

- (a) Socialisation
- (b) **Externalisation  <-- CORRECT**
- (c) Combination
- (d) Internalisation

> **Why:** Nonaka and Takeuchi's four modes: **Socialisation** (tacit to tacit), **Externalisation** (tacit to explicit), **Combination** (explicit to explicit), **Internalisation** (explicit to tacit).



**Q. [PYQ] The lowest cost solution to developing a KM system is:**

- (a) **in-house development  <-- CORRECT**
- (b) outsourcing
- (c) development by end users
- (d) off-the-shelf solution

> **Why:** Building internally uses existing staff and infrastructure, avoiding vendor fees, licences and consultancy charges.



**Q. [PYQ] Which qualitative statistic is difficult to quantify precisely?**

- (a) Model
- (b) Infrastructure
- (c) **Value  <-- CORRECT**
- (d) Decision making

> **Why:** **Value** is inherently subjective and context-dependent, so it resists precise measurement. Infrastructure can be counted; decision-making can be measured through outcomes and cycle times.



## 9.4 Emerging Technology - AI, Cloud, IoT and Cyber Security



> **WEIGHTAGE: 0-2 marks observed in DSSSB | 2-6 and RISING across KVS / NVS / EMRS | Priority MEDIUM-HIGH**



> **NOTE: Why this chapter exists**
>
> The three DSSSB papers you shared barely touched these topics. But newer papers across all these bodies are adding them, and **EMRS already has an explicit ICT and cyber-security component** in its published syllabus. Recent school curricula (CBSE Class XI-XII Computer Science and Informatics Practices) also now include Python, data handling and cyber safety - and TGT papers tend to follow the school syllabus they are recruiting teachers for.
>
> This is the one chapter that prepares you for the paper that may **not** look like the last one. Treat it as insurance: a single pass is enough, but do not skip it.



### 9.4.1 Questions



**Q. [EXPECTED] Machine learning in which the model is trained on labelled input-output pairs is called:**

- (a) Unsupervised learning
- (b) **Supervised learning  <-- CORRECT**
- (c) Reinforcement learning
- (d) Deep learning

> **Why:** **Supervised** = labelled data (classification, regression). **Unsupervised** = unlabelled, finds structure (clustering, association). **Reinforcement** = learning from rewards and penalties through interaction.



**Q. [EXPECTED] [TRAP] Which of the following is an unsupervised learning technique?**

- (a) Linear regression
- (b) Decision tree classification
- (c) **K-means clustering  <-- CORRECT**
- (d) Logistic regression

> **Why:** **K-means clustering** groups unlabelled data. The other three all need labelled training data.



**Q. [EXPECTED] The Turing Test is used to evaluate:**

- (a) processing speed
- (b) **whether a machine's behaviour is indistinguishable from a human's  <-- CORRECT**
- (c) memory capacity
- (d) network latency

> **Why:** Proposed by **Alan Turing** (1950), who is regarded as the father of theoretical computer science and AI.



**Q. [EXPECTED] Which of the following is NOT a characteristic of cloud computing?**

- (a) On-demand self-service
- (b) Broad network access
- (c) Resource pooling
- (d) **Permanent local storage on the user's device  <-- CORRECT**

> **Why:** The NIST characteristics are on-demand self-service, broad network access, resource pooling, **rapid elasticity** and **measured service**. Cloud deliberately moves storage *off* the local device.



**Q. [EXPECTED] [TRAP] In which cloud service model does the provider supply ready-to-use application software over the internet?**

- (a) IaaS
- (b) PaaS
- (c) **SaaS  <-- CORRECT**
- (d) DaaS

> **Why:** **IaaS** gives raw infrastructure (virtual machines, storage - e.g. AWS EC2). **PaaS** gives a development platform (e.g. Google App Engine). **SaaS** gives finished applications (Gmail, Google Docs, Salesforce). Memorise by what you receive: Infrastructure, Platform, Software.



**Q. [EXPECTED] IoT stands for:**

- (a) Internet of Technology
- (b) **Internet of Things  <-- CORRECT**
- (c) Integration of Things
- (d) Internet over Telephony

> **Why:** **IoT** = everyday physical objects fitted with sensors and network connectivity - smart meters, wearables, connected appliances. Key concerns are **security** and **data privacy**, because such devices are often weakly protected.



**Q. [EXPECTED] A blockchain is best described as:**

- (a) a centralised database
- (b) **a distributed, append-only ledger where blocks are linked by cryptographic hashes  <-- CORRECT**
- (c) a type of firewall
- (d) a cloud storage service

> **Why:** Each block stores the **hash of the previous block**, so altering any past block invalidates every block after it - that is the source of tamper resistance.



**Q. [EXPECTED] [TRAP] Which of the following best defines phishing?**

- (a) Flooding a server with traffic
- (b) **Fraudulent messages or websites that trick users into revealing credentials  <-- CORRECT**
- (c) Encrypting a victim's files for ransom
- (d) Intercepting traffic between two parties

> **Why:** The distractors define **DoS**, **ransomware** and a **man-in-the-middle** attack respectively. Phishing exploits the *human*, not the software - which is why user awareness is the main defence.



**Q. [EXPECTED] Two-factor authentication improves security because it requires:**

- (a) two passwords
- (b) **two different categories of evidence, such as something you know plus something you have  <-- CORRECT**
- (c) two user accounts
- (d) encryption twice

> **Why:** The three authentication factors are **something you know** (password), **something you have** (phone, token) and **something you are** (biometric). Combining categories is what makes 2FA strong.



**Q. [EXPECTED] Which Indian law gives legal recognition to electronic records and digital signatures?**

- (a) RTI Act 2005
- (b) **IT Act 2000  <-- CORRECT**
- (c) Companies Act 2013
- (d) RPwD Act 2016

> **Why:** The **Information Technology Act, 2000** also defines cybercrimes and penalties. Useful for both the Computer Science and General Awareness sections.



**Q. [EXPECTED] Which of the following is a strong password practice?**

- (a) Using your date of birth
- (b) Reusing one password everywhere
- (c) **Using a long passphrase with mixed character types, unique per site  <-- CORRECT**
- (d) Sharing it with a trusted colleague

> **Why:** Length matters more than complexity. Related concepts worth knowing for ICT sections: **password managers, OTP, biometric authentication, VPN, firewall, antivirus, regular patching**.



**Q. [EXPECTED] [TRAP] What is the primary purpose of a firewall?**

- (a) To remove viruses from files
- (b) **To filter incoming and outgoing network traffic according to security rules  <-- CORRECT**
- (c) To encrypt stored data
- (d) To back up data

> **Why:** A firewall controls **traffic**; an **antivirus** removes malware; **encryption** protects stored or transmitted data. An **IDS** detects intrusions and an **IPS** blocks them.

