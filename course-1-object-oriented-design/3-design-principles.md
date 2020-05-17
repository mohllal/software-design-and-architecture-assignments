# Week 3: Design Principles

- The metrics used to evaluate design complexity are ***coupling*** and ***cohesion***. Coupling focuses on complexity *between a module and other modules*. Cohesion focuses on complexity *within a single module*.
- When evaluating the coupling of a module, we need to consider ***degree***, ***ease***, and ***flexibility***.
  - *Degree is the number of connections between the module and others*. With coupling, you aim to keep the degree small.
  - *Ease is how obvious are the connections between the module and others*. With coupling, we aim to make the connections easy to make without needing to understand the implementations of the other modules.
  - *Flexibility is how interchangeable the other modules are for this module*. With coupling, you aim to make the other modules easily replaceable for something better in the future.
- Cohesion represents ***the clarity of the responsibilities*** of a module.
- In general, ***there's a balance to be made between low coupling and high cohesion*** in your designs. For a complex system, ***the complexity can be distributed to between the modules or within the modules***. As modules are simplified to achieve high cohesion, they may need to depend more on other modules thus increasing coupling. As connections between modules are simplified to achieve low coupling, the modules may need to take on more responsibilities thus lowering cohesion.
- Separation of concerns creates more cohesive classes using abstraction, encapsulation, decomposition, and generalization.
- ***Information hiding*** allows models of our system to give others the minimum amount of information needed to use them correctly and hide everything else.
- ***Access modifiers*** change which classes are able to access attributes and behaviors. They also determine which attribute and behaviors a superclass will share with its subclasses.
- The ***default access modifier*** will only allow access to attributes and methods to subclasses and to the encapsulating class. This access modifier is also called the no modifier access because you do not need to explicitly declare it.
- ***Conceptual integrity*** is about creating consistent software. It's making decisions about how the system will be designed and implemented, so that even if multiple people worked on the software, it would seem as if there was only one mind guiding all the work.
- There are multiple ways to achieve conceptual integrity:
  - ***Communication*** by adopting certain agile development practices like *daily stand-up meetings* and *sprint retrospectives*.
  - ***Code reviews***. Code reviews are systematic examinations of written code. It's often used to find mistakes in the software, but also to keep different developers consistent with each other.
  - Additionally, using *certain design principles and programming constructs* can also help in maintaining conceptual integrity.
  - Another approach to achieving conceptual integrity is *having a well defined design or architecture* underlying your software.
  - Unifying concepts is also another approach to maintaining conceptual integrity. It is taking seemingly different things and finding common ground so that each concepts can be seen and treated in similar ways.

> It is better to have a system omit certain anomalous features and improvements, but to reflect one set of design ideas, than to have one that contains many good but independent and uncoordinated ideas.

- An indication of improper use of generalization is, if you break the ***Liskov Substitution Principle***. The principle states that a subclass can replace a superclass, if and only if, the subclass does not change the functionality of the superclass.
- If inheritance does not suit, consider whether ***decomposition is more appropriate***.
- A ***sequence diagram*** describes how objects in your system interact to complete a specific task.
- When creating sequence diagrams, first you use a ***box*** to *represent role played by an object*. The role is typically labeled by the name of the class for the object. Second, you use ***vertical dotted lines, known as lifelines***, to *represent an object as time passes by*. Finally, we use ***arrows*** to *show messages* that are sent from one object to another.
- In a sequence diagram, we would have *one big sequence* of activities with two smaller sequences inside them. they are commonly used as a planning tool before the development team starts programming, or to show others how a system is designed.
- If there are people, who will be using or interacting with objects, this are typically draw on a ***stick figures***. We call these people ***actors***.
- When an object is activated, we denote this on our sequence diagram using *small rectangles on the objects lifeline*. You activate an object whenever an object *sends*, *receives* or it's *waiting for a message*.
- We can wrap sequence digram as a part of an ***alternative process***. So that it is a sequence of actions that will occur if a condition is true. ***So we put the sequence in a box and label it alt, for alternative, in the top right corner***.
- Sequence can contains a loop. We can denote that by adding and labeling a box ***loop*** on the top right corner.
- A ***state diagram*** is a technique that can be used to describe how the system behaves and responds. In state diagrams, *arrows* are used to represent events to transition from one state to another.
- State diagrams can *describe a single object and illustrate how that object behaves in response to a series of events in your system*. A state is the way an object exists at a particular point in time. The state of an object *is determined by the values of its attributes*.
- When an object is in a certain state, it behaves in specific ways or has attributes set to specific values. Using UML state diagrams, you can express the different states of your objects and how the states will change when an event occurs.
- Every state diagram has a ***filled circle*** to indicate which is the starting state. Each state has three important sections, ***a state name***, ***state variables***, and ***activities***. Each state should at least have a state name. A state name is as it sounds, the name of the state, these names should be meaningful for the states of an object.
- Activities are actions that are performed when in a certain state, and they're displayed at the bottom. There are three types of activities for each state, ***entry***, ***exit***, and ***do***:
  - *Entry activities* are actions that occur when the state is just entered from another state.
  - *Exit activities* are actions that occur when the state is exited and moves on to another state.
  - *Do activities* are actions that occur once, or multiple times while the object is in a certain state.
- Events that could change a state label ***transitions*** between the states. We draw these transitions with *arrows from one state to another*. Each transition arrow will always have an event, and may have a ***guard condition and an action***. The transition and action happens from a given state if the event occurs and the condition is true.
- ***Termination*** represents an object being destroyed, or the process being completed, and is drawn as a circle with a filled circle inside.

> So how do we reason about our software? One school of thought says that, well, we can look at our program as a mathematical artifact. And we can prove properties about what the program does. And there's another line of approach which says, for this things that have all these weird special cases, what we should do is mechanically enumerate all the special cases.
> The problem with model checking is the so called ***stage space explosion***. If I've got one bit, i have two states. If I got I've got ten bits, I've got two to the tenth states.

- A deadlock is a situation where the system cannot continue because two tasks are waiting for the same resource.
- There are three different phases to performing model checking:
  - ***The modeling phase***: This is where we enter the model description and desired properties.
  - ***The running phase***: This is when we run the model checker to see how our model conforms to the desired properties that you've wrote in the modeling phase.
  - ***The analysis phase***: This is where we check if all the desired properties are satisfied and if any are violated. Violations are called ***counterexamples***.

> Model checking is a very useful verification technique, there are many ways to test your system's behaviour, like *unit testing*, *beta testing*, and *simulations*. But model checking can help find errors that these tests can't. If you're looking to use model checkers to develop your programs, there are many different free model checkers available for developers that use different languages.