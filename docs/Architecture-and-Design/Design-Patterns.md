# Design Patterns

A software design pattern is a general reusable solution to a commonly occurring problem within a given context in software design. It is not a finished design that can be transformed directly into source or machine code. It is a description or template for how to solve a problem that can be used in many different situations. Design patterns are formalized best practices that the programmer can use to solve common problems when designing an application or system.

# Creational Patterns

Creational design patterns are design patterns that deal with object creation mechanisms. The basic form of object creation could result in design problems or added complexity to the design. Creational design patterns solve this problem by controlling this object creation.

Creational design patterns are composed of two dominant ideas. One is encapsulating knowledge about which concrete classes the system uses. Another is hiding how instances of these concrete classes are created and combined.

## Abstract Factory
Abstract Factory provides a level of indirection that abstracts the creation of families of related or dependent objects without directly specifying their concrete classes. The "factory" object has the responsibility for providing creation services for the entire platform family. Clients never create platform objects directly, they ask the factory to do that for them.

This mechanism makes exchanging product families easy because the specific class of the factory object appears only once in the application - where it is instantiated (usually as a singleton). The application can wholesale replace the entire family of products simply by instantiating a different concrete instance of the abstract factory.

![Abstract Factory](https://www.dofactory.com/images/diagrams/net/abstract.gif)

## Builder

The intent of the Builder design pattern is to separate the construction of a complex object from its representation. By doing so the same construction process can create different representations.

A "director" invokes builder services to build up a composite object. The builder creates part of the complex object each time it is called and maintains all intermediate state. When the product is finished, the client retrieves the result from the builder.

Builder affords finer control over the construction process. Unlike creational patterns that construct products in one shot, the Builder pattern constructs the product step by step under the control of the director.

![Builder](https://www.dofactory.com/images/diagrams/net/builder.gif)

## Factory Method

The Factory Method pattern uses factory methods to deal with the problem of creating objects without having to specify the exact class of the object that will be created. This is done by creating objects by calling a factory method—either specified in an interface and implemented by child classes, or implemented in a base class and optionally overridden by derived classes—rather than by calling a constructor.

![Factory Method](https://www.dofactory.com/images/diagrams/net/factory.gif)

## Lazy Initialization (Lazy Loading)

Lazy initialization is the tactic of delaying the creation of an object, the calculation of a value, or some other expensive process until the first time it is needed.  This is typically accomplished by augmenting a variable's accessor method (or property definition) to check for a previously-created instance. If none exists a new instance is created, placed into the variable, and this new object is returned to the caller in a just-in-time fashion. In this manner object creation is deferred until first use which can, in some circumstances (e.g., sporadic object access), increase system responsiveness and speed startup by bypassing large-scale object preallocation.

## Object Pool

Object pool uses a set of initialized objects kept ready to use – a "pool" – rather than allocating and destroying them on demand. A client of the pool will request an object from the pool and perform operations on the returned object. When the client has finished, it returns the object to the pool rather than destroying it; this can be done manually or automatically.  Object pools are primarily used for performance.

## Prototype

Prototype is used when the type of objects to create is determined by a prototypical instance, which is cloned to produce new objects. This pattern is used to avoid subclasses of an object creator in the client application, like the abstract factory pattern does, and to avoid the inherent cost of creating a new object in the standard way (e.g., using the 'new' keyword) when it is prohibitively expensive for a given application.

To implement the pattern, declare an abstract base class that specifies a pure virtual clone() method. Any class that needs a "polymorphic constructor" capability derives itself from the abstract base class, and implements the clone() operation.  The client, instead of writing code that invokes the "new" operator on a hard-coded class name, calls the clone() method on the prototype, calls a factory method with a parameter designating the particular concrete derived class desired, or invokes the clone() method through some mechanism provided by another design pattern.

![Prototype](https://www.dofactory.com/images/diagrams/net/prototype.gif)

## Singleton

Singleton restricts the instantiation of a class to one object. This is useful when exactly one object is needed to coordinate actions across the system. The concept is sometimes generalized to systems that operate more efficiently when only one object exists, or that restrict the instantiation to a certain number of objects. The term comes from the mathematical concept of a singleton.

There are some who are critical of the singleton pattern and consider it to be an anti-pattern in that it is frequently used in scenarios where it is not beneficial, introduces unnecessary restrictions in situations where a sole instance of a class is not actually required, and introduces global state into an application.

![Singleton](https://www.researchgate.net/profile/Armando_Rene_Narvaez_Contreras/publication/314175216/figure/fig8/AS:467513608806409@1488475338499/Singleton-pattern-class-diagram.png)

# Structural Patterns

Structural design patterns ease the design by identifying a simple way to realize relationships between entities.

## Adapter (Wrapper)

Adapter allows the interface of an existing class to be used as another interface. It is often used to make existing classes work with others without modifying their source code.  Adapter is about creating an intermediary abstraction that translates, or maps, the old component to the new system. Clients call methods on the Adapter object which redirects them into calls to the legacy component. This strategy can be implemented either with inheritance or with aggregation.

![Adapter](https://www.dofactory.com/images/diagrams/net/adapter.gif)

## Bridge

Bridge decouples an abstraction from its implementation so that the two can vary independently.  The interface class contains a reference to the abstract implementation class. This reference is initialized with an instance of a concrete implementation class, but all subsequent interaction from the interface class to the implementation class is limited to the abstraction maintained in the implementation base class. The client interacts with the interface class, and it in turn delegates all requests to the implementation class.

![Bridge](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cf/Bridge_UML_class_diagram.svg/500px-Bridge_UML_class_diagram.svg.png)

## Composite

Composite describes that a group of objects is to be treated in the same way as a single instance of an object. The intent of a composite is to "compose" objects into tree structures to represent part-whole hierarchies. Implementing the composite pattern lets clients treat individual objects and compositions uniformly.

![Composite](https://www.dofactory.com/images/diagrams/net/composite.gif)

## Decorator

Decorator allows behavior to be added to an individual object, either statically or dynamically, without affecting the behavior of other objects from the same class.

![Decorator](https://www.dofactory.com/images/diagrams/net/decorator.gif)

## Facade

Facade is an object that provides a simplified interface to a larger body of code, such as a class library.  This pattern hides the complexities of the larger system and provides a simpler interface to the client. It typically involves a single wrapper class which contains a set of members required by client. These members access the system on behalf of the facade client and hide the implementation details.

## Flyweight

Flyweight is an object that minimizes memory use by sharing as much data as possible with other similar objects; it is a way to use objects in large numbers when a simple repeated representation would use an unacceptable amount of memory. Often some parts of the object state can be shared, and it is common practice to hold them in external data structures and pass them to the flyweight objects temporarily when they are used.

![Flyweight](https://www.dofactory.com/images/diagrams/net/flyweight.gif)

## Marker

Marker provides a means to associate metadata with a class where the language does not have explicit support for such metadata.  A class implements a marker interface (also called tagging interface), and methods that interact with instances of that class test for the existence of the interface. Whereas a typical interface specifies functionality (in the form of method declarations) that an implementing class must support, a marker interface need not do so. The mere presence of such an interface indicates specific behavior on the part of the implementing class.

C# implements this pattern through custom attributes.

## Proxy

Proxy is a wrapper or agent object that is being called by the client to access the real serving object behind the scenes. Use of the proxy can simply be forwarding to the real object, or can provide additional logic. In the proxy extra functionality can be provided, for example caching when operations on the real object are resource intensive, or checking preconditions before operations on the real object are invoked. For the client, usage of a proxy object is similar to using the real object, because both implement the same interface.

![Proxy](https://www.dofactory.com/images/diagrams/net/proxy.gif)

# Behavioral Patterns

Behavioral design patterns identify common communication patterns between objects and realize these patterns. By doing so, these patterns increase flexibility in carrying out this communication.

## Chain of Responsibility

Chain of Responsibility consists of a source of command objects and a series of processing objects. Each processing object contains logic that defines the types of command objects that it can handle; the rest are passed to the next processing object in the chain. A mechanism also exists for adding new processing objects to the end of this chain.

![Chain of Responsibility](https://www.dofactory.com/images/diagrams/net/chain.gif)

## Command

Command is an object which is used to encapsulate all information needed to perform an action or trigger an event at a later time. This information includes the method name, the object that owns the method and values for the method parameters.

Four terms always associated with the command pattern are command, receiver, invoker and client. A command object knows about receiver and invokes a method of the receiver. Values for parameters of the receiver method are stored in the command. The receiver then does the work. An invoker object knows how to execute a command, and optionally does bookkeeping about the command execution. The invoker does not know anything about a concrete command, it knows only about command interface. Both an invoker object and several command objects are held by a client object. The client decides which commands to execute at which points. To execute a command, it passes the command object to the invoker object.

![Command](https://www.dofactory.com/images/diagrams/net/command.gif)

## Interpreter

Interpreter how to evaluate sentences in a language. The basic idea is to have a class for each symbol (terminal or nonterminal) in a specialized computer language. The syntax tree of a sentence in the language is an instance of the composite pattern and is used to evaluate (interpret) the sentence for a client.

![Interpreter](https://www.dofactory.com/images/diagrams/net/interpreter.gif)

## Iterator

Iterator provides a way to access the elements of an aggregate object sequentially without exposing its underlying representation.  The iterator pattern decouples algorithms from containers; in some cases, algorithms are necessarily container-specific and thus cannot be decoupled.

![Iterator](https://www.dofactory.com/images/diagrams/net/iterator.gif)

## Mediator

Mediator encapsulates how a set of objects interact. Usually a program is made up of a large number of classes. However, as more classes are developed in a program, especially during maintenance and/or refactoring, the problem of communication between these classes may become more complex. This makes the program harder to read and maintain. Furthermore, it can become difficult to change the program, since any change may affect code in several other classes.

With the mediator pattern, communication between objects is encapsulated with a mediator object. Objects no longer communicate directly with each other, but instead communicate through the mediator. This reduces the dependencies between communicating objects, thereby lowering the coupling.

![Mediator](https://www.dofactory.com/images/diagrams/net/mediator.gif)

## Memento

Memento provides the ability to restore an object to its previous state (undo via rollback).  The memento pattern is implemented with three objects: the originator, a caretaker and a memento. The originator is some object that has an internal state. The caretaker is going to do something to the originator, but wants to be able to undo the change. The caretaker first asks the originator for a memento object. Then it does whatever operation (or sequence of operations) it was going to do. To roll back to the state before the operations, it returns the memento object to the originator. The memento object itself is an opaque object (one which the caretaker cannot, or should not, change). When using this pattern, care should be taken if the originator may change other objects or resources - the memento pattern operates on a single object.

![Memento](https://www.dofactory.com/images/diagrams/net/memento.gif)

## Observer

Observer is when an object, called the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods. After notification, each observer carries out its task via a separate thread as to prevent blocking. It is mainly used to implement distributed event handling systems.  The observer pattern can cause memory leaks, known as the lapsed listener problem, because in basic implementation it requires both explicit registration and explicit deregistration, as in the dispose pattern, because the subject holds strong references to the observers, keeping them alive. This can be prevented by the subject holding weak references to the observers.

![Observer](https://www.dofactory.com/images/diagrams/net/observer.gif)

## State

State implements a state machine in an object-oriented way. With the state pattern, a state machine is implemented by implementing each individual state as a derived class of the state pattern interface, and implementing state transitions by invoking methods defined by the pattern's superclass. The state pattern can be interpreted as a strategy pattern which is able to switch the current strategy through invocations of methods defined in the pattern's interface.

![State](https://www.dofactory.com/images/diagrams/net/state.gif)

## Strategy

Strategy enables an algorithm's behavior to be selected at runtime. The strategy pattern defines a family of algorithms, encapsulates each algorithm, and makes the algorithms interchangeable within that family. Strategy lets the algorithm vary independently from clients that use it.

![Strategy](https://www.dofactory.com/images/diagrams/net/strategy.gif)

## Template Method

Template Method defines the program skeleton of an algorithm in an operation, deferring some steps to subclasses. It lets one redefine certain steps of an algorithm without changing the algorithm's structure.

![Template Method](https://www.dofactory.com/images/diagrams/net/template.gif)

## Visitor

Visitor is a way of separating an algorithm from an object structure on which it operates. A practical result of this separation is the ability to add new operations to existing object structures without modifying those structures. It is one way to follow the open/closed principle.

In essence, the visitor allows one to add new virtual functions to a family of classes without modifying the classes themselves; instead, one creates a visitor class that implements all of the appropriate specializations of the virtual function. The visitor takes the instance reference as input, and implements the goal through double dispatch.

![Visitor](https://www.dofactory.com/images/diagrams/net/visitor.gif)

# Enterprise Patterns
- MVP
- MVVM
- MVC
- Active Record
- Data Mapper
- Domain Model
- Identity Field
- Repository
- Separated Interface
- Service Layer
- Unit of Work

# Anti-Patterns
- Big ball of mud
- Gold plating
- Interface bloat
- God object
- Error hiding
- Hard code
- Lava flow
- Magic strings

# References
- [.NET Design Patterns](http://www.dofactory.com/net/design-patterns)
- [Design Patterns](https://sourcemaking.com/design_patterns)
- [Software design pattern](https://en.wikipedia.org/wiki/Software_design_pattern)
