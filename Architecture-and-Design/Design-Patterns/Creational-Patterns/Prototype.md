# Prototype

Prototype is used when the type of objects to create is determined by a prototypical instance, which is cloned to produce new objects. This pattern is used to avoid subclasses of an object creator in the client application, like the abstract factory pattern does, and to avoid the inherent cost of creating a new object in the standard way (e.g., using the 'new' keyword) when it is prohibitively expensive for a given application.

To implement the pattern, declare an abstract base class that specifies a pure virtual clone() method. Any class that needs a "polymorphic constructor" capability derives itself from the abstract base class, and implements the clone() operation.  The client, instead of writing code that invokes the "new" operator on a hard-coded class name, calls the clone() method on the prototype, calls a factory method with a parameter designating the particular concrete derived class desired, or invokes the clone() method through some mechanism provided by another design pattern.

![Prototype](https://www.dofactory.com/images/diagrams/net/prototype.gif)