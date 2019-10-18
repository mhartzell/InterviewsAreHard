[<< Back to Structural Patterns](index.md)

# Adapter (Wrapper)
Adapter allows the interface of an existing class to be used as another interface. It is often used to make existing classes work with others without modifying their source code.  Adapter is about creating an intermediary abstraction that translates, or maps, the old component to the new system. Clients call methods on the Adapter object which redirects them into calls to the legacy component. This strategy can be implemented either with inheritance or with aggregation.

![Adapter](https://www.dofactory.com/images/diagrams/net/adapter.gif)