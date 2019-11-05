[<< Back to The Basics](index.md)

# Parallel Programming
There are a variety of ways to harness the the computer's ability to execute operations in parallel.

Consider an example where you are cooking in a restaurant.  An order comes in for eggs and toast.  In a synchronous context, you would cook the eggs, and when the eggs are finished, you would cook the toast.  You would then put the eggs and the toast on a plate and serve the meal.

# Asynchronous Programming
Asynchronous programming is about **tasks**.   As an asynchonrous cook,  you would start cooking the eggs and set a timer.  You would then start the toast cooking, and set another timer.  While both are cooking would you clean the sink.  When the timers go off, you put the eggs on a plate and the toast on a plate and serve them.  

In asynchronous single-threaded workflows you have a graph of tasks where some tasks depend on the results of others; as each task completes it invokes the code that schedules the next task that can run, given the results of the just-completed task.  However, this often requires just one worker to perform all tasks.

# Multithreaded Programming
Multithreaded programming is about **workers**.  As a multithreaded cook, you would hire two more cooks, one of which will cook eggs and one of which will cook toast.  You now need to figure out how to coordinate the cooks so that they do not conflict with one another when using shared resources in the kitchen.  You also have to pay the cooks.

In multithreaded workflows you assign tasks to workers.  Many tasks are not processor-bound, but if they are, it makes sense to use as many worker threads as there are processors to work in parallel.

## Synchronization Challenges
Multithreaded operations must synchronize access to share resources, as problems can occur when multiple threads try to modify these resources at the same time.

### Race Conditions
A race condition occurs when the correctedness of a program depends on the relative timing of events in two or more concurrent operations.

### Lost Update
An operation writes a value.  A second operation concurrently writes a second value on top of the first.  The first value is now lost to any additional concurrent operations which require the first value rather than the second.  Those operations will have incorrect results at the end of processing.

### Dirty Read
An operation may attempt to write a value, but for whatever reason it fails or aborts.  This value should no longer exist in the system.  A dirty read occurs when other concurrent operations read this value before the first operation aborts.

### Incorrect Summary
One operation reads a summary over the values of all instances of a repeated value, while a second concurrent operation updates some instances of that value. The resulting summary does not reflect a correct result for any precedence order between the two operations, but rather a random result dependent upon timing.

### Deadlock
Deadlock occurs when one operation is waiting for the completion of a second operation, while the second is waiting on the completion of the first.  

# Concurrency
Concurrency the ability of the parts of a program, algorithm, or problem to be excecuted out-of-order or in partial order without affecting the final outcome of the work.  This can significantly improve the overall speed of execution in multi-processor/multi-core systems.

Concurrency is achived typically through the sharing of resources, or via message passing.

## Concurrency Control
Concurrency control ensures that correct results for concurrent operations are generated, while getting those results as quickly as possible.  Introducing concurrency control into a system means applying operation constraints which typically result in some performance reduction.  These constraints can easily become quite complicated.  

### ACID
ACID is a concurrency control mechanism applied to Database Management Systems, implemented through the concept of a **transaction**, a unit of work that typically encapsulates a variable number of database operations.  

- Atomicity: A transaction is atomic of it commits either all or none of the requested operations.
- Consistency: Consistency requires that every operation must leave the database in a consistent or correct state.
- Isolation: Isolation ensures that one transaction cannot interfere with another transcation.
- Durability: Durability requires that the effects of successful transcations must persist through database crashes.

### Optimistic Concurrency
Optimistic concurrency assumes an operation will succeed, and delays looking for any concurrency violations until the end of execution.  If concurrency was violated, the operation is aborted.  This approach typically incurs overhead.  It works well when concurrency violations are relatively low.

### Pessimistic Concurrency
Pessimistic concurrency blocks the completion of an operation until when it causes concurrency violations, until the possibility of a violation is removed.  This approach typically incurs a reduction in performance.

### Semi-Optimistic Concurrency
Semi-optimistic concurrency blocks for some operations and not others.

## Concurrency Methods

### Locking
A lock can be placed on a shared resource, so that only one operation may modify that resource at a time.  Other operations are blocked and must wait.

### Timestamp Ordering
Operations or transactions are assigned a timestamp.  Operations are controlled by checking timestamp order.

### Commitment Ordering
Operations or transactions are assigned a precedence and are executed in order.

# References
- [Concurrency (Computer Science)](https://en.wikipedia.org/wiki/Concurrency_(computer_science))
- [Concurrency Control](https://en.wikipedia.org/wiki/Concurrency_control)
- [What is the difference between ansynchronous programming and multithreading?](https://stackoverflow.com/questions/34680985/what-is-the-difference-between-asynchronous-programming-and-multithreading)
