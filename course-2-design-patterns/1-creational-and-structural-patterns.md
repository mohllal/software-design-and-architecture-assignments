# Week 1: Introduction to Design Patterns: Creational & Structural Patterns

- A design pattern is a ***practical proven solution*** to a recurring design problem. These design solutions are not theoretical proposals of only academic interest. These are actual solutions that are used in industrial software.
- Design patterns are a bit more conceptual. It is knowledge that you can apply within your software design to guide its structure, and make it more flexible and reuseable.
- A collection of patterns that are related to a certain problem space is called a ***Pattern Language***. Depending on the context of the problem, you would need to use different pattern languages.
- Design patterns can be categorized into three types:
  - Creational Patterns tackle how you handle creating new objects. There are several different patterns based upon creating and cloning objects.
  - Structural patterns describe how objects are connected to each other.
  - Behavioral Patterns focus on how objects distribute work. They describe how each object does a single cohesive function. Behavioral patterns also focus on how independent objects work towards a common goal.
- The ***singleton design pattern*** is about something singular, *having only one*. the Singleton pattern refers to having only one object of a class that is globally accessible within the program.
- ***Lazy creation*** can be helpful if the object is large. It is not created until the `getInstance()` method is called, which is more efficient.
- ***Factory object*** is an instance of such a class, which has a method to create product objects *(concrete instantiation)*. So if there are multiple clients that want to instantiate the same set of classes, then by using a factory object, we have cut out redundant code and made the software easier to modify.
- The client methods do not need to name a concrete type of classes and now deal with a type generalization. This is called ***coding to an interface, not an implementation***.
- The ***factory method pattern*** approaches the creation of specific types of objects in a different way. *Instead of using a separate object*, a factory object to create the objects, *the factory method uses a separate method in the same class to create the objects*. Now instead of working with the factory object, we specialize or subclass the class that uses the factory method. Each subclass must define its own factory method.
- The factory method design intent is to ***define an interface for creating objects***, but *let the sub-classes decide which class to instantiate*.
- The facade design pattern provides a single simplified interface for client classes to interact with the subsystem. A facade does not actually add more functionality, a facade simply acts as a point of entry into your subsystem.
- *A facade is a wrapper class that encapsulate the subsystem in order to hide the subsystem's complexity*. This wrapper class will allow a client class to interact with the subsystem through a facade.
- We can summarize the facade design pattern in four steps:
  1. Design the interface.
  2. Implement the interface with one or more internal classes.
  3. Create the facade class and wrap the classes that implement the interface.
  4. Use the facade class to access the subsystem by different client classes.
- The ***adapter design pattern*** will help facilitate communication between two existing systems by providing a compatible interface. It consists of the following components:
  - The ***client class***: Which will be part of the system that wants to use a third-party library or external system.
  - The ***adaptee class***: A class in the third-party library or external system to be used.
  - ***The adapter class***: Sits in between the client and the adaptee. It will implement a target interface which is the interface that the client will use. The adapter conforms to what the client is expecting to see.
- The adapter is meant to wrap the adaptee and expose a target compatible interface to the client.
- The client *sends a request to the adapter* using the target interface. The *adapter will then translate the request* into a message that the adaptee will understand. Once the translation is finished, it *will send the translated request to the adaptee*.
- We can summarize the adapter design pattern in four steps:
  1. Design the target interface. Create the target interface that the adapter class will be implementing for the client class to use.
  2. Implement the target interface with the adapter class.
  3. Make the client interact with the adapter using the target interface.
  4. Make the adapter interact with the adaptee.
- The proxy acts as *a simplified or lightweight version of the original object*. A proxy object is still able to accomplish the same tasks, but may delegate requests to the original object to achieve them.
- In the proxy design pattern, the proxy class wraps the real subject class, that is, hides a reference to an instance of the real subject class. Client classes will interact with it instead of the real subject class.
- The three most common scenarios for using the proxy pattern are:
  - One, to act as a virtual proxy where the proxy class is used in place of a real subject class, that is resource intensive to instantiate.
  - Two, to act as a protection proxy in order to control access to the real subject class.
  - And three, to act as a remote proxy, where the proxy class is local and the real subject class exists remotely.
- Since the proxy class is meant to stand in for the real subject class, it must offer the same methods. We can ensure that by *having both these classes implement a common subject interface*, which also allows for polymorphism.
- The main features of the proxy design pattern are:
  - To use the proxy class to *wrap the real subject class*.
  - To have a *polymorphic design* so that the client class can expect the same interface for the proxy and real subject classes.
  - To use a *lightweight proxy in place of a resource intensive object* until it is actually needed.
  - To implement some form of intelligent verification of requests from client code in order to determine if, how, and to whom the requests should be forwarded to.
  - To *present a local representation of a system* that is not in the same physical or virtual space.
- The ***decorator*** design pattern uses aggregation to combine behaviors at runtime. Aggregation is used to represent a *has a* or *weak containment* relationship between two objects.
- We can use that *has a* relationship to *build a stack of objects where each level of the stack contains an object that knows about its own behavior and augments the one underneath it in the stack*.
- The aggregation relationship is always one-to-one in the decorator design pattern in order to build up the stack so that one object is on top of another.
- Decorator is an abstract class. Just like the concrete component class, it implements the component interface. The main differences are that decorator aggregates other types of components which will allow us to stack components on top of each other, and decorator serves as the abstract superclass of concrete decorator classes that will provide an increment of behavior.
- The key concepts for the decorator design pattern are that:
  - We can ***add in effect any number of behaviors dynamically*** to an object at runtime by using aggregation as a substitute for pure inheritance.
  - ***Polymorphism is achieved by implementing a single interface***.
  - ***Aggregation lets us create a stack of objects***.
  - **Each decorator object in the stack is aggregated in a one-to-one relationship with the object below it in the stack**.
  - Combining aggregation and polymorphism, we can recursively invoke the same behavior down the stack and have the behavior execute upwards from the concrete component object.
