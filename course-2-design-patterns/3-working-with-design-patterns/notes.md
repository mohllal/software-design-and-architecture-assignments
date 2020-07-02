# Week 3: Working with Design Patterns & Anti-patterns

## Model-View-Controller Pattern

- MVC stands for ***model-view-controller***. The MVC pattern divides the responsibilities of a system that offers a user interface into those three parts:
  - ***Model***: It contains the underlined data and logic users want to see and manipulate. A key part of the MVC pattern is that the model is self-contained. It has all of the state, methods and other data that it needs to exist on its own
  - ***View***: It gives the user a way to see the model or at least parts of it. Sometimes, the view will also have interaction elements like buttons and fields that allow the user to interact with the system.
  - ***Controller***: Information about the user interaction is passed to a controller which is responsible for interpreting these requests and changing the model.

- When some value changes in the back end or the model, it has to tell the view to update itself accordingly. This is done by using the *Observer Design Pattern*. In the observer pattern, the observers act like subscribers. In this case, any view is also an observer. When the model changes, *it notifies all the views that are subscribed to it*. The view may also have ways for a user to make changes to the data in the underlying model.
- In general, the *model* corresponds to those ***entity objects*** derived from analyzing the problem space for the system. A view corresponds to a ***boundary object*** at the edge of your system that deals with users. A controller corresponds with ***control object*** that receives events and coordinates action.

## Design Principles Underlying Patterns

- ***Open/Closed Principle***: This principle states, that classes should be *open for extension*, but *closed to change* which is used to keep the stable parts of your system separate from the varying parts.
- A class as being "closed" to editing, once:
  - It has been *tested to be functioning properly*. The class should be behaving as we would expect it to behave.
  - *All the attributes and behaviors are encapsulated*.
  - Proven to *be stable* within your system.
- Once we've reached a point in development where we've already *finalized most of our design decisions, and have implemented most of our system*, then we should consider ***closing your classes*** to avoid introducing undesirable side effects.
- There are two different ways to extend our system using the *open principle*:
  - The first way, is through ***Inheritance*** of a superclass.
  - The second way a class can be considered open to extension, is if the class is ***abstract*** and enforces the Open/Closed Principle through polymorphism.
- The Open/Closed Principle is a concept that:
  - Helps keep a system stable, by closing classes to changes.
  - Allows the system to open for extension through the use of inheritance, or interfaces.
- If a part of our system is highly coupled, then the degree to which they rely on one another is considered high, whereas low dependency means that your system has a lower degree of coupling.
- The ***Dependency Inversion*** principle states that high level modules should *depend on high level generalizations and not on low level details* which means that the client classes should ***depend on an interface or abstract class*** instead of referring to concrete classes.
- The dependency inversion principle is a means to:
  - Change the referencing of concrete classes from being *direct to indirect*.
  - *Generalize the behaviors* of our concrete classes into abstract classes and interfaces.
  - Have client classes *interact with our system through a generalization* rather than directly with concrete resources.
  - Put emphasis on high level dependency over low level concrete dependency.
- While inheritance is a great way to achieve a high amount of code reuse, it comes with the *cost of tightly coupling the super class with its subclasses*.
- We can use the ***composing objects principle*** to gain a high amount of code reuse without using inheritance. This principle states that ***classes should achieve code reuse through aggregation rather than inheritance***.
- An object can *reuse and aggregate another object* to delegate certain request to it. The idea is that we want to design our system, so that ***concrete classes can delegate task to other concrete classes***. Delegation will provide a loser level of coupling that inheritance.
- Composing objects also provides our system with ***more flexibility***. During the design phase, it's easier and more natural to keep classes separated. Composing objects does not force us to try and find commonalities between two classes, and couple them together like with inheritance.
- Composing objects allows us to, in effect, ***dynamically change the behaviors of objects at run time***. We can build up a new overall combination of behavior by composing objects.
- The biggest drawback of composition is that we must provide implementations for all behavior without the benefit of inheritance to share code. This means that we night have very similar implementations across classes.
- The composing objects principle will:
  - Provide a means of code reuse without the tight coupling of inheritance.
  - Allow objects to dynamically add behaviors at run time.
  - Provide our system with more flexibility.
- The ***Interface Segregation*** principle states that a class should not be forced to depend on methods it does not use. This means that any classes that implement an interface should not have dummy implementations of any methods defined in the interface. Instead, you should split large interfaces into smaller generalizations.
- The ***Least Knowledge*** principle is also realized in a rule known as The ***Law of Demeter***. The underlying idea of this law is that classes should know about and interact with as few other classes as possible. This means that any class should only communicate with its immediate friends. These friends would be other classes that one class should only know about.
  - The First Rule: method, M, in an object, O, can call on any other method within O itself.
  - The Second Rule: method, M, can call the methods of any parameter, P.
  - The Third Rule: method, M, can call a method, N, of an object, I, if I is instantiated within M.
  - The Fourth Rule: method, M, in object, O, can invoke methods of any type of object that is a direct component of O.
- All the rules of the Law of Demeter come down to the principle that *we should not allow a method to access another method by* ***reaching through an object***. The term "reaching through" means that *we'd need to use another object to pass along your request*. Or that we are using methods of objects that are considered outside your immediate friends.
- Another way we can reach through an object is when *our method receives an object of an unknown type* as a return value and you make method calls to the returned object.
- According to the Least Knowledge design principle a method, M, of an object should only call other methods if they are:
  - Encapsulated within the same object.
  - Encapsulated within an object that is in the parameters of M.
  - Encapsulated within an object that is instantiated inside of M.
  - Encapsulated within an object that is reference in an instance variable of the class for M.

## Anti-Patterns and Code Smells

- Refactoring is the process of making changes to our code so that *the external behaviors of the code are not change*, but *the internal structure is improved*.
- Using comments to explain a design can sometimes indicate that the programming language isn't appropriate. Perhaps the programming language does not support the design principles you're trying to apply.
- Having a ***long method*** can sometimes indicate that there is more occurring in that method than should be. Or it's more complex than it needs to be.
- Having a ***large class*** is sometimes considered to be a code smell. These large classes are commonly referred to as *God classes*, *Blob classes*, or *Black Hole classes*.
- ***Data classes*** are classes that contain only data and no real functionality. Generally, these classes would have getter and setter methods, but not much else.
- ***Data clumps*** are groups of data appearing together in the instance variables of a class, or parameters to methods.
- Having a ***method with a long parameter*** list can be difficult to use, which is bad. However, the common solution to reduce the amount of parameters is often to have global variables. These have issues of their own, and generally should be avoided.
- The ***divergent change*** code smells occur when you have to change a class in many different ways for many different reason.
- The ***shotgun surgery*** code smell occurs when a change in one place requires us to fix many other areas of the code as a result. This could happen when we're trying to add a feature, adjust code, fix bugs or change algorithms.
- The ***feature envy*** code smell occurs when we've got a method that is more interested in the details of a class other than the one that it's in.
- The ***inappropriate intimacy*** code smell occurs we have two classes that talk really closely to each other. So, a method in one class calls methods of the other and vice versa. To remove this cycle, *we can factor out methods that both classes use into another class*. This might free up some of the close communication. At the very least, you should be able to make it, so that the communication only occurs one way.
- The ***primitive obsession*** code smell occurs when we rely on the use of built-in types too much. These built-in types or primitives are things likes `int`s, `long`s, `float`s or `string`s.
- The ***Speculative generality*** occurs when we make a superclass, interface or code that is not needed at the time, but we think we may use it someday. With agile development, we want to be practicing ***just in time design***. We want just enough design to take the requirements for a particular iteration to a working system.
- The ***refused request*** smell occurs when a subclass inherit something and doesn't need it.
