[<< Back to .NET](index.md)

# Generics
Generics are code templates which allow a developer to introduce a type-safe data structure in classes and functions (called a type parameter) without committing to an actual data type.  The client specifies the exact type to use in place of the parameter.  They can be used without incurring the cost or risk of runtime casts or boxing operations.

Prior to the release of generics, collections stored all elements as objects.  A silent boxing operation occurred when elements were added, and specific unboxing operations were required to access the concrete types of the collected elements upon read.  These operations hinder performance, as well as create fragile code.  Generics allow for static type checking at compile-time.

## Constraints
When you define a generic class, you can apply restrictions to the kinds of types that client code can use for type arguments when it instantiates your class. If client code tries to instantiate your class by using a type that is not allowed by a constraint, the result is a compile-time error.
- `where T: struct` - The type argument must be a value type. Any value type except Nullable can be specified. See Using Nullable Types (C# Programming Guide) for more information.
- `where T : class` - The type argument must be a reference type; this applies also to any class, interface, delegate, or array type.
where T : new() - The type argument must have a public parameterless constructor. When used together with other constraints, the new() constraint must be specified last.
- `where T : <BaseClassName>` - The type argument must be or derive from the specified base class.
- `where T : <InterfaceName>` - The type argument must be or implement the specified interface. Multiple interface constraints can be specified. The constraining interface can also be generic.
- `where T : U` - The type argument supplied for T must be or derive from the argument supplied for U.

By constraining the type parameter, you increase the number of allowable operations and method calls to those supported by the constraining type and all types in its inheritance hierarchy. Therefore, when you design generic classes or methods, if you will be performing any operation on the generic members beyond simple assignment or calling any methods not supported by `System.Object`, you will have to apply constraints to the type parameter.

## IL Generation
For value types, the runtime creates new IL for each instance per value type.  e.g., duplicate IL will not be created for multiple instances of `Stack<int>`, but IL will be created for `Stack<int>` and `Stack<long>`, with the appropriate type substituted.  

For reference types, only ONE specialized set of IL will be created, regardless of how many reference types use a generic.  This is because references are the same size, regardless of the types of objects they reference.