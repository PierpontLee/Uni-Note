## Chapter 1 
### Summary
- Software & within it & attribute of good software 
- Type of Software products
- Why software important
- Types of software applications
- Layered technology 
- Generic Process Framework
- Software process & purpose

### memorization shit
1. Software : product built and supported over long time
    - ==Instructions== : executed provide desired features, etc.
    - ==Data structures== : programs to ==store and manipulate information==
    - ==Documentation== : operation and ==use of program==

2.  Attributes of good software : required function and performance for user
    - ==Maintainability== : changing needs
    - ==Dependability and security== : no damage in system failure, evil users no enter yes
    - ==Efficiency==: responsive, process time, memory utile
    - ==Acceptability== : understandable, usable, compatible
    + ==Reusable==

  

3. Software Development 

    - Set of CS activities in creating, designing, deploying and supporting software by software engineers (build software for users)

  

4. Software products

    - Generic : marketed and sold to any customer (word editing)

    - Customized : commissioned by specific customer to meet their needs (inventory control / management)

  

5. Why is software important?

    - Dependent on software and systems software controlled

  

6. Software Application

    - System software : utilities (compilers, editors, file management)

    - Application software : specific needs

    - Engineering / Scientific software : number crunching

    - Embdedded software : within systems 

    - Product-line software : limited marketplace for mass consumers 

        (word, database, graphic)

    - WebApps : network centric software. web 2.0 supports remote database and business

    - AI : non-numerical solve complex 

  

7. Software engineering : engineering discipline for software production

    - system is all computer, software just software

    - CS for theory fundamentals, SWE development 

  

## Layered Technology 

  

- Quality : continuous process improvement, providing integrity (security)

- Process : base layer binding all layers for development before deadline

    - Generic Process Framework:

        - Communication -> planning -> modeling -> construction -> deployment 

        - Communication : talk with customer for objective, requirements

        - Planning : map for tasks, risks, resources, schedule

        - Modeling : sketch (from communication) for understanding

        - Consturction : coding, testing

        - Deployment : delivery, feedback

- Method : todo software, information of all tasks above (process)

- Tools: self-operating system for process used by one another

  

Software process : adaptable collection of activities to choose appropriately

    - purpose : deliver in time and quality for users

  

### Umbrella Activities

  

Activities by team to maintain process, quality, changes and risks of tasks

  

Process : 

- Software project tracking and control : assess progress plan

- Risk management : assess risk

- Software quality assurance : ensure quality

- Technical reviews : assess work for error

- Measurement : collect progress measure for user

- Software configuration management : manage configuration 

- Reusability management : reuse criteria, mechanism for reusable component

- Work product preparation and production : create work product (models, documentation, logs, forms)

  

----------

  

## Chapter 2 

  

### SDLC Software Development Life Cycle

  

Structured process for high-quality low-cost software in shortest time

  

Goal : produce good software meet customer demands

  

Why important : standardized framework, aiding project scheduling and control with better speed, client relation and risks

  

Process:

- Planning : gathering business requirements from clients

- Analysis : outline scope and requirements of problem and solutions from planning

    - Software requirement specification (SRS) is all requirements to be developed and guideline of next phase

  

- Design : approval before developemnt

    - Software design document (SDD) is system design, language, platform, security, etc. (also plan and vision with flowchart)

    - Prototype visualize product and make changes

    - System flowchart

    - Database design with ERD/DFD

    - Timeline

  

- Implementation / Development

    - Longest, code, work divided in modules with testing

  

- Testing & integration 

    - Tested for requirements phase, perform Software Testing Life Cycle finding bugs & fixes meeting SRS quality

    - Integration : deliver to client for beta testing, additional changes, then final

    - Types

        - Performance 

        - Functional 

        - Security 

        - Unit-testing

        - Usability 

        - Acceptance 

  

- Maintenance 

    - actual problems, agile approach for maintenance futher improvement 

    - SDLC restart for new features,  update

  

### Agile Testing

  

Iterative development methodology to deliver faster

  

Continuously develop where testing and feedback in any stage without waiting to finish  

  

### Testing Approach

  

- Black-box / Behavior testing : 

    - external behavior without internal by tester

    - fastest

    - In system / acceptance testing, called data-driven / functional / closed box

  

- White-box / Logic testing : 

    - software with its internal function

    - slowest 

    - In unit / integration testing, called clear box / non-functional / code based / structural / transparent

    - For algorithm testing

  

### Types of testing

  

- Functional (verifies features) : Unit, integration, system, smoke, interface, regression, beta/acceptance testing

- Non-functional (verfies behaviors) : Performance, load, volume, security, compatibility, installation, recovery, reliability, usability

  

### Verification and Validation

  

Verfication : determine software meet specified requirement 

  

Validation : determine software meet clien't true needs 

  

Scientists (theorems, algorithms, languages), Engineer (application, using tools, techniques), software engineer (multiple domains)

  

---

  

## Chapter 3 

  

### SDLC Models

  

Framework with how phases are organized and executed

  

Why? : clear structure, better communication, controlled development  else error, failure, unorganized, misunderstood requirements

  

Why choose correct? : project cost, time, quality, user satisfaction

  

- Groups:

    - Linear Model (fixed sequence, waterfall)

    - Iterative Model (repeat develop cycle, incremental, spiral)

    - Agile Model (flexible, adaptive, continuous feedback)

  

- Types:

    - Waterfall Model 

    - Incremental Model

    - Spiral Model

    - Agile Model

  

### Waterfall Model

  

- Linear, Simple, Rigid

- One phase to another, no go back

  

- Usage : clear requirements, simple, no frequent changes

  

- Advantage

    - Easy understand, manage

    - Clear structure, documentation

    - For small, simple project

- Limitation

    - Difficult changes

    - Late testing

    - High risk wrong requirements

  

> ex : Government system

  

### Incremental & Iterative

  

Develop system in small parts / repeated cycles. Each increment / cycle add new features, working version. Flexible

  

Incremental : new features, expands

Iterative : improve existing, refines 

  

- Advantage 

    - Early delivery

    - Easier testing and debugging

    - Customer feedback

  

- Limitation: 

    - Need planning

    - Difficult integration

  

### Spiral Model

  

Combines iterative and risk management, happens in cycles/spiral 

  

- Usage : large systems, high risks

    - Identify early risks

    - Reduce risks before dev

  

- Advantage: 

    - Strong risk management

    - Large and complex

  

- Limitations:

    - Expensive

    - Complex to manage

    - Expertise

  

> ex: Banking systems

  

### Agile Model

  

Flexible, fast and iterative model in short cycles / sprints with continuous testing

  

Agile principles:

- Customer collaboration

- Continuous feedback

- Adapt to changes

  

- Usage: changing requirements, fast-paced

  

> ex: Mobile apps

  

- Advantage

    - Fast delivery

    - changing requirements

    - Continuous feedback

- Limitation

    - experience

    - Hard predict cost and time 

    - Less docs

  

----------

## Chapter 9

  

### Architectural Design 

  

How software organized and designing structure, components and relationships

  

> Critical link between design and requirement

  

### Representing Architectural Design  

  

- Block / Box-line Diagram: 

    - Abstract only for communicating / planning

    - Depends on use of architectural models

    - Lack semantic (type of relationship, properties)

  

Architectural Model : system as communicating components

  

> Early agile process for designing architecture, refactoring system architecture 

are expensive 

  

### Architectural abstraction

  

- Small: individual programs into components

- Large: complex enterprise system including other systems

  

- Advantage of explicit architecture:

    - Stakeholder communication 

        - To facilitate discussion about system design

        - To document complete architecture 

    - System analysis (meet requirements or no)

        - Design affects the characteristic of the system

        (except for different types, same design process)

    - Large-scale reuse 

        - Same domain, similar architecture (product lines, variants by patterns / styles) 

  

- Architecture characteristics:

    - Performance 

    - Security 

    - Safety

    - Availability 

    - Maintainability

  

### Architectural Views

  

> Each model for each view, architectures can be documentted from these views

  

#### 4 + 1 view model

  

- Logical view : abstractions in system (object / classes)

- Process view : system interacting processess at run-time

- Development view : system decomposed for development

- Physical view : hardware and software distributed

- Scenarios 

  

### Representing Architectural View 

  

- Unified Modeling Language (UML) is appropriate but doens't provide correct abstractions for high-level systems

  

- Architectural Description Languages (ADLs) but not widely used

  

### Architectural Patterns

  

Patterns : Representing, sharing and reusing knowledge 

  

Architectural pattern : description of tested design practise , reusing generic system architectures 

  

Using graphical or tabular descriptions 

  

#### Model-View-Controller (MVC)

  

- Description : separates presentation and interaction.

    - System divided into Model, View, and Controller

        - Model : manage data and operations 

        - View : how data presented to user 

        - Controller : manage user interaction and pass to View & Model

  

- Usage : multiple view and interact with data or unknown future requiremetns

  

- Advantage : 

    - data independent of representation vice versa

    - support presentation data in different ways, change respresent shows all

  

- Disadvantage : 

    - additional code and complexity 

  

- [ ] Check graph

    - Model, View, Controller 

  

#### Layered Architecture 

  

- Description : organize system into layers by associated function  

    - provide service above as lowest layer as core service

  

- Advantages : 

    - allow modularity or replacement of layers 

    - Provide redundant service (authentication) in each layers for system dependability

  

- Disadvantages : 

    - difficult for clean separation

    - high layer may have to interact with lower

    - performance issue for processing each layer

  

- Usage : inteface sub-systems

  

- [ ] Check graph

    - UI, UI management / authentication / authorization, application / utilities, system support (OS, database) 

  

#### Repository Architecture 

  

- Description : central repo for all system components (only interact by repo) (data sharing)

    - Ways sub-systems exchange data:

        - central data at database and accessed by all 

        - each sub-system have its database and pass data to others

  

- Usage : large information to be stored or data-driven systems triggering tools / actions from repo

  

- Advantages : 

    - independent components 

    - data managed consistently in one place

- Disadvantages : 

    - single point of failure 

    - inefficiency in communication via repo

    - difficult to distribute repo 

  

- [ ] Check graph

    - parent node to all components 

  

#### Client-server architecture 

  

- Description : Functionality into services, each service delivered from a server

    - Distributed model (data, process distributed to components)

    - Can implement on single computer

    - Servers : provide specific services 

    - Clients : Users of services and access servers to use / call them services

    - Network : allows lients to access servers

  

- Usage : shared database access from multiple locations or variable system load (dividing tasks to servers)

  

- Advantages : 

    - Servers distributed over network

    - Functionality available to all clients 

    - Servers no need to implement all services

  

- Disadvantages : 

    - Each service as single point of failure (DoS, server fail)

    - Unpredicatable performance from network & system

    - Server management problems from different ownerships

  

- [ ] Check graph

    - multiple client <-> internet <-> multiple server 

#### Pipe and Filter Architecture 

  

- Description : organize data processing into processing components (filter) for each data transformation. Data flows (pipe) inbetween filters 

  

- Usage : data processing (batch / transaction) in different stages 

  

- Advantages : 

    - easy to understand 

    - transformation reuse

    - workflow match business process

    - straightforward adding transformations

    - can be sequential or concurrent 

  

- Disadvantages : 

    - data format must be suitable between transformation

    - system overhead in transformations parse input and unparse output

    - no reuse if incompatible data structure 

    - not suitable for interactive systems 

  

- [ ] Check graph

    - data pipeline 

  

### Application Architecture  

  

- Definition : Meet organization need and common architecture in business reflecting requirements, to understand and compare applications in deisgn and reuse

  

- Generic application architecture : to configure and adapted to a system thtat meets specific requirements 

  

- Use of application architecture : 

    - Design starting point / checklist, organizing dev work, assesing reuse, application types guide 

  

- Software architecture graph : input > process (database) > output

  

#### Generic Application Architecture Types 

  

- Data processing 

    - Process data in batches with no interaction

- Transaction processing  

    - Process user request and update database. Async request handled by transaction manager. Remotely access database by users

    - Transaction from users : sequence of operations for a goal (london to paris bitch)

    - I/O processing <-> Application logic <-> Transaction manager <-> Database

- Event processing 

    - Actions on events from system environment

- Language processing 

    - Process and interpret user formal language, carry out instruction within input. Include translator and abstract machine to execute output language

  

> Widely used are transaction (e-commerce & reservation system) and language (compilers, interpreters)

  

  

### Transaction Processing Systems 

  

#### Information Systems Architecture 

  

- Definition : Generic architecture that can be layered 

- Transaction-based systems as interactions, involving database interaction

- Layered Information System Architecture:

    - User interface 

    - User communication 

    - Information Retrieval 

    - System database 

  

#### Web-based Information Systems

  

- Web-based system in UI implemented with web browser. 

- ex: E-commerce system as internet-based orders 

  

#### Server Implementation

  

- Multi-tier client server/architectures systems

- Web server for all user comms and UI with web browser

- Application server : application-specific logic with info storage, retrieval

- Database server : moves information between database and transaction management 

  

### Langauge Processing Systems 

  

Language as input and output other representation

  

- Interpreter to act on instructions from processing input 

- Used in describing algorithm / data to solve problem

    - ex: tools descriptions, rules

  

- [ ] graph (kinda useless)

    - for ide: translator -> instructions -> interpreter -> 

  

#### Compiler Components

  

- Lexical analyzer : input language token and output internal form

- Symbol table : info about entities in text 

- Syntax analyzer : check syntax using syntax tree and symbol table

- Syntax tree : internal program structure 

  

- [ ] graph (do i need to even study this???)

    - for ide: translator -> instructions -> interpreter ->



# --- Tutorial ---
# Chap 1
1. What is meant by software development
Computer Science activities that are dedicated to the **==process==** of ==creating, designing, deploying,==
==**and supporting software==.**

2. Software consists of three main components.
	- List the THREE components and Briefly explain ONE of them 
- **Instruction.**
- **Data Structures.**
- **Documentation: Describes the operation and use of the programs.**

3. `A company has deployed a new inventory management system. However, staff often enter incorrect data, and there is no proper way to track or correct mistakes. As a result, reports generated by the system are unreliable.`
	Which TWO software components are likely missing or weak? Explain your answer.
- **Data structures = The data structure components are weak because the system does not**
**store an organized record of errors or changes, making it hard to track, manage, and**
**correct mistakes, leading to unreliable reports. For example: missing error log,**
**transaction history and audit trails which record details who, what, and when the**
**modification being made.**
- **Instruction = Staff often enter incorrect data because the data validation function is not**
**working properly. So the system just accepts any input given by the staff without**
**checking the requirements of the data, example Age data with requirement of integer and**
**above 0, since the validation failed the staff can enter another type of data or out of range**
**and the system still accepts it.**
4. List TWO activities involved in software engineering
- **Communication: communicate with customers to know the actual demand, understand the**
**objectives and gather requirements.**
- **Construction: Coding and testing the problem.**

5. Who is a software engineer?
**Individuals who apply engineering principles and knowledge of programming languages to**
**build software solutions for end users.**

6. `A company develops a mobile app, but it frequently crashes and is not updated after release.`
	Which TWO software engineering activities are not properly done? Explain your answer. 
- **The app frequently crashes, which indicates that the software was not properly tested during**
**the development stage. During testing, bugs or defects should be identified and fixed before the**
**system is released.**
- **The app is not updated after release, which shows that maintenance activities are not being performed. After deployment, the system should be continuously improved and updated to fix problems and add new features.**

7. `A school wants to create an online system for students to register subjects. The software engineer immediately starts coding without discussing with users or planning the system design. Later, many functions do not meet the school’s needs.`
	- Which software engineering activity was ignored at the beginning?
**Communication was ignored. Because the software engineer immediately starts to code**
**without discussing with the customers**
	- Why is this activity important?
**In order to determine the true demand, comprehend the goals, and collect needs,**
**communication with the client is crucial**

8. What is a customized product? Give TWO examples.
**Software that is commissioned by a particular client to satisfy their unique requirements is known as a customized product. Examples of customer software development include inventory management and control systems**

9. State ONE difference between generic and customized products
**While custom items are commissioned by a particular customer, generic products are**
**stand-alone systems advertised and sold to any customer.**

10. `A supermarket hires a software team to build a system that tracks their stock, sales, and suppliers based on their business process.`
	Identify the type of software product and explain your answer. 
**Since the supermarket employs a software team to create a system based on their own business process, the software type is a specialized product that is uniquely commissioned by the supermarket.**

11. What is meant by quality in software engineering?
**Software quality is a principle of ongoing process improvement.**

12. State ONE feature of quality mentioned.
Integrity

13. Describe Process, Method and Tools.
- **Process: foundation or base layer of software engineering, connects all the layers and makes it possible to produce software on schedule or ahead of schedule.**
- **Method: offers technical instructions for creating software. Communication, requirement analysis, design modeling, program building, testing, and support are just a few of the**
**numerous jobs it includes.**
- **Tools: give procedures and approaches their own operating system; they are integrated, meaning that data produced by one tool can be utilized by another.**

14. `A system allows anyone to access sensitive user data without login.`
	Which aspect of software engineering is lacking? What should be improved?
**Reliability and security are the areas of software engineering that are deficient. To prevent malicious users from accessing or harming the system, the software's security should be strengthened. This is accomplished by making sure that only authorized users with the correct login can access data.**

15. `A software project is delayed because the team has no clear workflow and uses separate tools that cannot share data.`
	Which TWO elements are weak in this situation? Explain your answer. 
- **The approach is inadequate because it lacks a clear workflow, despite the fact that it is meant to offer a technical how-to for developing software, which includes a variety of responsibilities like communication, requirement analysis, design modeling, program construction, testing, and support.**
- **The inability of the many tools to share data makes them weak. Since tools are meant to be integrated, data produced by one tool can be utilized by another. Sensitive user information can be accessed by anybody without logging in. Because the team employs disparate tools that are unable to share data and lacks a clear workflow, a software project is delayed**

16. What are umbrella activities in software engineering?
**A software development team uses umbrella activities, which are set procedures, to maintain the quality, risks, modifications, and progress of finished development projects.**

17. Describe:
	- Risk management
	- Software project tracking and control
	- Technical reviews
- **Risk management: evaluates risks that could have an impact on the quality and result.**
- **Software project tracking and control: evaluate progress in relation to the plan and take**
**steps to keep the timeline on track.**
- **Technical reviews evaluate work products to find and fix mistakes before moving on to**
**the next task.**

18. `A software team realizes too late that the project cannot be completed on time because no one monitored progress earlier.`
	Which umbrella activity was not properly applied? Explain your answer. Software project tracking and control
**Tracking and controlling software projects was not done correctly. The goal of software project tracking and control is to evaluate progress in relation to the plan and take appropriate action to keep the schedule on track.**

# Chap 2
1. Define SDLC and state its main goal. [4m]
- **SDLC (Software Development Life Cycle) is a structured process that enables the production of high-quality, low-cost software, in the shortest possible production time.**
- **The goal of the SCDLC is to produce superior software that meets and exceeds all customer expectations and demands.**

2. List all SIX (6) stages in SDLC. [6m]
- **Planning : Gathering business requirements from client or stakeholders.**
- **Analysis : Outline the scope of the problem and identify solutions.**
- **Design : Defining overall system architecture lie system flow using flowchart, database design using ERD, timeline, and prototype to get final approval before start development.**
- **Implementation : Developers will focus on producing the code, the actual development starts and the product is built.**
- **Testing and integration : After the code is developed it is tested against the requirements to make sure that the product is actually solving the needs addressed and gathered during the requirements phase.**
- **Maintenance : Once when the customers start using a developed system then the actual problems come up and need to be solved from time to time.**

3. Explain TWO (2) activities in the Planning phase. [4m]
- **Gathering business requirements from clients or stakeholders.**
- **Gather input from customer, sales department , market survey, and domain experts in the industry.**

4. What is the purpose of the Analysis phase? [3m]
- **Outline the scope of the problem and identify solutions.**

5. What is SRS and why is it important? [4m]
- **SRS (Software requirement specification) : serves the purpose of guideline for the next phase of the model. It's important because SRS consists of all the product requirements to be designed and developed during the project life cycle.**

6. State THREE (3) components included in the Design phase. [3m]
- **System design**
- **Templates**
- **Application security method**

7. Differentiate between Functional and Non-Functional Testing. [2m]
- **Functional testing checks whether the system functions correctly according to the specified requirements and ensures that each feature works as expected.**
- **Non- Functional testing evaluates performance and quality of the system, like speed , security, usability and reliability, to ensure the system works efficiently.**

8. Define Verification and Validation. [2m]
- **Verification is a process of determining if the software is design and developed as per the specified requirement**
- **Validation is the process of checking if the software has met the client true needs and expectations.**

9. A development team creates a document that contains all system requirements before
starting coding
a. What is the document called? [2m]
- **Software Design Document (SDD)**
b. In which phase is it created? [2m]
- **Design**

10. A team builds a prototype of a mobile app to visualize the design before actual
development.
a. Which phase is this? [2m]
- **Design**
b. Why is prototype important? [3m]
- **It gave the team the opportunity to visualize what the product will look like and make changes without having to go through the hassle of rewriting code.**

11. Users test the system after deployment and request improvements.
a. Which phase is involved? [2m]
- **Maintenance**
b. What happens next? [2m]
- **Software Maintenance Process**


12. A team performs testing continuously while developing the system instead of waiting
until coding is complete.
a. What approach is this? [2m]
- **Agile Testing**
b. State ONE advantage [2m]
- **You can impart continuous feedback to the development phase from the start**

13. A system passes all internal tests, but users complain it does not meet their expectations.
a. Which process failed? [2m]
- **Validation**
b. Why? [2m]
- **The system worked according to the code (verified) but it does not meet the user's needs and expectations (not validated).**

14. A system crashes when too many users access it at the same time.
a. What type of testing should be performed?
- **Load Testing**
b. Under which category does it fall?
- **Non-Functional Testing**

Question 16 (12 marks)
A company developed an e-learning system but skipped the Analysis phase to save time.
After deployment, users complain that the system does not meet their needs.
a. Analyse TWO problems caused by skipping the Analysis phase [4 marks]
- **Because the analysis phase focuses on outlining issues and identifying solutions, they were unable to satisfy client expectations.**
- **Lacked the minimal requirements needed to complete the project.**
b. Explain how the Analysis phase could have prevented these issues [4 marks]
- **After outlining the issue and determining a solution, the analysis phase's goal is to create a software requirement specification (SFS) that will serve as a guide for the model's subsequent phase.**
c. Suggest TWO improvements for future projects [4 marks]
- **Make sure they have a clear requirement by not skipping the analytical stage.**
- **Initiate the creation of SRS so that every product requirement has been created and developed for the other project life cycle.**

Question 17 (10 marks)
A system passed all internal testing but failed during user acceptance testing because it did
not meet customer expectations.
a. Identify the issue related to this situation. [2m]
- **The system is solely tested using the white box test, which focuses exclusively on the internal aspects; the black box test, which does not take the system's exterior behavior into account, is ignored.**
b. Analyze TWO causes why this problem occurred [4m]
- **Ignoring the analysis approach since the system didn't satisfy the needs of the customers They were unable to identify what they overlooked because they failed to perform the double check or double validation.**
c. Suggest TWO solutions to avoid this issue [4m]
- **Verify each stage again to ensure that all requirements have been met. Use both the white box and black box testing techniques.**

# Chap 3
1. State THREE main reasons why SDLC (Software Development Life Cycle) is important in software development. [3 marks]
- **SDLC is important because it ensures software is developed in an organized way, quality is maintained, and time and cost are controlled**

2. What is the difference between SDLC and SDLC models? [4 marks]
- **SDLC is the structured process used to develop software systematically through phases like planning and design, while an SDLC model is the specific framework that defines how those phases are organized and executed.**

3. Based on this situation, explain TWO problems caused by not using an SDLC model. [6
marks]
- **Without a model, development becomes unorganized and requirements may be misunderstood, often leading to increased errors or project failure.**

4. State TWO advantages and TWO limitations of the Waterfall model. [4 marks]
- **Advantages: It is easy to understand and manage, and it offers a clear structure and documentation .**
- **Limitations: It is difficult to handle changes once development has started, and testing only happens late in the cycle.**

5. Give TWO reasons why is the Waterfall model suitable for this project? [6 marks]
- **Waterfall is suitable because the requirements are clear and fixed from the start, and the project itself is simple.**

6. Explain TWO causes why this problem happens in the Waterfall model. [6 marks]
- **This problem occurs because Waterfall follows a rigid, linear sequence where each phase must be completed before the next begins, and there is no easy way to go back to previous phases to handle changes.**

7. Compare the focus and output of the Incremental Model and Iterative Model. [4 marks]
- **The Incremental model focuses on adding new features to produce new functionality, while the Iterative model focuses on improving the existing system to produce a better, refined version.**

8. Which model is being used and give TWO reasons? [6 marks]
- **The Incremental Model is being used because the system is developed in small parts where each version adds new features, and it allows users to start using early versions of the app.**

9. Which model is being used and why? [6 marks]
- **The Iterative Model is being used because the development is performed in repeated cycles to improve and refine the existing system's design and user experience.**

10. Explain THREE reasons why the Spiral Model may not be suitable for this project. [6
marks]
- **The Spiral Model is unsuitable for a simple project because it is expensive, complex to manage, and requires a high level of expertise to execute.**

11. Give THREE comparisons between Agile and Traditional Models (Waterfall) [6 mark]
- **Flexibility: Agile is very high, while Waterfall is very low.**
- **Handling Changes: Agile accepts changes anytime, whereas Waterfall finds changes difficult and costly.**
- **Delivery: Agile provides frequent delivery every sprint, while Waterfall only delivers the final product at the end.**

12. Give THREE reasons why is the Agile Model suitable for this project? [6 marks]
- **Agile is suitable because it is designed for projects with changing requirements, fits fast-paced environments, and relies on continuous customer feedback to adapt to market trends.**

# Chap 4
1. The 4+1 View Model
The 4+1 view model provides different perspectives for documenting software architecture:

| View             | Purpose                                                                                  |
| ---------------- | ---------------------------------------------------------------------------------------- |
| Logical View     | Shows the key abstractions in the system as objects or object classes.                   |
| Process View     | Shows how the system is composed of interacting processes at run-time.                   |
| Development View | Shows how the software is decomposed for development purposes.                           |
| Physical View    | Shows the system hardware and how software components are distributed across processors. |
| Use Cases (+1)   | Used to relate the other four views together and validate the architecture.              |
2. MVC Architecture
The Model-View-Controller (MVC) pattern separates presentation and interaction from the
system data. It is organized into three logical components:
- **Model: Manages the system data and the operations performed on that data.**
- **View: Defines and manages how the data is presented to the user.**
- **Controller: Manages user interaction (e.g., key presses, mouse clicks) and passes these interactions to the View and the Model.**

3.Generic Layered Architecture
A generic layered architecture organizes a system into layers, where each layer provides
services to the layer above it. This supports incremental development and limits the impact of
changes to adjacent layers.
Main Layers:
- **User Interface: The top-level layer for user interaction.**
- **User Communications: Manages authentication and session management.**
- **Information Retrieval: Implements application-specific logic and data processing.**
- **System Database: The lowest layer representing core data storage and management.**

4. Online Shopping App Case Study
**a) Identified Architecture: Client-Server Architecture.**
**b) Roles:**
- **Client: Users who access services provided by the server through requests over a**
**network.**
- **Server: Stand-alone components that provide specific services (e.g., order processing,**
**inventory management) to clients.**
- **Flow of Communication:**
**[Client (Request)] → [Network] → [Server (Processing)] → [Network] → [Client (Result Display)]**


5. Exam Marks Processing System
a) Best Architecture: **Pipe and Filter Architecture.**
b) Explanation: **This architecture is ideal for data processing applications where inputs are processed in separate, discrete stages (filters) to produce related outputs.**
c) Box-and-Line Diagram Representation:
**[Input Marks] -> [Filter: Remove Invalid Data] -> [Filter: Calculate Totals] -> [Filter: Generate**
**Results] -> [Final Output]**
d) Advantage & Limitation:
- **Advantage: Supports reuse of transformations and is easy to understand.**
- **Limitation: Requires agreement on a data transfer format between filters, which can increase system overhead.**

6. University Student Data System
a) Identified Architecture: **Repository Architecture.**
b) Why Repository: **It is the most effective model for sharing large volumes of data among**
**independent components (lecturers, admin) in a consistent, centralized manner.**
c) Box-and-Line Diagram Representation: **A central "Student Database" connected to**
**peripheral components: "Lecturer Interface" and "Admin Interface."**

7. Online Student Management System

| Layer                 | System Application                                                                        |
| --------------------- | ----------------------------------------------------------------------------------------- |
| User Interface        | The web browser interface where students log in and navigate.                             |
| User Communications   | Handling authentication, secure login sessions, and online payment protocols.             |
| Information Retrieval | Logic for course registration, calculating GPA/results, and processing fee  transactions. |
| System Database       | Central storage for student records, enrollment lists, and financial history.             |
