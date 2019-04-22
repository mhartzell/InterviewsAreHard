# The Operating System

# Process
A process is an instance of a running program that is isolated from other processes on the same machine.  It has its own private section of memory.  Sharing of memory between processes is possible but not typical.

As an abstraction, a process is a **virtual machine**.

# Thread
A thread is the smallest sequence of programmed instructions that can be managed independently by a scheduler.  In most cases, a thread is a child of a process.  Multiple threads can be executed concurrently and share memory and other resources.  

As an abstraction, a thread is a **virtual processor**.

# References
- [Process (computer)](https://en.wikipedia.org/wiki/Process_(computing))
- [Thread (computing)](https://en.wikipedia.org/wiki/Thread_(computing))
