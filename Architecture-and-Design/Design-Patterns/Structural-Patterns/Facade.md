[<< Back to Structural Patterns](index.md)

# Facade
Facade is an object that provides a simplified interface to a larger body of code, such as a class library.  This pattern hides the complexities of the larger system and provides a simpler interface to the client. It typically involves a single wrapper class which contains a set of members required by client. These members access the system on behalf of the facade client and hide the implementation details.