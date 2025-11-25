# Interview-Questions

https://www.questpond.com/c-interview-questions-and-answers/cid69
### 1. [Explain difference between .NET and C# ?](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/0fbd102f867eba96fca1cd610d9dd1c258827c72/Interview-Questions/Explain%20difference%20between%20.NET%20and%20C%23.md)

### 2. .NET Framework vs .NET Core vs .NET 5.0 (Difference) ?

### 3. What is IL ( Intermediate Language)  ?
Intermediate Language (IL), also called CIL (Common Intermediate Language) or MSIL (Microsoft Intermediate Language), is the platform-independent bytecode that all .NET languages (like C#, VB.NET, F#) compile into. At runtime, the Common Language Runtime (CLR) translates IL into native machine code using the Just-In-Time (JIT) compiler

### 4. What is the use of JIT ( Just in time compiler) ?
The Just-In-Time (JIT) compiler in .NET converts Intermediate Language (IL) code into native machine code at runtime.

Its main use is to make .NET applications platform-independent during development while still achieving high performance when executed.

#### Execution
Source code (e.g., C#) → compiled into IL → JIT translates IL into machine code specific to the CPU/OS

### 5. Is it possible to view IL code ?
Yes ✅, it’s absolutely possible to view IL (Intermediate Language) code from your compiled .NET assemblies. Developers often do this to understand what the compiler generated, debug performance issues, or learn how high-level C# translates into IL.

### 6. What is the benefit of compiling in to IL code ?

### 7. Does .NET support multiple programming languages ?
Yes

### 8. What is CLR ( Common Language Runtime) ?
The Common Language Runtime (CLR) is the execution engine of .NET. It runs your compiled code (IL – Intermediate Language), manages memory, enforces security, and provides essential services like garbage collection, exception handling, and cross-language interoperability

### 9. What is managed and unmanaged code ?   
🧩 Managed Code
- Definition: Code that runs under the supervision of the Common Language Runtime (CLR) in .NET.

⚙️ Unmanaged Code
- Definition: Code that runs directly on the operating system without CLR supervision.

### 10. Explain the importance of Garbage collector ?
The Garbage Collector (GC) in .NET is one of the most important features of the Common Language Runtime (CLR). It automatically manages memory, freeing developers from the burden of manual allocation and deallocation.

### 11. Can garbage collector claim unmanaged objects ?
No, the Garbage Collector cannot directly reclaim unmanaged objects. It only manages managed objects that live on the CLR-managed heap. Unmanaged resources (like file handles, database connections, sockets, or memory allocated outside the CLR) are invisible to the GC.

### 12. [What is the importance of CTS ?](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/9a04cb31ad386e68b30a9a84b4f813e7f07c14e0/Interview-Questions/What%20is%20the%20importance%20of%20CTS.md)

### 13. [Explain CLS ?](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/ddba41177e3367203739bb42d2711d2696c2702c/Interview-Questions/Explain%20CLS.md)

### 14. [Difference between Stack vs Heap ?](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/8761588929ca9a16c9dac65c54cd768357731743/Interview-Questions/Difference%20between%20Stack%20vs%20Heap.md)

### 15. [Data Type in C#](DataType/README.md) ? 

### 16. Explain boxing and unboxing ?
Boxing is the process of converting a value type into a reference type (specifically, into an `Object` ).

Unboxing is the process of converting Reference type ino a value type.



### 2) Explain Type casting in C# ? ###
[Reference](https://www.w3schools.com/cs/cs_type_casting.php#:~:text=In%20C%23%2C%20there%20are%20two,to%20a%20smaller%20size%20type)

