[<< Back to Behavioral Patterns](index.md)

# Chain of Responsibility
Chain of Responsibility consists of a source of command objects and a series of processing objects. Each processing object contains logic that defines the types of command objects that it can handle; the rest are passed to the next processing object in the chain. A mechanism also exists for adding new processing objects to the end of this chain.

![Chain of Responsibility](https://www.dofactory.com/images/diagrams/net/chain.gif)