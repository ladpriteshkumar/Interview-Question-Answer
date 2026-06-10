# What is Destructor ?

A **destructor** in C# is a special method that runs automatically when the **garbage collector** is about to reclaim an object. Its purpose is to clean up **unmanaged resources** as a last‑chance fallback.

The key takeaway:  
> A destructor is C#’s version of a *finalizer* — it runs nondeterministically and should only be used to release unmanaged resources if `Dispose()` wasn’t called.

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
