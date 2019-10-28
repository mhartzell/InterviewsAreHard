[<< Back to .NET](index.md)

# Multithreaded Programming
See [Parallel Programming](/docs/The-Basics/Parallel-Programming.md) for an overview of Multithreaded Programming.

# Lock Keyword
The **lock** keyword in .NET help to synchronize multhreaded access to shared resources, by insuring that only a single thread can access that resource at a time.  However, the **lock** keyword does not discriminate between read operations and write operations.  

# ReaderWriterLockSlim
The **ReaderWriterLockSlim** class can provide concurrent access to a shared resource for reads, while only allowing a single thread to access the resource for write operations.
