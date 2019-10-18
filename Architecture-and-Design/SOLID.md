[<< Back to Architecture and Design](index.md)

# SOLID
SOLID was introduced by Michael Feathers for the "first five principles" named by Robert C. Martin that stands for five basic principles of object-oriented programming and design. The intention is that these principles, when applied together, will make it more likely that a programmer will create a system that is easy to maintain and extend over time. The principles of SOLID are guidelines that can be applied while working on software to remove code smells by providing a framework through which the programmer may refactor the software's source code until it is both legible and extensible. 

# Main Tenets

## Single-Responsibility Principle
A class should have one, and only one, reason to change.  Every module or class should have responsibility over a single part of the functionality provided by the software, and that responsibility should be entirely encapsulated by the class.

- Single-responsibility moves towards a cohesive design, typically leading to smaller and simpler classes.
- A change in responsibility requires a class to change, which may break existing functionality.  When a class has multiple responsibilities, changes to one set of responsibilities could break other responsibilities
- Can go overboard and violate encapsulation.  Level of granularity for class responsibility is subjective and influenced by the problem domain.

### Examples
- A report has data and a way to display that data.  The presentation of the report’s data is a separate responsibility from the collection of that data.

## Open-Closed Principle
Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.  An entity can allow its behaviour to be extended without modifying its source code.

- A module will be said to be open if it is still available for extension. For example, it should be possible to add fields to the data structures it contains, or new elements to the set of functions it performs.
- A module will be said to be closed if it is available for use by other modules. This assumes that the module has been given a well-defined, stable description (the interface in the sense of information hiding).
- It is much easier to write new code than to try to change existing code that has dependencies.

## Liskov Substitution Principle
A derived classes must be substitutable for its base classes:  in a computer program, if B is a subtype of A, then objects of type A may be replaced with objects of type B (i.e., an object of the type A may be substituted with its subtype object of the type B) without altering any of the desirable properties of that program (correctness, task performed, etc).

- The substitution principle is a semantic rather than merely syntactic relation because it intends to guarantee semantic interoperability of types in a hierarchy
- All types have an explicit contract (visible members, methods, properties, etc) and an implicit contract (a set of assumptions around how those members behave).  LSP can be violated through either.
- The principle can generally only be violated by classes with mutators.

## Interface Segregation Principle
No client should be forced to depend on methods it does not use.  

- ISP splits interfaces that are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them.
- Make thin interfaces that pertain to the needs of specific kinds of consumers

## Dependency Inversion Principle
High-level modules should not depend on low-level modules. Both should depend on abstractions.
Additionally, abstractions should not depend on details. Details should depend on abstractions.

- Always depend on abstract classes or interfaces, not concrete types
- Greatly increases the amount of loose coupling in a system.
- Typically enforced through an Inversion of Control container.

### Examples
- A domain layer should not depend directly on a data access layer.  A domain layer should depend on an abstracted service interface, which the data access implements.  The data layer is then injected into the domain layer.

# References
- [SOLID (object-oriented design)](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design))
