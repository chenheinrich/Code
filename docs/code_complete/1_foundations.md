# Laying the Foundations (Chapters 1 - 4)

## 1. Measure Twice, Cut Once! 

### Metaphor: Contructing a building

* Code construction is like building a house, there are the stages of **planning, construction, and testing/inspection**. 

* Poorly planned projects are costly not because of the material cost but because **errors cause people time** (e.g. moving a wall after construction; redoing the construction two or more times).

* Overarching goal of preparation is **risk reduction**; the most common project risks in software development are *poor requirements* and *poor project planning*.

* _Illustration: building a 3 foot tower (1 meters) takes 10 beer cans, a pair of steady hands and a level ground, but building a tower 10 times higher takes much more than just 10x more beer cans. Similarly, detailed planning is required for building code just like building a house or a sky-scraper. The level of planning and the approach could be different depending on the kind of building._


### Why are good prerequisites important?

* **High-quality software** comes from attention to quality in all three phases. But **attention to quality at beginning** (requirement and architecture design) has greater influence on product quality than attention at the end, during system testing. 

* It is much more costly (estimated ~20-100x) to change a requirement after construction than earlier, closer to the time of writing the requirements. 

* So be sure the requirements are right before you start.

### Other Notes

* However, do not over-engineer! Some projects are better **sequential**, and some are better **iterative**, where the requirements are revised at each development cycle according to user feedback. **Choose the right model** (or combination of) for your project.

* Even in the iterative case, nevertheless, specifying well-specified pre-requisites reduces cost of the current cycle.

* **What if there is no time for pre-requisites?** -- Part of the job of a technical employee is to educate people around them (including their supervisors and team-members) about the software-development process, including the importance of developing pre-requisites before constructing the code, and planning time for it.

### Checklist for good prerequisites

#### Requirements

* Specify inputs, outputs to the system.

* Specify tasks to be performed.

* Specify any external software/communication interfaces.

* (Optional) Specify response time form user's point of view, timing in various part of the system, memory/free disk space, maintainability, definition of success, etc.

#### Architecture 

Main components: <br />  

* Describe clearly the overall organization of the program, including good architecture overview and justification. Provide motivations for all major decisions made.

* Define major building blocks, what each block is responsible for, and how they interface.

* Describe and justify critical classes (*use the 80/20 rule: specify 20% of the classes that make up 80% of the system's behavior*).

* Describe and justify data design.

* Establish technical feasibility of all parts of the system.

Other: <br />  

* Describe how scalability can be achieved.

* Describe how it is designed to accommodate likely changes.

* Describe and justify possibly other aspects: I/O handling strategy, speed vs memory budgets for different components, error-handling strategy, security requirements, buy-vs-build decisions, how re-used code will be made to conform.

* Make sure the user interface is modularized so changes can be decoupled from the rest of the program.

----------------------------

## 2. Key Construction Decisions [Draft, to be polished]

### Programming Languages

* Programming languages (people coding in languages they are familiar with are ~3x more productive than as beginners.) In general, programming in higher-level languages is more efficient. (ratio: 6 for python, 2.5 for C++, 2 for fortran, and 1 for C). C++ seems to be the most expressive. 

* Programming languages have their own strengths and limitations. Program _into_ the language rather than _in_ the language is important. Programming happens in the head first, before it goes on screen, i.e. choosing how to express the idea in the particular language. 

### Programming Conventions

* It is important to set the programming conventions before you start constructing (because it's nearly impossible to change afterward); Lower-level implementations need to reflect consistency w/ the higher-level design (integrity), and be internally consistent. _Illustration: Great design for a painting done in impressionist/modern/crayon styles, looks like a collage at the end of the day, rather than a painting._

* Unified programming conventions also means that there is less brain load on the programmers spending time in the code, for figuring out the variations that are results of arbitrary choice, and that meaningful variations could stand out, and programmers can use their brain power to concentrate on those.

### Checklist before you start constructing [Draft]

* Procedure for handling errors; different conventions for classes/comments/naming, etc. (Google style guide)

* Procedure for checking in code into the master source (pairs + tests, individual + inspection) - Git

* Write test cases before coding? Unit tests? System integration tests? (--> want to set this up)  - CI + unit tests


