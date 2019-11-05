[<< Back to .NET](index.md)

# Asynchronous Programming
Asynchronous Programming is a first-class citizen in .NET, providing support for I/O-bound and CPU-bound operations that can be performed in the background.  Async programming follows the task-based asynchronous pattern and introduces language constructs that bring single-threaded, cooperative multitasking to C#.  

The core of the model are the `Task` (a single operation which does not return a value) and `Task<T>` (a single operation which returns a value of type `T`) objects, which abstract asynchronous operations. They are supported by the `async` and `await` language keywords. 

# Task and Task\<T\>
Tasks are constructs used to implement the Promise Model of Concurrency.  A Task is a promise that work will be completed at some point in the future, and additionally provides an API for dealing with asynchronous operations.   While the Task is completing, the application can perform other useful work by yielding control back to its caller, without the need for callbacks or event handlers.  Note that this does not constitute and exit from the method.  When the Task is finished, the result value will be unwrapped for you automatically.

By default, Tasks execute on the current thread and delegate work to the OS as appropriate.  They can optionally be executed on a new thread.  However, by default there is no single thread dedicated to running the task.  Rather, the .NET runtime hands off the operation to the OS, and the OS uses asynchronous operations (interrupts, driver requests, queuing, etc) to perform the requested action.  This approach can use one or many threads, and there is no single thread **waiting** for an operation to complete.

For server scenarios, this increases throughput by allowing the server to process additional requests while it is waiting for a Task to complete.  The client also has increased responsiveness by not blocking on bound operations.  Both gain improved efficiency by not directly creating new threads, which is an expensive operation, especially if the operation happens to be I/O-bound.  In that scenario, creating a new CPU thread that does little work is inefficient.  

## CPU-Bound Operations
CPU-bound operations are a bit different, as there is no way around dedicating a thread to the Task.  `await` provides a clean way to interact with the background thread and keep the caller responsive.  Shared data will still need an appropriate synchronization strategy.  

# Async and Await
Asynchronous methods are declared so by applying the `async` keyword to the function definition.  Within the asynchronous method, use of the `await` keyword tells the compiler that the asynchronous method can’t continue past that point until the awaited asynchronous process is complete.  An `async` method that does not use `await` in its method body will run as as synchronous method.  

An `async` method with a return type of `void` cannot be awaited, and the caller of a void-returning method can't catch any exceptions that the method throws.  



# References
- [Asynchronous Programming with async and await (C#)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/async/)
- [Async Overview](https://docs.microsoft.com/en-us/dotnet/standard/async)
- [Control Flow in Async Programs (C#)](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/async/control-flow-in-async-programs)
- [Eric Lippert Async Blog Posts](https://blogs.msdn.microsoft.com/ericlippert/tag/async/)
- [Futures and Promises](https://en.wikipedia.org/wiki/Futures_and_promises)