# Polymorphism

Polymorphism means “one name, many forms”, or the ability to present the same interface for differing underlying forms \(types\). Polymorphism declares a uniform interface that is not type-aware, leaving implementation details to concrete types that implement the interface.  A derived object can be “seen” as the base class in which it inherits from. Polymorphism also provides the mechanism for method overloading.

### Examples

* Integers and floats are implicitly polymorphic since you can add, subtract, multiply and so on, irrespective of the fact that the types are different. 
* Shape is the classic analogy. A triangle, square, circle, and rectangle are both distinct entities and yet at the same time also all shapes. A triangle does not have four sides, and a rectangle is not constrained to equal sizing. However, each entity can be treated as a shape that can be drawn and has a specific geometrical area.  
* An object that implements multiple interfaces is polymorphic, in that the same object can be treated as an implementation for one interface or the other. 
* A MemoryStream can be treated as its base type, Stream.

