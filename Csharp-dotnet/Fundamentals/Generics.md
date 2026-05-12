## What is Generics ?
Generics allow us to write flexible, reusable, and type‑safe code by using type parameters like `<T>` instead of hard‑coding data types.

## What Are Generics? (Easy Explanation)
Generics let you create reusable code that works with any data type while still keeping type safety.   
Think of generics like a template:   
- You write the logic once
- You decide the data type later
- The compiler still checks types and prevents errors

## Why Generics Are Useful
**1. Reusable Code**:
Write once → use with any type.

**2. Type Safe**:
Compiler catches mistakes early.

**3. No Casting**:
No need to convert types manually.

**4. Better Performance**:
Avoids boxing/unboxing.


## Super Simple Example
Without generics:   
- You write one class for int
- Another for string
- Another for double

With generics:
```csharp
public class Box<T>
{
    public T Value { get; set; }
}

```

Now `T` can be any type:

```csharp
var intBox = new Box<int>();
var stringBox = new Box<string>();
```
