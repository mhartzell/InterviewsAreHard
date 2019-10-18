[<< Back to Behavioral Patterns](index.md)

# Mediator
Mediator encapsulates how a set of objects interact. Usually a program is made up of a large number of classes. However, as more classes are developed in a program, especially during maintenance and/or refactoring, the problem of communication between these classes may become more complex. This makes the program harder to read and maintain. Furthermore, it can become difficult to change the program, since any change may affect code in several other classes.

With the mediator pattern, communication between objects is encapsulated with a mediator object. Objects no longer communicate directly with each other, but instead communicate through the mediator. This reduces the dependencies between communicating objects, thereby lowering the coupling.

![Mediator](https://www.dofactory.com/images/diagrams/net/mediator.gif)