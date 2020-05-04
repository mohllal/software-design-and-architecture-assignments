# Week 1: Object Oriented Analysis and Design

- A ***software architect*** role would be responsible for looking at the entire system and choosing appropriate *frameworks*, *data storage*, *solutions* and determining *how components interact* with each other.
- Software design *looks at the lower level aspects* of a system, whereas software architecture tends to *look at the bigger picture, the higher level aspects of a system*.
- Software design is *the process of turning the requirements* of a customer *into code that is stable and maintainable* in the long run, and can be evolved and can become part of a larger system.
- One of the key challenges in software architecture is the tendency to have to ***trade off between speed and quality***. The tendency for the businesses that wants their software provide functional results as soon as possible. And there's a tendency for the engineering team to want to build, the most robust, thoroughly designed, thoroughly implemented system possible.
- A software architect's job is to be ***the interface*** between the product and the customer and the engineering teams.
- We can communicate software architecture through the *written word*, through wikis, through white papers, these kinds of things, in addition to *fairly detailed engineering design schematics*, class diagrams, if necessary, big box diagrams, if it's just a simple high level architecture design.
- ***Simplicity*** is main key principle in architecting software. The engineering maxim to keep it simple.

> But of all the technical skills that you've got, you need this meta skill, which is to look at various technologies and ideas and decide, is that going to be useful to me or not in my particular problem I'm trying to solve? So you have to have the skill of being able to quickly assess various technologies and fit them into your understanding of the discipline.
> The advice you give to new software architect is the same advice you give to a musician. Try and play with people who are much better than you are because that's how you become a better architect. At the very least, try to read as much of the foundational literature in the field.

- ***Object-oriented modeling*** involves the practice of representing key concepts through objects in the software. Depending on the problem, many concepts, even instances of people, places or things become distinct objects in the software.
- The design activity involves taking requirements and outlining a solution. This activity involves producing a ***conceptual design*** and then a ***technical design***, which results in two corresponding kinds of artifacts, c***onceptual mockups*** and ***technical diagrams***.
- In a technical design, you start ***specifying the technical details of each component***. This is done by splitting components *into smaller and smaller components* that are specific enough to be designed in detail.
- Components, when they are refined enough, turn into collections of functions, classes or other components. These pieces then represent a much simpler problem that the developers can individually implement.
- ***A user story is simply a technique for expressing a requirement***, often from the perspective of an end-user, which is stated in natural language. Usually, *the nouns correspond to objects* in your software. Verbs can help you identify the requirements that your objects might have.
- ***Entity objects*** are objects that correspond to some real-world entity in the problem space.
- ***Boundary objects*** are objects which sit at the boundary between systems. This could be an object that deals with another software system.
- ***Control objects*** are objects which are responsible for coordination. A great example is a *Mediator*: it simply coordinates the activities of many different objects so that they can stay loosely coupled.
- When designing software, it is important to consider how qualities attributes such as *performance*, *convenience* and *security* can compete in a proposed solution under different situations and determine a suitable compromise.
- Architecture is all about *balancing competing concerns*. Software Architect always balances quality versus time to market.
- ***Functional requirements*** describe what the system or application is expected to do.
- ***Non-functional requirements*** specify how well the system or application does what it does.
- There is a common trade-off between ***performance*** and ***maintainability***. High performance code may be less clear and less modular making it less maintainable. Another trade-off is security and performance. The extra overhead for high security may reduce performance. Extra code for backward compatibility can worsen both performance and maintainability.

> Qualities are competing ideals that must be balanced. Generally, you have to strike a balance during design. You should ask how much performance, maintainability, security or backward compatibility is needed

- User stories can be written as: ***As a ____, I want to ____, so that ____***.
- ***CRC*** cards where CRC stands for *Class*, *Responsibility*, *Collaborator* is a technique for representing the requirements at a high level when forming the conceptual design. CRC cards help us to organize our components into classes, identify the responsibilities and determine how they will collaborate with each other.
- A CRC card has *three sections*. The *top* of the card has the ***class name***. On the *left* are the ***responsibilities*** of the class, and on the *right*, you list ***collaborators***. Collaborators are other classes that the class interacts with to fulfill its responsibilities.