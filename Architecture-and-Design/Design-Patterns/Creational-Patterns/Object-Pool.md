[<< Back to Creational Patterns](index.md)

# Object Pool
Object pool uses a set of initialized objects kept ready to use – a "pool" – rather than allocating and destroying them on demand. A client of the pool will request an object from the pool and perform operations on the returned object. When the client has finished, it returns the object to the pool rather than destroying it; this can be done manually or automatically.  Object pools are primarily used for performance.