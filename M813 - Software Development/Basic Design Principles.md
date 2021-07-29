# Object-Oriented Design Basics

Object-oriented design essentially aims to assign responsibilities to classes so as to realise system functionality and maximise software flexibility, ease of maintenance and reuse.

A **responsibility** can be seen as an obligation to perform a particular service.

Broadly speaking, we group responsibilities into two main categories:
-   responsibility for _knowing_ – that is, about:
    -   attribute values
    -   links to other objects
    -   information that can be derived or calculated from attributes and links.
-   responsibility for _doing_ – that is, for:
    -   performing calculations
    -   cooperating with other objects to perform functions (**collaboration**)
    -   coordinating the behaviour of other objects (**orchestration**).

# General Design Principles

### Low coupling principle
Strive for loosely coupled design between objects that interact. This is also known as the **low coupling principle**. In a software system, **coupling** is a measure of the dependency between classes resulting from collaborations between objects to realise the overall system functionality; it is a measure of how strongly one class is connected to, has knowledge of, or relies on other classes.

Two objects that are loosely coupled can interact, but have very little knowledge of each other. Loosely coupled designs let us build flexible object-oriented systems that can handle change because they minimise interdependency between objects. For the same reason, they also maximise the potential for class reuse.

On the other hand, classes that exhibit high coupling are ones whose objects are very reliant on each other; this implies rigidity, hence reduced flexibility, because it is harder to understand each class in isolation, and changes in one class may require changes in other dependent classes.

### Law of Demeter
"Only talk to your friends." This principle, also known as the **principle of least knowledge (PLK)** or **law of Demeter**, helps coders avoid certain patterns of object interactions which can lead to overly coupled systems, by preventing the creation of designs with several classes coupled together.

The basic idea is that an object only needs to know about its immediate linked neighbours – that is, objects whose classes are associated with the class of the object in question. What the neighbours know should remain private to them.

### Single-responsibility principle
A class should have only one reason to change. This is also known as the **single-responsibility principle (SRP)** or **high-cohesion principle**. In software, **cohesion** is a measure of how closely related and strongly focused the responsibilities of a class are. That is, a cohesive class is one that performs a well-defined function or task, rather than many functions or tasks with little in common.

A class with high cohesion is easy to maintain and offers wide opportunities for reuse. A class with low cohesion requires greater maintenance effort, because it is harder to understand and there may be many reasons why the code might change.

### Abstraction principle
"Don't repeat yourself." This principle guards against code duplication on the basis that things that are common should be abstracted out and placed in a single location. Duplication should be avoided as it can lead to systems which are hard to understand and maintain, and can increase the likelihood of inconsistent behaviour across a system.

### Encapsulation
**Encapsulate what varies**. This means organising an object’s properties into private and public domains. Public properties can be accessed by other objects; private properties remain hidden within the object (this is also called **information hiding**). Encapsulation emphasises the separation between public interface and private implementation – the services offered by an object are publicly advertised in its interface, while their implementation remains hidden within the object. Other objects wanting to use such services can do so only by relying on the object’s public interface. Through encapsulation, an object’s interface, and the information it needs to implement that interface, are packaged under one name. Encapsulated objects which interact with each other will be unaffected by any changes made to their implementation, as long as their interfaces remain unchanged.

### Program to interfaces, not implementations
An **interface** is a description of a set of externally visible operations: it specifies a set of services in terms of operations and their signatures. An interface does not define the operations, only their signature; instead, operations are defined within classes that provide an implementation for the interface. This is called **realisation**, with a class realising an interface by defining (or inheriting) operations corresponding to those of the interface. A class can realise more than one interface, in which case the class must declare all the operations included in all the interfaces. A class may also contain additional operations.

### Depend on abstraction, not on concrete classes
Also called the **dependency inversion principle (DIP)**. The principle looks at dependency relationships between classes at a high level of abstraction and classes at a lower level of abstraction. It states that high-level classes should not depend on low-level classes; rather, both should depend on abstractions. The main goal here is to avoid dependency on lower-level components which may limit reuse opportunities for higher-level components.

### Liskov substitution principle
This principle enhances designs with inheritance and polymorphism in the context of generalisation–specialisation (‘is-a’) hierarchies. The substitution principle states that in such a hierarchy, objects that are instances of a subclass can substitute for instances of the superclass – so you should guard against designing hierarchies where this property does not hold.

One benefit of generalisation–specialisation hierarchies in object-oriented code is **inheritance**: a subclass inherits both attributes and operations from a superclass, but can also add its own. This allows clarity and code reuse, with all common code defined once in the superclass and shared among all subclasses.

Classes in a generalisation–specialisation hierarchy are often polymorphic. **Polymorphism** is the ability of objects of different classes to respond to the same message in a specialised way. In the context of inheritance, polymorphism allows subclasses to define specialised versions of operations defined in their superclasses; this is called **overriding**.

### Favour composition over inheritance
This principle, also known as the **composite reuse principle**, allows classes to achieve polymorphic behaviour and code reuse by ‘containing’ other classes that implement the desired functionality instead of applying inheritance.

This is one of the most important design principles, it is based on the concept of composition. A **composition** relationship between classes can be thought of as a ‘whole–part’ relationship between their objects. A strong whole–part relationship exists where the composite object owns its parts – that is, a part can only belong to one composite and the composite has sole responsibility for its parts, including creation and destruction. In a composition relationship a part does not exist independently of its composite.

A weaker form of composition is defined as an **aggregation** relationship, where parts can exist independently of their aggregates.

_Note: compositions and aggregations are sometimes called ‘has-a’ relationships._

### Open-Closed principle
Classes should be open to extension but closed for modification. In an ideal world, you should never need to change existing code within classes – any new functionality should be added by adding new subclasses or methods, or invoking services of existing classes. This principle fosters designs in which classes can easily be extended to incorporate new behaviour without modifying existing code. This boosts resilience and flexibility to allow new functionality to be defined to meet changing requirements.

### Don’t call us, we’ll call you (IoC)
This principle, also known as the **Hollywood principle** or the **inversion- of control principle**, is particularly relevant when your software must fit the constraints of an existing software framework.

The principle states that the application-specific (low-level) classes you define should depend on generic (high-level) classes in the framework, but not vice versa. That is, your classes should be tailored to the framework by realising appropriate interfaces defined in the framework and depending on high-level classes in the framework to determine when they are needed and how. The framework defines the flow of control and your code is called by the framework when the time is right. This allows frameworks to define generic skeletal applications that can be extended with user-defined code to realise specific applications.

### Interface segregation principle
The **interface segregation principle (ISP)** states that clients should not be forced to depend on interfaces they don’t use. This principle encourages you to replace large, complex interfaces with smaller, more specific ones so that clients only have to know methods that are of interest to them. The intention is to reduce coupling and complexity, making software more flexible and easier to maintain. Smaller, focused interfaces are also more cohesive (fewer reasons to change) and can be reused more easily.

# From System Operations To Detailed Design
In analysis we specify system operations with contracts which establish ‘what’ the operations will accomplish but not ‘how’ they will do this. In design we devise object collaborations to fulfil those specifications – addressing the ‘how’.

Starting from a system operation, we follow these steps:
1.  Identify whether object collaborations are required to verify the precondition or fulfil the postcondition.
2.  Model those collaborations and identify how objects and their links are affected when the system operation is performed.
3.  Based on such collaborations, assign appropriate responsibilities to each class involved and define finer-grained operations in those classes to carry out their responsibilities; contracts may be used when necessary.
4.  Update the class diagram to reflect design choices.


