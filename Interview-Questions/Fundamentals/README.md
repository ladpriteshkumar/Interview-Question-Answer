
### 1. [Explain difference between .NET and C# ?](https://github.com/ladpriteshkumar/Interview-Question-Answer/blob/main/Interview-Questions/Explain%20difference%20between%20.NET%20and%20C%23.md)

### 1. .NET Framework vs .NET Core vs .NET 5.0 (Difference) ?
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

![IMAGE](https://github.com/ladpriteshkumar/Interview-Question-Answer/blob/main/Interview-Questions/Fundamentals/dotnetframework-vs-dotnet.jpg)

### 3. What is IL ( Intermediate Language)  ?
Intermediate Language (IL), also called  Common Intermediate Language(CIL) or Microsoft Intermediate Language (MSIL), all .NET languages (like C#, VB.NET, F#) compile into IL at runtime, the Common Language Runtime (CLR) translates IL into native machine code using the Just-In-Time (JIT) compiler

### 4. What is the use of JIT ( Just in time compiler) ?
The Just-In-Time (JIT) compiler in .NET converts Intermediate Language (IL) code into native machine code at runtime.

Its main use is to make .NET applications platform-independent during development while still achieving high performance when executed.

#### Execution
![IMAGE](https://github.com/ladpriteshkumar/Interview-Question-Answer/blob/main/Interview-Questions/Fundamentals/dotnetExecution.png)

### 5. Is it possible to view IL code ?
Yes ✅, it’s absolutely possible to view IL (Intermediate Language) code from your compiled .NET assemblies. Developers often do this to understand what the compiler generated, debug performance issues, or learn how high-level C# translates into IL.


### 6. What is the benefit of compiling in to IL code ?  OR Why .NET Compiles to IL Instead of Direct Machine Code

#### 1. Platform Independence
- The same compiled DLL/EXE can run on Windows, Linux, or macOS.
- The CLR/JIT converts IL into native machine code for the specific OS and CPU at runtime.

**Benefit:** Write once, run anywhere the .NET runtime exists.

#### 2. Runtime Optimizations (JIT)
- JIT optimizes code based on the actual hardware.
- Can use CPU‑specific instructions (SSE, AVX).
- Supports tiered compilation for fast startup and later optimization.

**Benefit:** Better performance than precompiled native binaries.


#### 3. Security & Verification
- CLR verifies IL for type safety.
- Prevents memory corruption and unsafe operations.
- Enforces code access security and metadata validation.

**Benefit:** Safer execution environment.


#### 4. Cross‑Language Interoperability
- All .NET languages compile to IL.
- Enables seamless interaction between C#, F#, VB.NET, PowerShell, etc.

**Benefit:** Unified multi‑language ecosystem.


#### 5. Reflection, Metadata & Dynamic Features
- IL stores rich metadata about types, methods, attributes, etc.
- Enables reflection, dynamic code generation, DI frameworks, ORMs, and serialization.

**Benefit:** Powerful runtime capabilities not possible with native binaries.


#### 6. Flexibility for JIT, AOT, and Hybrid Models
- IL supports JIT (default), AOT (NativeAOT), and hybrid compilation.
- Developers can choose based on startup time, performance, or deployment needs.

**Benefit:** Best of both worlds — flexibility + performance.


#### **One‑Line Summary**
**IL gives .NET portability, runtime optimization, security, interoperability, and advanced runtime features that native compilation alone cannot provide.**


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

### 12. [What is the importance of CTS ?]
- CTS is the standard that defines how all data types behave in .NET so that all languages can work together.
- CTS Exist Because .NET supports multiple languages (C#, F#, VB.NET), CTS ensures they can interoperate without type conflicts.


### 13. [Explain CLS ?]
- CLS is a subset of CTS—a set of rules that languages must follow to be cross‑language compatible.
- Not all languages support all CTS features. CLS defines the minimum features that every .NET language must support.


