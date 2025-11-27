
### What is Delegates
A delegate in C# is a type-safe object that represents a reference to a method with a specific signature and return type. In simple terms, it’s like a function pointer but safer and more powerful, because it ensures that the method you assign matches the expected parameters and return type

### 🌐 What is a Delegate?
- A delegate in C# is like a pointer to a function.
- It allows you to store a reference to a method and call that method later.
- Think of it as a way to pass methods around just like variables.
- Delegates are especially useful for event handling and situations where you want to decide at runtime which method should be executed.


#### 🛠 How to Create a Delegate
- Declare the delegate type
- You define what kind of methods it can point to (based on return type and parameters).
```csharp
// Step 1: Declare a delegate type
public delegate void MyDelegate(string message);
```
- Create methods that match the delegate signature
```csharp
// Step 2: Create methods
public static void PrintMessage(string msg)
{
    Console.WriteLine("Message: " + msg);
}

public static void ShowUpperCase(string msg)
{
    Console.WriteLine(msg.ToUpper());
}
```
- Instantiate the delegate and assign a method
```csharp
// Step 3: Use the delegate
MyDelegate del = PrintMessage;   // pointing to PrintMessage
del("Hello World!");             // calls PrintMessage

del = ShowUpperCase;             // pointing to ShowUpperCase
del("Hello World!");             // calls ShowUpperCase
```



### can we create obj of delegate ?
Yes 👍, in C# you can create an object of a delegate because a delegate is actually a class type under the hood.


### 🎯 Where Delegates Are Used

- Event Handling
  
     Delegates are the backbone of events in C#.
  
- Callback Methods
  
    Delegates are used when you want to pass a method as a parameter to another method.

- Multicast Delegates
  
    A single delegate object can hold references to multiple methods.

- LINQ and Anonymous Methods
  
    Delegates are used under the hood with Func<> and Action<>.
#### Example:
```csharp
List<int> numbers = new List<int> {1,2,3,4};
var evens = numbers.FindAll(x => x % 2 == 0); // uses a delegate internally
```







### 🔑 Key Characteristics of Delegates
- Type-safe function pointer: Ensures the method signature matches the delegate declaration.
- Encapsulation of methods: Can reference both static and instance methods.
- First-class object: Delegates can be stored in variables, passed as parameters, or returned from methods.
- Foundation of events: Events in C# are built on delegates, making them essential for event-driven programming.
- Supports flexible programming: Enables callbacks, anonymous methods, and lambda expressions.

#### 📘 Example
```csharp
// Declare a delegate type
public delegate void Notify(string message);

class Program
{
    static void Main()
    {
        // Assign a method to the delegate
        Notify notifier = ShowMessage;

        // Invoke the method via delegate
        notifier("Delegates are powerful!");
    }

    static void ShowMessage(string msg)
    {
        Console.WriteLine(msg);
    }
}
```

Here:
- Notify is a delegate type that can point to any method taking a string and returning void.
- ShowMessage is assigned to the delegate, and calling notifier("...") executes that method indirectly.




