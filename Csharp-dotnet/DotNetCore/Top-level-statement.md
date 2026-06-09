## Top-level statements
Top-level statements in .NET (introduced with C# 9/.NET 5 and widely used in .NET Core 6+) allow you to write code directly in a file without wrapping it inside a `Program` class or a `Main` method. They simplify the entry point of applications by removing boilerplate code.


- How it works:
- Normally, a console app starts with:
```csharp
using System;

namespace MyApp {
    class Program {
        static void Main(string[] args) {
            Console.WriteLine("Hello World!");
        }
    }
}
```
With top-level statements, you can just write:
```csharp
Console.WriteLine("Hello, World!");
```

- The compiler automatically generates the `Program` class and `Main` method behind the scenes.
### Rules:
- Only one file in a project can contain top-level statements.
- They must appear before any namespace or type declarations in that file.
- You can still define methods, classes, or records in the same file, but they must come after the top-level code.
