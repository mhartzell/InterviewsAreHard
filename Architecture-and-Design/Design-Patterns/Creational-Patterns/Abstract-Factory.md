# Abstract Factory
Abstract Factory provides a level of indirection that abstracts the creation of families of related or dependent objects without directly specifying their concrete classes. The "factory" object has the responsibility for providing creation services for the entire platform family. Clients never create platform objects directly, they ask the factory to do that for them.

This mechanism makes exchanging product families easy because the specific class of the factory object appears only once in the application - where it is instantiated (usually as a singleton). The application can wholesale replace the entire family of products simply by instantiating a different concrete instance of the abstract factory.

![Abstract Factory](https://www.dofactory.com/images/diagrams/net/abstract.gif)