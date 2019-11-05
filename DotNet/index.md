[<< Back to the top](../readme.md)

# .NET
.NET is a general purpose development ecosystem.  It supports multiple programming languages and target platforms for deployment.  A .NET application is developed and runs in one or more implementations of .NET.

# Table of Contents
- [Architecture](Architecture.md)
- [Asynchronous Programming](Asynchronous-Programming.md)
- [C#](C-Sharp/index.md)
- [Delegates](Delegates.md)
- [F#](F-Sharp/index.md)
- [Garbage Collection](Garbage-Collection.md)
- [Generics](Generics.md)
- [LINQ](Linq.md)
- [Multithreaded Programming](Multithreaded-Programming.md)

# High-Level Features

## Assemblies
.NET uses a binary file format that is used to fully-describe and contain .NET programs.  The assembly file format is fully-specified and standardized as ECMA 335, which all .NET compilers and runtimes use.  It is CPU- and OS-agnostic.  

## Automatic Memory Management
.NET uses [garbage collection](Garbage-Collection.md) to provide automatic memory management for applications.  The GC operatoes on a lazy approach to memory management, and ensures memory safety by allowing a program to only access memory it has been allocated.  

## Type Safety
.NET enforces type safety.  The only operations allowed for a given object are those of its type, and all other calls result in a compile-time or run-time error.  Additionally, the .NET runtime only allows object casts and calls that align within a given object’s inheritance hierarchy.  Type safety is also responsible for enforcing encapsulation by guaranteeing the fidelity of access modifiers.  Type inference is implemented via the `var` keyword.

## Unmanaged Resources
Objects may reference unmanaged resources, which are not automatically maintained by the .NET runtime.  Unmanaged resources implement the IDisposable interface for automatic clean-up.  The using statement instructs .NET when to automatically perform this clean-up, even when an exception is generated before execution completion. 

## Delegates and Lambdas
[Delegates](Delegates.md) define a type that specifies a specific method signature, and serve as a function pointer.  Any method with the same signature can be assigned to the delegate and executed when the delegate is invoked.

## Collections
Some common data structures in the collections namespace:

| Legacy        | Generic | 
| ------------- | ------- |
| `ArrayList`   | `Dictionary<TKey, TValue>` |
| `Hashtable`   | `List<T>` |
| `Queue`       | `Queue<T>` |
| `Stack`       | `SortedList<TKey, TValue>` |
|               | `Stack<T>` |
 
## Generics
[Generics](Generics.md) are code templates which allow a developer to introduce a type-safe data structure in classes and functions (called a type parameter) without committing to an actual data type.  The client specifies the exact type to use in place of the parameter.  They can be used without incurring the cost or risk of runtime casts or boxing operations.

## Asynchronous Programming
[Asynchronous Programming](Asynchronous-Programming.md) is a first-class citizen in .NET, following the task-based asynchronous pattern and introducing language constructs that bring single-threaded cooperative multitasking to C#.  The core of the model are the `Task` (a single operation which does not return a value) and `Task<T>` (a single operation which returns a value of type `T`) objects, which model asynchronous operations. They are supported by the `async` and `await` keywords. 

## Language-Integrated Query (LINQ)
[LINQ](Linq.md) allows the creation of declarative code for operating on data as a first-class language construct.  It provides language-level querying capabilities and a higher-order function API.  It is especially useful for data access, as LINQ abstracts common elements of data access into a query syntax which looks the same no matter which data source you pick.

## Native Interoperability
.NET provides several ways to call API operating system APIs.  At times, this may necessitate the use of unsafe code, which loses the benefit of garbage collection and type safety.  