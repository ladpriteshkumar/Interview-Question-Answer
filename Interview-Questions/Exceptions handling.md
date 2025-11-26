## How do we handle exceptions in C#(try/catch)?

In C#, exceptions are handled using `try`, `catch`, and optionally `finally` blocks. The `try` block contains code that may throw an exception, while the `catch` block allows us to handle specific exceptions gracefully. A `finally` block is often used for cleanup tasks, such as closing files or releasing resources, and it executes regardless of whether an exception occurred.


From a best-practice perspective, I always prioritize catching specific exceptions first—for example, `FileNotFoundException` or `SqlException`—before falling back to a general `Exception` catch. This ensures that error handling is precise and avoids masking issues. I also avoid empty `catch` blocks, since they can swallow errors silently and make debugging difficult.


## ⚙️ How try/catch Works in C#
### try block
- Contains code that might throw an exception.
- If no exception occurs, the catch block is skipped.
### catch block
- Handles the exception if one occurs in the try block.
- You can have multiple catch blocks to handle different exception types.
### finally block (optional)
- Executes regardless of whether an exception occurred or not.
- Commonly used for cleanup (closing files, releasing resources, etc.).

#### 🧑‍💻 Example
```csharp
using System;

class Program
{
    static void Main()
    {
        try
        {
            int[] numbers = { 1, 2, 3 };
            Console.WriteLine(numbers[5]); // This will throw IndexOutOfRangeException
        }
        catch (IndexOutOfRangeException ex)
        {
            Console.WriteLine($"Error: {ex.Message}");
        }
        catch (Exception ex) // General catch for any other exceptions
        {
            Console.WriteLine($"Unexpected error: {ex.Message}");
        }
        finally
        {
            Console.WriteLine("Execution completed (finally block).");
        }
    }
}
```


### 🔑 Best Practices
- Catch specific exceptions first (e.g., FileNotFoundException) before using a general Exception.
- Avoid swallowing exceptions silently (don’t leave empty catch blocks).
- Use finally for cleanup tasks like closing database connections or file streams.
- For advanced scenarios, consider try/catch with exception filters (catch (Exception ex) when (condition)).





