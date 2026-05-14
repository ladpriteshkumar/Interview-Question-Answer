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

---



“Generics allow type‑safe, reusable, high‑performance code. They apply to classes, methods, interfaces, delegates, collections, constraints.


# **🔥 C# Generics — Top Interview Questions & Answers**

## **1. What are Generics in C#?**
**Answer:**  
Generics allow you to create type‑safe, reusable classes, methods, interfaces, and collections without specifying the actual data type until used. They eliminate casting, improve performance, and catch errors at compile time.

---

## **2. Why do we use Generics?**
**Answer:**  
- Type safety  
- No boxing/unboxing  
- Better performance  
- Code reusability  
- Cleaner, maintainable code  

---

## **3. What is a Generic Class?**
```csharp
public class Box<T>
{
    public T Value { get; set; }
}
```

---

## **4. What is a Generic Method?**
```csharp
public T GetItem<T>(T value)
{
    return value;
}
```

---

## **5. What are Generic Constraints?**
Constraints restrict what types can be used with a generic.

Examples:
```csharp
where T : class
where T : struct
where T : new()
where T : BaseClass
where T : IBaseInterface
```

---

## **6. What is the benefit of constraints?**
They enforce rules at compile time and allow the generic code to safely use features of the constrained type.

---

## **7. What is Covariance and Contravariance?**
### **Covariance (out T)**  
Allows assigning a more derived type to a less derived type.

### **Contravariance (in T)**  
Allows assigning a less derived type to a more derived type.

---

## **8. What is a Generic Interface?**
```csharp
public interface IRepository<T>
{
    void Add(T item);
    T Get(int id);
}
```

---

## **9. What is a Generic Delegate?**
```csharp
public delegate T Operation<T>(T a, T b);
```

---

## **10. What are Generic Collections?**
- `List<T>`
- `Dictionary<TKey, TValue>`
- `Queue<T>`
- `Stack<T>`
- `HashSet<T>`

These are faster and safer than non‑generic collections like `ArrayList`.

---

## **11. What is the difference between List<T> and ArrayList?**
| Feature | List<T> | ArrayList |
|--------|---------|-----------|
| Type Safety | Yes | No |
| Boxing/Unboxing | No | Yes |
| Performance | Faster | Slower |
| Compile‑time checks | Yes | No |

---

## **12. Can Generics be used with static classes?**
Yes.

```csharp
public static class Cache<T>
{
    public static T Data;
}
```

---

## **13. Can we overload generic methods?**
Yes — as long as the signatures differ.

---

## **14. Can a Generic class have multiple type parameters?**
Yes.

```csharp
public class Pair<T1, T2>
{
    public T1 First;
    public T2 Second;
}
```

---

## **15. What is default(T)?**
Returns the default value of a type.

Examples:
- `default(int)` → 0  
- `default(string)` → null  
- `default(bool)` → false  

---

# **🔥 Bonus: Real‑World Generic Repository Example**
```csharp
public class Repository<T> where T : class
{
    public void Add(T entity) { }
    public T Get(int id) => default;
}
```

---

If you'd like, I can assemble all of this into a **one‑page Generics cheat sheet** you can use for last‑minute interview revision.




















==============================================
 ## What is Generic in C#?
Generics in C# allow you to define classes, interfaces, methods, and data structures with a placeholder for the data type. Instead of writing separate implementations for each type, you write one generic definition that works with any type, while still maintaining type safety and performance.

 ### 🔑 Key Points to Mention
#### Definition:
Generics introduce type parameters (like `<T>`) that let you create reusable code components without sacrificing type safety.
#### Benefits:
- Type Safety: Errors are caught at compile time, no need for casting.
- Performance: Avoids boxing/unboxing for value types.
- Reusability: One implementation works for multiple types.
- Maintainability: Cleaner, more readable code.
#### Examples:
```csharp
// Generic Class
public class GenericBox<T>
{
    private T value;
    public void Add(T item) { value = item; }
    public T Get() { return value; }
}

// Usage
GenericBox<int> intBox = new GenericBox<int>();
intBox.Add(10);
Console.WriteLine(intBox.Get()); // Output: 10

GenericBox<string> strBox = new GenericBox<string>();
strBox.Add("Hello");
Console.WriteLine(strBox.Get()); // Output: Hello
```

 
 ## What are generic collections

 Generic collections in .NET are strongly‑typed data structures provided by the `System.Collections.Generic` namespace. Unlike non‑generic collections (like `ArrayList` or `Hashtable`), generic collections enforce type safety at compile time, which eliminates the need for boxing/unboxing and reduces runtime errors.



#### Definition:
Generic collections store elements of a specific type, defined using type parameters (e.g., List<T>). This ensures type safety and better performance.

#### Advantages:
- Type Safety: Compile‑time checking prevents invalid type insertions.
- Performance: No boxing/unboxing overhead for value types.
- Flexibility: Can work with any data type using generics.
- Code Reusability: One implementation works for multiple types.
#### Common Generic Collections:
- List<T> → Dynamic array, fast indexing.
- Dictionary<TKey, TValue> → Key/value pairs with fast lookups.
- Queue<T> → FIFO structure.
- Stack<T> → LIFO structure.
- HashSet<T> → Unique elements, optimized for set operations.
- SortedList<TKey, TValue> / SortedDictionary<TKey, TValue> → Maintain sorted order.
-
#### Example:
```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<string> names = new List<string>();
        names.Add("Alice");
        names.Add("Bob");

        foreach (var name in names)
        {
            Console.WriteLine(name); // Type-safe, no casting required
        }
    }
}
```

