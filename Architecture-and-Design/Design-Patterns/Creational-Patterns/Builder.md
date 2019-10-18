[<< Back to Creational Patterns](index.md)

# Builder
The intent of the Builder design pattern is to separate the construction of a complex object from its representation. By doing so the same construction process can create different representations.

A "director" invokes builder services to build up a composite object. The builder creates part of the complex object each time it is called and maintains all intermediate state. When the product is finished, the client retrieves the result from the builder.

Builder affords finer control over the construction process. Unlike creational patterns that construct products in one shot, the Builder pattern constructs the product step by step under the control of the director.

![Builder](https://www.dofactory.com/images/diagrams/net/builder.gif)