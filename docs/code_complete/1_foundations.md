# Laying the Foundations (Chapters 1 - 4)

## 1. Measure Twice, Cut Once!

### The Goal of Preparation: Risk Reduction

- Code construction is like building a house, there are the stages of **planning, construction, and testing/inspection**.

- Poorly planned projects are costly not because of the material cost but because **errors cause people time** (e.g. moving a wall after construction; redoing the construction two or more times).

- Overarching goal of preparation is **risk reduction**; the most common project risks in software development are _poor requirements_ and _poor project planning_.

- Illustration: building a 3 foot tower (1 meters) takes 10 beer cans, a pair of steady hands and a level ground, but building a tower 10 times higher takes much more than just 10x more beer cans. Similarly, detailed planning is required for building code just like building a house or a sky-scraper. The level of planning and the approach could be different depending on the kind of building.

### Why are good prerequisites important?

- High-quality software comes from attention to quality in all three phases. But **attention to quality at beginning** (requirement and architecture design) has greater influence on product quality than attention at the end, during system testing.

- It is **much more costly** (estimated ~20-100x) to **change a requirement after construction** than earlier, closer to the time of writing the requirements.

- So be sure the requirements are right before you start.

### Caution

- However, do not over-engineer! Some projects are better **sequential**, and some are better **iterative**, where the requirements are revised at each development cycle according to user feedback. **Choose the right model** (or combination of) for your project.

- Even in the iterative case, nevertheless, specifying well-specified pre-requisites reduces cost of the current cycle.

- **What if my environment allows no time for designing pre-requisites?** -- Part of the job of a technical employee is to educate people around them (including their supervisors and teammates) about the software-development process (_so don't pretend you are coding while doing the design, or worse, skip it altogether_), including the importance of developing pre-requisites before constructing the code, and planning time for it.

## Checklist for good prerequisites

### Requirements

**Essential**

- Describe **inputs** and **outputs** to the system (e.g. accuracy, range of values, format, frequency; source for inputs; destination for outputs). Put output formats in shared documentation.

- Specify all **external software interfaces** and all **communication interfaces** (e.g. protocols for error-checking, hand-shaking, communication.)

- List all the **tasks** the user want to perform.

- Specify **data used in and output by each task**.

**Optional** (specify if needed): the expected response time from the user's point of view; other timing expectations, e.g. processing time, data-transfer rate, system throughput; minimum machine memory/free disk space; portability to other operating system; ability to handle changes in internal functionalities and external software interface; definition of success/failure, etc.

**Signs of good requirements**
(1) Each requirement can be tested; (2) requirements are not specifying a design; (3) possible changes to the requirements are specified along with how likely the changes are; (4) if all the requirements are satisfied, then the product is acceptable; (5) areas where it is impossible to specify the requirements before construction are noted; (6) no requirements are impossible to implement.

### Architecture

**Main components:** <br />

- Describe clearly the overall organization of the program, including good architecture overview and justification. Provide motivations for all major decisions made.

- Define major building blocks, what each block is responsible for, and how they interface.

- Describe and justify critical classes (_use the 80/20 rule: specify 20% of the classes that make up 80% of the system's behavior_).

- Describe and justify data design.

- Establish technical feasibility of all parts of the system.

**Other:** <br />

- Describe how scalability can be achieved.

- Describe how it is designed to accommodate likely changes.

- Describe and justify possibly other aspects: I/O handling strategy, speed vs memory budgets for different components, error-handling strategy, security requirements, buy-vs-build decisions, how re-used code will be made to conform.

- Make sure the user interface is modularized so changes can be decoupled from the rest of the program.

---

## 2. Key Construction Decisions

### Programming Languages

- Choosing the right programming language is important. **People coding in languages they are familiar with** are ~3x more productive than as beginners.

- In general, programming in higher-level languages is more efficient for development. (ratio of statement number: 6 for python, 2.5 for C++, 2 for fortran, and 1 for C). Some languages are also more expressive than others.

- Beware that some may be able to **"program into the language"** instead of "in a language" (having the ability to think of a concept first and then to express it in a given language), while others may not be able to do so even having the most expressive language to use (because their thoughts are being limited by the way things are done in a particular language they are used to.)

### Programming Conventions

- It is important to **set the programming conventions** before you start constructing (because it's nearly impossible to change afterward).

- Lower-level implementations need to **reflect consistency** with the higher-level design (integrity), and be internally consistent. Illustration: A great design for a painting can amount to a weird collage when its different parts are being done with impressionist/ modern/ crayon styles...

- **Unified programming conventions** means that there is **less brain load on the programmers** spending time in the code. Instead of spending time figuring out which variations that are results of arbitrary choice, they **single out the meaningful variations** much faster as a results and focus their attention on those.

## Checklist before you start constructing

### Do you have a?

- Procedure for **naming/comments/functions/classes** and other specific **coding practices**. (We recommend the [Google style guide](https://google.github.io/styleguide/); see also the [summary on Clean Code](../clean_code/overview.md) upcoming on this website for general principles.)

- Procedure for **Error handling**; convention for **class interfaces**; standards for reused code; performance considerations?

- **Integration procedure** for checking in code into the master source.
  (We recommend using **Git** for version control, locking the master branch for releases only, and using the develop branch for intaking daily pull requests, where each pull request needs to be reviewed and approved by at least one person on the team, either by a peer or a supervisor, before being merged in.)

### Will you ... ?

- Write unit tests? (Highly recommended.) Write down the test cases before coding?

- Write and perform integration tests before checking code in? (Recommended to setup automated **continuous integration** if you are working on a large system or working with more than one person on the code.)

### Do you have the tools for ?

- Editing, refactoring, syntax checking? (We highly recommend using **Visual Studio Code** as your editor, where you can download a lintor for syntax checking of any language, you debug concurrently in a terminal while editing code all in one window, and work remotely on a cluster as if you were on your laptop. We also recommend unifying editing tools within the team as much as possible, since some editors have different auto-formatting conventions.)
