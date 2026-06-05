### What is Array ?
• 	Definition: An Array is a fixed-size collection of elements of the same type.
  #### 	Key Points:
  • 	Size is defined at creation and cannot change later.
  • 	Elements are stored in contiguous memory locations.
  • 	Provides fast access using an index ( time complexity).
  • 	Example:
```csharp
int[] numbers = new int[3];   // Array of size 3
numbers[0] = 10;
numbers[1] = 20;
numbers[2] = 30;
```

 
  ### What is ArrayList ?
- Definition: An ArrayList is a dynamic collection class in C# (part of System.Collections).
### Key Points:
  - Size is not fixed; it can grow or shrink dynamically.
  - Stores elements as objects (not type-safe, unlike generic collections).
  - Useful when you don’t know the number of items in advance.
  - Example:
```csharp
ArrayList list = new ArrayList();
list.Add(10);
list.Add("Hello");   // can store different types
list.Add(3.14);
```

# 🔑 Differences Between Array and ArrayList

| Feature        | Array                          | ArrayList                          |
|----------------|--------------------------------|------------------------------------|
| Size           | Fixed at creation              | Dynamic, can grow/shrink           |
| Type Safety    | Strongly typed (same type only)| Stores objects (mixed types allowed)|
| Performance    | Faster (no boxing/unboxing)    | Slightly slower (boxing/unboxing)  |
| Namespace      | Built-in (System)              | System.Collections                 |

## Differentiate between Array and ArrayList ?

In C#, the key difference between an Array and an ArrayList lies in size, type safety, and flexibility.
#### Array
- Fixed in size once created.
- Strongly typed — all elements must be of the same type.
- Provides better performance because there’s no boxing/unboxing overhead.
- Ideal when the number of elements is known and type safety is critical.
#### ArrayList
- Resizable — it can grow or shrink dynamically.
- Not strongly typed — it stores objects, so value types are boxed and unboxed.
- More flexible, but less efficient due to casting and boxing overhead.
- Useful when you  don’t know the size in advance.
  
👉 In modern C#, List<T> is generally preferred over ArrayList because it combines the flexibility of dynamic resizing with type safety and performance.

##### Example (to demonstrate in an interview)
```csharp
// Array
int[] numbers = new int[3] { 1, 2, 3 };

// ArrayList
using System.Collections;
ArrayList list = new ArrayList();
list.Add(1);
list.Add("Hello"); // Mixed types allowed
```

#### Whose performance is better array or arraylist ?
- Arrays are faster and more memory-efficient because they are strongly typed and store elements contiguously.
- ArrayLists trade performance for flexibility — they can grow dynamically and hold mixed types, but incur overhead from boxing/unboxing and casting.




