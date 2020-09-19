# Creating High Quality Code (Chapters 5 - X)

## Managing Complexities 

* The primary causes of software project failures reported in surveys are rarely technical. They are mostly poor requirements, planning or management. But when they do fail for mainly technical reasons, the primary culprit is **uncontrolled complexity**.

* Managing complexities is one of the most, if not the most important technical topic in software development. 

* **No one's brain is big enough to contain an entire computer program.** So one should not try to cram it all into one brain, but aim to organize the programs in such a way that we can safely focus on one part of it at a time.

* To minimize the amount of program you have to think about at once, we **break big pieces into smaller ones**.  
For example: make code modular (the more the different components are independent the more one can focus on it one at a time); keep routines short, write programs in the problem domain, work at the highest level of abstraction. <link to Clean Code section on functions in the future>

* In sum, those who compensate for the fact that **humans can hold only a few things in the brain at once**, will make code that's easier for themselves and others to understand and reduce errors.

## Design Principles

How hard is it to work in your code?  

* **Minimal Complexity** - Avoid "clever" designs; choose "simple", "easy-to-understand" ones. Your design should let you safely ignore most parts of the program while focusing on a specific part. 

* **Ease of Maintenance** - Design it for the maintenance programmer (possibly yourself in a few years). Continually ask yourself what maintenance programmer would ask you when they try to maintain the code. Make the design self-explanatory.  

How easy is it to test/extend/resuse your code?

* **Loose coupling** - Least possible connections among different parts of the program (e.g. classes have few interconnections between them). This benefits integration/ testing/ maintenance.

* **Extensibility** - You can enhance the system without shaking its whole structure (e.g. it's safe to change one piece of a system without affecting many others).

* **Reusability** - You can reuse pieces of the code in other systems.  

How efficient is your code's internal organization?

* **High fan-in** - A class is being used by many other classes, e.g. lower-level utility classes. The same applies to functions.

* **Low-to-medium fan-out** - Each class uses only a few other classes (about <7); otherwise, it's an indication that the class is too complex). The same applies to functions.  

* **Leanness** - Voltaire: "a book is finished not when nothing more can be added but when nothing more can be taken away." Be careful, extra code needs to be written/ reviewed/ tested/ considered when other code is changed -- it's not for free.  
 
How welcoming is your code to others?

* **Stratification** - You can view each level of decomposition without dipping into other levels.  
For example, if your code uses older and poorly designed code, write new classes to interface with it, so all other parts of the system just use these new classes. This way, you can 1) compartmentalize messy code, and 2) modify only the interface when the old code is to be replaced or improved.

* **Standard Techniques** - Use less exotic pieces since it can be intimidating for others trying to understand it. Cultivate a familiar feeling by using standard and common techniques.

* **Portability** - You can easily move it to another environment. 
