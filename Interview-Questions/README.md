# Interview-Questions

https://www.questpond.com/c-interview-questions-and-answers/cid69
### 1. [Explain difference between .NET and C# ?](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/0fbd102f867eba96fca1cd610d9dd1c258827c72/Interview-Questions/Explain%20difference%20between%20.NET%20and%20C%23.md)

### 2. .NET Framework vs .NET Core vs .NET 5.0 (Difference) ?
.NET Framework is Windows‑only and legacy, .NET Core is cross‑platform and high‑performance, and .NET 5+ is the unified, modern future of .NET

| Feature / Aspect      | .NET Framework        | .NET Core                 | .NET 5+ (5, 6, 7, 8…)            |
|-----------------------|------------------------|----------------------------|----------------------------------|
| Release Year          | 2002                   | 2016                       | 2020+                            |
| Platform Support      | Windows only           | Cross‑platform             | Cross‑platform                   |
| Open Source           | Partially              | Fully open source          | Fully open source                |
| Performance           | Moderate               | High                       | Highest                          |
| App Models            | WebForms, WPF, WinForms, ASP.NET MVC, WCF | ASP.NET Core, Console, Microservices | ASP.NET Core, MAUI, Blazor, Cloud‑native |
| Future Development    | Maintenance only       | Ended at .NET Core 3.1     | Actively developed (future of .NET) |
| Use Case              | Legacy enterprise apps | Modern, cloud, microservices | All new development, unified platform |

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

### 16. [Explain boxing and unboxing ?](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/types/boxing-and-unboxing)
Boxing is the process of converting a value type into a reference type (specifically, into an `Object` ).

Unboxing is the process of converting Reference type ino a value type.


### 17. [Explain Type casting in C# ? OR Explain casting, implicit casting and explicit casting](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/92e6583639e1c3181f583e2d77f1addbedcf57b4/Interview-Questions/Explain%20Type%20Casting.md)
[Ref](https://www.w3schools.com/cs/cs_type_casting.php#:~:text=In%20C%23%2C%20there%20are%20two,to%20a%20smaller%20size%20type)

### 18. [Array and ArrayList](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/c2debea049fa8121cd80334b69e746cd860b658e/Interview-Questions/Array%20and%20ArrayList.md)

### 19. [What are generic collections ?](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/1cafed76b9e151e79e0efb686b1145824946a523/Interview-Questions/generic%20collections.md)

### 20. [What are threads (Multithreading)?](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/b713c300498a1e8a06466a5ba4fbdc4f62dc2364/Interview-Questions/What%20are%20threads%20(Multithreading).md)

### 21. [Exception Handling](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/f6dbca3a14f946516efa1bb68a40203fde85c820/Interview-Questions/Exceptions%20handling.md)

### 22. [Difference Between Ref and Out Parameter](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/6e3c5e1fc36cba86a0afe31d6a929daab219dd5d/Interview-Questions/Difference%20Between%20Ref%20and%20Out%20Parameter.md)

### 23. [Delegates in C#](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/tree/b81ef7dfc048f9d326747a566c64bd7b8da76259/Interview-Questions)

### 24. [Events](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/ff1214a6b356f40d633f9a7c4d630e7f48fe8328/Interview-Questions/events.md)

### 25. [Whats the difference between Abstract class and interface ?](https://github.com/ladpriteshkumar/Learn-C-Sharp-Dot-Net-Core/blob/332a9efa170892b862f7b97bb8d18f62313863d7/Interview-Questions/Abstract%20class%20and%20interface.md)

