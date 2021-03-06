[<< Back to Behavioral Patterns](index.md)

# Observer
Observer is when an object, called the subject, maintains a list of its dependents, called observers, and notifies them automatically of any state changes, usually by calling one of their methods. After notification, each observer carries out its task via a separate thread as to prevent blocking. It is mainly used to implement distributed event handling systems.  The observer pattern can cause memory leaks, known as the lapsed listener problem, because in basic implementation it requires both explicit registration and explicit deregistration, as in the dispose pattern, because the subject holds strong references to the observers, keeping them alive. This can be prevented by the subject holding weak references to the observers.

![Observer](https://www.dofactory.com/images/diagrams/net/observer.gif)