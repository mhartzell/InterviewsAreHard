# Object-Oriented Programming (OOP)

Object-oriented programming (OOP) is a programming paradigm based on the concept of "objects", which may contain data, in the form of fields, often known as attributes or properties; and code, in the form of procedures, often known as methods.  OOP uses objects to abstract and model a problem domain, making it easier to understand.  A system is therefore represented by a collection of these objects that interact with each other. 

OOP contrasts sharply with the philosophy of Procedural Programming, which uses procedures (also known as routines, subroutines, or functions) which simply contain a series of computational steps to be carried out.

# Main Tenets
The main tenets of Object-Oriented Programming are as follows.

# Abstraction
Abstraction takes a concept or entity and elevates the most useful and relevant aspects while discarding the rest.  Abstraction is critical to managing complexity, and the breaking down of a larger problem into smaller, more manageable components.  Abstraction provides the most useful information to specific audiences.

- Simplifies real-world concepts, allowing their relevant properties to be captured in the data modeling process
- Good applications introduce multiple levels of abstraction
- Abstraction often reduces the complexity at the expense of additional overhead and slower performance.

## Examples
- A programming language is an abstraction over hardware layers.  A programmer uses a language construct rather than directly filling data in CPU registers.  
- An interface is an abstraction of an object.  A public interface provides the accessors and mutators that are relevant to a given audience.  
- A car lot provides an example of abstraction.  The car lot is filled with cars.  The on-site mechanic cares about engine performance and outstanding mechanical problems.  A salesman cares about available features and amenities, as well as the aesthetic presentation of the car.  The lot manager cares about the state of a car’s ownership.  A customer may care about all of the prior details of a car, as well the color.  Each car provides all these details, but not every audience cares about all the details that are available.

# Encapsulation
Encapsulation describes the hiding of both an object's data and behavior from external parties, by restricting access to only an object’s accessors and mutators.  Internal details therefore become irrelevant to external callers, and can be changed without external callers needing to know about those changes.  Encapsulation also prevents external callers from setting the data of an object to an invalid or inconsistent state.  

- An accessor, also known as a getter, is a property or method that provides information about an object to the outside world.  
- A mutator, also known as a setter, is a public method that is used to modify the internal state of an object, while hiding the details of how that object’s data is changed.  
- Encapsulation leads to a cohesive object

# Inheritance
Inheritance is the process of sharing common logic between similar but distinct objects.  One object can inherit behavior, and sometimes data, from another object, without the need to duplicate that behavior.  Additionally, that behavior can be overridden to provide a more specific implementation for the inheriting object.

- Establishes an “is-a” relationship between objects

# Polymorphism
Polymorphism means “one name, many forms”, or the ability to present the same interface for differing underlying forms (data types). Polymorphism declares a uniform interface that is not type-aware, leaving implementation details to concrete types that implement the interface.

- A derived object can be “seen” as the base class in which it inherits from.
- Also provides avenue for method overloading

## Examples
- Integers and floats are implicitly polymorphic since you can add, subtract, multiply and so on, irrespective of the fact that the types are different.
- Shape is the classic analogy.  A triangle, square, circle, and rectangle are both distinct entities and yet at the same time also all shapes.  A triangle does not have four sides, and a rectangle is not constrained to equal sizing.  However, each entity can be treated as a shape that can be drawn and has a specific geometrical area.
- An object that implements multiple interfaces is polymorphic, in that the same object can be treated as an implementation for one interface or the other.  
- A MemoryStream can be treated as its base type, Stream.
