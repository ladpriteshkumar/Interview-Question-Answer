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






