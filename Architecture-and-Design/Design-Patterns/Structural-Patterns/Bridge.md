[<< Back to Structural Patterns](index.md)

# Bridge
Bridge decouples an abstraction from its implementation so that the two can vary independently.  The interface class contains a reference to the abstract implementation class. This reference is initialized with an instance of a concrete implementation class, but all subsequent interaction from the interface class to the implementation class is limited to the abstraction maintained in the implementation base class. The client interacts with the interface class, and it in turn delegates all requests to the implementation class.

![Bridge](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cf/Bridge_UML_class_diagram.svg/500px-Bridge_UML_class_diagram.svg.png)