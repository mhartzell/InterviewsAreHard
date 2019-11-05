[<< Back to .NET](index.md)

# Garbage Collection
In the CLR, the garbage collector is an automatic memory manager.  It allocates and frees memory, manages the heap efficiently, reclaims objects that are no longer used, and provides memory safety by ensuring one object cannot access the memory of another object.  

# Conditions for Collection
GC occurs when the system has low physical memory, the memory that is used by allocated objects on the heap surpasses an acceptable threshold, or the GC.Collect method is called.

# The Managed Heap
The GC allocates a segment of memory to store objects.  This managed heap is not the native heap in the OS.  Each process has its own heap.  The fewer objects on the heap, the less work the GC has to do.  When collection is triggered, the GC reclaims memory used by dead objects, and also compacts live objects so they are moved together. 

The heap can be broken into two components: the large object heap and the small object heap.  The large contains objects that are 85,000 bytes and large (usually arrays).

# Generations
The heaps is organized into generations: 

- Generation 0 (short-lived objects)
- Generation 1 (buffer between short-lived and long-lived)
- Generation 2 (long-lived objects).  

Newly allocated objects are implicitly gen 0, unless they are large objects, in which case they go on the large object heap / gen 2.  A collection occurs on a generation, plus all younger generations (thus, a gen 2 collection is a full collection).

Objects that are not reclaimed are known as survivors and are promoted to the next generation.

# Collection Process
The GC has three phases: 

- During marking, it creates a list of all live objects.  
- During relocating, it updates references of objects that will be compacted.  
- During compacting, it compacts survivors and reclaims dead space.  

Survivors are moved to older generations / segments.  During collection, all threads are suspended, except for the thread that triggered collection.

By default, the large object heap is not compacted.

# References
- [Fundamentals of Garage Collection](https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/fundamentals)
