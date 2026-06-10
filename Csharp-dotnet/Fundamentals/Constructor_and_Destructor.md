# What is Constructor ?
A **constructor** in C# is a special method that runs **automatically** when you create an object. Its job is to **initialize the object**, set default values, and prepare it for use.

Think of it as the “setup” step every time you say `new`.

---

## ✅ Short Definition
A **constructor** is a method that:

- Has the **same name as the class**
- Has **no return type** (not even `void`)
- Runs **automatically** when an object is created
- Is used to **initialize fields** or run startup logic

---

## 🧩 Basic Example

```csharp
class Person
{
    public string Name;

    public Person(string name)
    {
        Name = name;
        Console.WriteLine("Constructor called!");
    }
}
```

Usage:

```csharp
var p = new Person("John");
```

This automatically calls the constructor and sets `Name`.

---

## 🛠️ Types of Constructors

### 1. **Default Constructor**
Created automatically if you don’t define one.

```csharp
class Car
{
    public Car() { }
}
```

### 2. **Parameterized Constructor**
Allows passing values during object creation.

```csharp
public Car(string model, int year)
{
    Model = model;
    Year = year;
}
```

### 3. **Static Constructor**
Runs **once per class**, before the first use. Used for static initialization.

```csharp
static Car()
{
    Console.WriteLine("Static constructor called!");
}
```

### 4. **Private Constructor**
Prevents creating objects from outside the class (used in Singletons).

```csharp
private Car() { }
```

---

## 🔍 Constructor vs Destructor (Quick Comparison)

| Feature | Constructor | Destructor |
|--------|-------------|------------|
| When it runs | When object is created | When object is collected by GC |
| Purpose | Initialize | Cleanup unmanaged resources |
| Can have parameters | Yes | No |
| Can be overloaded | Yes | No |
| Called manually | Yes | No |

---

## 🎯 Why Constructors Matter
They help you:

- Ensure objects start in a valid state  
- Inject dependencies  
- Set default values  
- Prepare resources  

---

If you want, I can show you how constructors and destructors work together in a full class example.


---
# What is Destructor ?

A **destructor** in C# is a special method that runs automatically when the **garbage collector** is about to reclaim an object. Its purpose is to clean up **unmanaged resources** as a last‑chance fallback.

---

## 🧩 What a destructor looks like
In C#, a destructor uses the **tilde (~)** syntax:

```csharp
class MyClass
{
    ~MyClass()
    {
        // cleanup logic
    }
}
```

You **cannot** call a destructor manually — the runtime calls it.

---

## 🧠 What a destructor actually does
A destructor:

- Is translated into a **finalizer** under the hood  
- Runs on the **GC finalizer thread**  
- Executes at an **unknown time**  
- Only runs if `Dispose()` was *not* called  
- Should only clean **unmanaged resources**  

Because finalizers slow down garbage collection, they should be used sparingly.

---

## 🛠️ Destructor vs Dispose
| Feature | Destructor (`~ClassName`) | Dispose (`IDisposable.Dispose()`) |
|--------|---------------------------|-----------------------------------|
| When it runs | GC decides | You call it manually |
| Deterministic? | ❌ No | ✅ Yes |
| Purpose | Last‑chance cleanup | Primary cleanup |
| Can free managed objects? | ❌ No | ✅ Yes |
| Performance | Slow | Fast |

---

## 🏆 Best Practice
Use:

- **Dispose()** for normal cleanup  
- **Destructor** only as a *safety net* for unmanaged resources  

This is why the recommended pattern is:

```csharp
~MyClass()
{
    Dispose(false);
}
```

---

If you want, I can show you how destructors fit into the full **IDisposable pattern** with unmanaged resources.
