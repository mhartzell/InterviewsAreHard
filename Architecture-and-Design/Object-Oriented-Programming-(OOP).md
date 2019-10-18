[<< Back to Architecture and Design](index.md)

# Object-Oriented Programming (OOP)
Object-oriented programming (OOP) is a programming paradigm based on the concept of "objects", which may contain data, in the form of fields, often known as attributes or properties; and code, in the form of procedures, often known as methods.  OOP uses objects to abstract and model a problem domain, making it easier to understand.  A system is therefore represented by a collection of these objects that interact with each other. 

OOP contrasts sharply with the philosophy of Procedural Programming, which uses procedures (also known as routines, subroutines, or functions) which simply contain a series of computational steps to be carried out.

# Main Tenets
The main tenets of Object-Oriented Programming are as follows.

## Abstraction
Abstraction takes a concept or entity and elevates the most useful and relevant aspects while discarding the rest.  Abstraction is critical to managing complexity, and the breaking down of a larger problem into smaller, more manageable components.  Abstraction provides the most useful information to specific audiences.

- Simplifies real-world concepts, allowing their relevant properties to be captured in the data modeling process
- Good applications introduce multiple levels of abstraction
- Abstraction often reduces the complexity at the expense of additional overhead and slower performance.

### Examples
- A programming language is an abstraction over hardware layers.  A programmer uses a language construct rather than directly filling data in CPU registers.  
- An interface is an abstraction of an object.  A public interface provides the accessors and mutators that are relevant to a given audience.  
- A car lot provides an example of abstraction.  The car lot is filled with cars.  The on-site mechanic cares about engine performance and outstanding mechanical problems.  A salesman cares about available features and amenities, as well as the aesthetic presentation of the car.  The lot manager cares about the state of a car’s ownership.  A customer may care about all of the prior details of a car, as well the color.  Each car provides all these details, but not every audience cares about all the details that are available.

## Encapsulation
Encapsulation describes the hiding of both an object's data and behavior from external parties, by restricting access to only an object’s accessors and mutators.  Internal details therefore become irrelevant to external callers, and can be changed without external callers needing to know about those changes.  Encapsulation also prevents external callers from setting the data of an object to an invalid or inconsistent state.  

- An accessor, also known as a getter, is a property or method that provides information about an object to the outside world.  
- A mutator, also known as a setter, is a public method that is used to modify the internal state of an object, while hiding the details of how that object’s data is changed.  
- Encapsulation leads to a cohesive object

## Inheritance
Inheritance is the process of sharing common logic between similar but distinct objects.  One object can inherit behavior, and sometimes data, from another object, without the need to duplicate that behavior.  Additionally, that behavior can be overridden to provide a more specific implementation for the inheriting object.

- Establishes an “is-a” relationship between objects

## Polymorphism
Polymorphism means “one name, many forms”, or the ability to present the same interface for differing underlying forms (data types). Polymorphism declares a uniform interface that is not type-aware, leaving implementation details to concrete types that implement the interface.

- A derived object can be “seen” as the base class in which it inherits from.
- Also provides avenue for method overloading

### Examples
- Integers and floats are implicitly polymorphic since you can add, subtract, multiply and so on, irrespective of the fact that the types are different.
- Shape is the classic analogy.  A triangle, square, circle, and rectangle are both distinct entities and yet at the same time also all shapes.  A triangle does not have four sides, and a rectangle is not constrained to equal sizing.  However, each entity can be treated as a shape that can be drawn and has a specific geometrical area.
- An object that implements multiple interfaces is polymorphic, in that the same object can be treated as an implementation for one interface or the other.  
- A MemoryStream can be treated as its base type, Stream.

# Key Terminology
| Term            | Definition                                                                                                                   |
|-----------------|------------------------------------------------------------------------------------------------------------------------------|
| Abstract Method | A signature with no implementation body, often used to specify that a subclass must provide an implementation of the method. |
| Abstract Type   | A type that cannot be instantiated directly, and may provide no implementation, or an incomplete implementation.             |
|                 |                                                                                                                              |
| Access Modifiers | Keywords in object-oriented languages that set the accessibility of classes, methods, and other members. |
| Base Class | A class from which another class inherits from. |
| Class | A data structure that defines an object, its data, behaviors, and members. |
| Class Interface | The defined public members of a class. |
| Collaboration | "Uses a" - Objects can collaborate with other objects. |
| Composition | "Has a" - Objects can be composed of other objects. |
| Concrete Class | A class having no abstract operations and can be instantiated. |
| Constructor | Code that is executed during the initial instantiation of a class. |
| Coupling | The degree of interdependence between modules, services and objects. |
| Deep Copy | A copy-by-value, where a new entity contains references to identical values stored in new memory allocations. |
| Default Constructor | A constructor with no arguments that assigns default initial values to all data members in a newly created instance of a class. |
| Destructor | A method which is automatically invoked when the object is destroyed. |
| Dynamic Binding | The method being called upon an object or the function being called with arguments is looked up by name at runtime. |
| Dynamic Dispatch | The process of selecting which implementation of a polymorphic operation (method or function) to call at run time. |
| First-Class Citizen | An entity which supports all the operations generally available to other entities, which typically include being passed as an argument, returned from a function, and assigned to a variable. |
| Function | A sequence of program instructions that perform a specific task, packaged as a unit. | 
| Inheritance | "Is a" - Objects can be subtyped. |
| Instantiation | The process of creating (giving a value to) instances from classes. |
| Interface | A defined, contractual, abstract set of properties and methods. |
| Iterator | An object that enables a programmer to traverse a container, particularly lists. |
| Member | The properties,methods and other attributes of a class. |
| Member Variable | A variable that is associated with a specific object, and accessible for all its methods. |
| Message Passing | The fundamental mechanism of program execution by which objects send each other messages. |
| Method | The computations and actions that can be performed by a class. |
| Method Signature | The name and parameters of a class function. |  Does not include return type. |
| Name Binding | The association of entities (data and/or code) with identifiers. | An identifier bound to an object is said to reference that object. |
| Orthogonality | The ability to use various language features in arbitrary combinations with consistent results. |
| Overloading | Methods that have identical names but different method parameters. |
| Overriding | The replacement implementation of a function provided by an inherited object
| Pass-By-Reference | Method of passing an argument that permits the function to refer to the memory holding the original copy of the argument. |
| Pass-By-Value | Method of passing an argument that evaluates the argument and stores this value in the corresponding formal argument, so the function has its own copy of the argument value. |
| Primitive Data Type | Either a data type provided by a programming language as a basic building block (basic type), or a data type for which the programming language provides built-in support. |
| Property | The data members defined by a class. |
| Recursion | A method where the solution to a problem depends on solutions to smaller instances of the same problem. |
| Reflection | The ability of a computer program to examine, introspect, and modify its own structure and behavior at runtime. |
| Scope | The part of a computer program where a name binding is valid, or where the name can be used to refer to the entity. |
| Shallow Copy | A copy-by-reference, where a new entity contains references to existing values in memory. |
| Static | Belongs to the class itself, not to an instance of the class. |
| Strongly Typed | A language that statically resolves types at compile-time, via the compiler. |
| Type | A classification identifying one of various types of data, that determines the possible values for that type, the operations that can be done on values of that type, the meaning of the data, and the way values of that type can be stored. |
| Type Casting | Explicit type conversion which is explicitly defined within program code. |
| Type Coercion | Implicit type conversion via an automatic type conversion by the compiler. |
| Type Conversion | The changing an entity of one data type into another
| Type Checking | The process of verifying and enforcing the constraints of types that may occur either at compile-time (a static check) or at run-time. |
| Type Safety | The extent to which a programming language discourages or prevents the erroneous or undesirable program behavior caused by a discrepancy between differing data types for the program's constants, variables, and methods. |
| Type System | A collection of rules that assign a property called type to various constructs a computer program consists of, such as variables, expressions, functions or modules. | The main purpose of a type system is to reduce possibilities for bugs in computer programs by defining interfaces between different parts of a computer program, and then checking that the parts have been connected in a consistent way. | This checking can happen statically (at compile time), dynamically (at run time), or as a combination of static and dynamic checking. |
| Variable | A storage location paired with an associated symbolic name (an identifier), which contains some known or unknown quantity of information referred to as a value. |
| Virtual Function | An inheritable and overridable function or method for which dynamic dispatch is facilitated. |
| Weakly Typed | A language that dynamically resolves types at run-time. | 
| Weak Reference | A reference that does not protect the referenced object from collection by a garbage collector, unlike a strong reference. |

# References
- [Glossary of Object-Oriented Terms](https://www.clear.rice.edu/mech517/Books/oop14.pdf)
- [Index of Object-Oriented Programming Articles](https://en.wikipedia.org/wiki/Index_of_object-oriented_programming_articles)
- [Object-Oriented Programming (OOP)](https://en.wikipedia.org/wiki/Object-oriented_programming)
