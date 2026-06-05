## What are threads (Multithreading) ?
Threads are lightweight units of execution within a process, and multithreading is the technique of running multiple threads concurrently to improve performance and responsiveness.

###  What is a Thread?
- A thread is the smallest unit of execution in a program, sometimes called a lightweight process.
- Threads exist inside a process and share the same memory and resources (like CPU and I/O) of that process.
- Each thread has its own program counter, stack, and registers, but shares the process’s code, data, and files.

### What is Multithreading?
- Multithreading is the ability of a CPU or a program to execute multiple threads at the same time.
- It allows concurrency (tasks overlapping in execution) or parallelism (tasks running truly simultaneously on multi-core CPUs).
#### Example:
- In a web browser, one thread renders the page, another handles user input, and another downloads files.
- In MS Word, one thread formats text while another checks spelling.


### 🔑 Benefits of Multithreading
- Improved performance: Multiple tasks progress without waiting for one to finish.
- Responsiveness: Applications remain interactive even during heavy processing.
- Resource sharing: Threads share memory and resources, reducing overhead compared to multiple processes.
- Throughput computing: Increases the number of tasks completed over time.

### ⚠️ Challenges of Multithreading
- Race conditions: Multiple threads accessing shared data can cause inconsistent results.
- Deadlocks: Threads waiting on each other indefinitely.
- Complex debugging: Harder to trace errors when tasks overlap.


## How are threads different from TPL ?

### 🔑 Key Differences

| Aspect              | Threads                          | TPL (Tasks)                          |
|---------------------|----------------------------------|---------------------------------------|
| Level of abstraction | Low-level (manual control)       | High-level (managed by runtime)       |
| Resource management | Developer must manage            | Automatic via ThreadPool              |
| Ease of use         | Complex, error-prone             | Simplified with built-in features     |
| Features            | Basic execution                  | Continuations, cancellation, async/await |
| Best for            | Fine-grained control, legacy code | Modern parallelism & async programming |


"Threads are the basic unit of execution, giving developers direct control but requiring manual management of synchronization and lifecycle. The Task Parallel Library (TPL) is a higher-level abstraction that builds on threads, using the ThreadPool and scheduler to manage execution automatically. TPL makes it easier to write scalable, maintainable, and asynchronous code by providing features like continuations, cancellation, and integration with async/await. In practice, developers prefer TPL for most scenarios, while raw threads are used only when very fine-grained control is required."



 ### When should you use Threads vs TPL?

Use threads when you need low‑level, fine‑grained control over execution — for example, setting priorities, managing lifecycle explicitly, or working with legacy code that requires direct thread manipulation. Use the Task Parallel Library (TPL) when you want higher‑level abstractions for concurrency and parallelism, such as running background tasks, handling continuations, cancellations, or integrating with async/await. In modern .NET development, TPL is preferred for most scenarios because it simplifies code, improves scalability, and leverages the ThreadPool automatically, while raw threads are reserved for special cases requiring direct control."









