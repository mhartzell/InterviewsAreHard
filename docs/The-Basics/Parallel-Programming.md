# Parallel Programming

There are a variety of ways to harness the the computer's ability to execute operations in parallel.

Consider an example where you are cooking in a restaurant.  An order comes in for eggs and toast.  In a synchronous context, you would cook the eggs, and when the eggs are finished, you would cook the toast.  You would then put the eggs and the toast on a plate and serve the meal.

# Asynchronous Programming

Asynchronous programming is about *tasks*.   As an asynchonrous cook,  you would start cooking the eggs and set a timer.  You would then start the toast cooking, and set another timer.  While both are cooking would you clean the sink.  When the timers go off, you put the eggs on a plate and the toast on a plate and serve them.  

In asynchronous single-threaded workflows you have a graph of tasks where some tasks depend on the results of others; as each task completes it invokes the code that schedules the next task that can run, given the results of the just-completed task.  However, this often requires just one worker to perform all tasks.

# Multithreaded Programming

Multithreaded programming is about *workers*.  As a multithreaded cook, you would hire two more cooks, one of which will cook eggs and one of which will cook toast.  You now need to figure out how to coordinate the cooks so that they do not conflict with one another when using shared resources in the kitchen.  You also have to pay the cooks.

In multithreaded workflows you assign tasks to workers.  Many tasks are not processor-bound, but if they are, it makes sense to use as many worker threads as there are processors to work in parallel.

## Synchronization Challenges

Multithreaded operations must synchronize access to share resources, as problems can occur when multiple threads try to modify these resources at the same time.

### Locks

A lock can be placed on a shared resource, so that only one thread modify that resource at a time.

# References
[What is the difference between ansynchronous programming and multithreading?](https://stackoverflow.com/questions/34680985/what-is-the-difference-between-asynchronous-programming-and-multithreading)
