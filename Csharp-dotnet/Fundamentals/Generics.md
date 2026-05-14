## What is Generics ?
Generics allow us to write flexible, reusable, and type‑safe code that work with any datatype in a type‑safe way.

Generics allow developers to design classes, methods, and interfaces that can work with any data type without compromising type safety.

## What Are Generics? (Easy Explanation)
Generics let you create reusable code that works with any data type while still keeping type safety.   
Think of generics like a template:   
- You write the logic once
- You decide the data type later
- The compiler still checks types and prevents errors
---
Generics are not a datatype.
They are a feature in C# that lets you create classes, methods, and interfaces that work with any datatype in a type‑safe way.

Think of generics as templates.

You write the logic once, and the datatype becomes a placeholder like `<T>`.


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

Generic classes improve type safety by avoiding explicit type casting.   
Generic are widely used in collection classes like List<T>, Dictionary<TKey, TValue>, and Queue<T>.
