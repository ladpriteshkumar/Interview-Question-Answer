# Difference Between Ref and Out Parameter

Both `ref` and `out` in C# are used to pass arguments by reference, but `ref` requires the variable to be initialized before being passed, while `out` requires the variable to be assigned inside the method before returning

### 📘 Examples
Example with `ref`
```csharp
public static void Increment(ref int number)
{
    number += 1;
}

int value = 10;
Increment(ref value);
Console.WriteLine(value); // Output: 11
```

- Here, value must be initialized before being passed.
- The method modifies the existing value.

Example with `out`
```csharp
public static void GetValues(out int x, out int y)
{
    x = 5;
    y = 10;
}

int a, b; // No initialization required
GetValues(out a, out b);
Console.WriteLine($"a={a}, b={b}"); // Output: a=5, b=10
```

- Variables a and b don’t need initialization before the call.
- The method must assign values before returning.

### 🧠 Conceptual Summary
- Use ref when you want to modify an existing variable.
- Use out when you want to return multiple values from a method.
- Both pass by reference, but their compiler rules differ to enforce correct usage.

| Aspect                  | ref Parameter                                                                 | out Parameter                                                                 |
|--------------------------|-------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
| Initialization           | Must be initialized before being passed to a method.                         | Does not need to be initialized before being passed.                          |
| Requirement in Method    | The called method may or may not assign a value to the parameter.             | The called method must assign a value before returning.                       |
| Purpose                  | Used when the called method needs to read and modify the existing value.      | Used when the called method needs to return multiple values.                  |
| Data Flow                | Two-way: value is passed in and can be modified.                              | One-way: value is only passed out (must be set inside the method).            |
| Compilation Check        | Compiler ensures the variable is initialized before use.                      | Compiler ensures the variable is definitely assigned inside the method.       |
| Example Usage            | `public void Update(ref int x) { x += 10; }`                                 | `public void GetValue(out int y) { y = 20; }`                                |
| Common Scenario          | Updating existing data.                                                       | Returning additional data from a method.                                      |


