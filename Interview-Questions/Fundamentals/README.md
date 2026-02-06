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

### 3. What is IL ( Intermediate Language)  ?
Intermediate Language (IL), also called  Common Intermediate Language(CIL) or Microsoft Intermediate Language (MSIL), all .NET languages (like C#, VB.NET, F#) compile into IL at runtime, the Common Language Runtime (CLR) translates IL into native machine code using the Just-In-Time (JIT) compiler

### 4. What is the use of JIT ( Just in time compiler) ?
The Just-In-Time (JIT) compiler in .NET converts Intermediate Language (IL) code into native machine code at runtime.

Its main use is to make .NET applications platform-independent during development while still achieving high performance when executed.

#### Execution
Source code (e.g., C#) → compiled into IL → JIT translates IL into machine code specific to the CPU/OS

### 5. Is it possible to view IL code ?
Yes ✅, it’s absolutely possible to view IL (Intermediate Language) code from your compiled .NET assemblies. Developers often do this to understand what the compiler generated, debug performance issues, or learn how high-level C# translates into IL.

### 6. What is the benefit of compiling in to IL code ?
- “.NET compiles to IL (Intermediate Language) so the code becomes platform‑independent, secure, and highly optimized at runtime. IL allows the CLR to verify type safety, prevent memory issues, and then JIT‑compile the code into machine instructions that are optimized for the specific CPU and OS.
- It also enables cross‑language interoperability, reflection, and advanced runtime features that wouldn’t be possible with direct native compilation.”

“Platform independence means the same compiled code can run on multiple operating systems and CPU architectures without needing to be recompiled." 


### 7. Why .NET Compiles to IL Instead of Direct Machine Code

#### 1. Platform Independence
- IL is CPU‑agnostic.
- The same compiled DLL/EXE can run on Windows, Linux, or macOS.
- The CLR/JIT converts IL into native machine code for the specific OS and CPU at runtime.

**Benefit:** Write once, run anywhere the .NET runtime exists.

---

#### 2. Runtime Optimizations (JIT)
- JIT optimizes code based on the actual hardware.
- Can use CPU‑specific instructions (SSE, AVX).
- Supports tiered compilation for fast startup and later optimization.

**Benefit:** Better performance than precompiled native binaries.

---

#### 3. Security & Verification
- CLR verifies IL for type safety.
- Prevents memory corruption and unsafe operations.
- Enforces code access security and metadata validation.

**Benefit:** Safer execution environment.

---

#### 4. Cross‑Language Interoperability
- All .NET languages compile to IL.
- Enables seamless interaction between C#, F#, VB.NET, PowerShell, etc.

**Benefit:** Unified multi‑language ecosystem.

---

#### 5. Reflection, Metadata & Dynamic Features
- IL stores rich metadata about types, methods, attributes, etc.
- Enables reflection, dynamic code generation, DI frameworks, ORMs, and serialization.

**Benefit:** Powerful runtime capabilities not possible with native binaries.

---

#### 6. Flexibility for JIT, AOT, and Hybrid Models
- IL supports JIT (default), AOT (NativeAOT), and hybrid compilation.
- Developers can choose based on startup time, performance, or deployment needs.

**Benefit:** Best of both worlds — flexibility + performance.

---

#### **One‑Line Summary**
**IL gives .NET portability, runtime optimization, security, interoperability, and advanced runtime features that native compilation alone cannot provide.**


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

