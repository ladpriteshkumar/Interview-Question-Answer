## what is abstract class ?
An abstract class in C# is a class that cannot be instantiated directly. It serves as a blueprint for other classes, allowing you to define common functionality while leaving some methods or properties to be implemented by derived classes.

## What is interface ?
An interface in C# is a contract that defines a set of methods, properties, events, without providing their implementation. Any class that implements the interface must provide the actual implementation of those members.


## Whats the difference between Abstract class and interface ?

# Difference Between Abstract Class and Interface in C#

| Feature            | Abstract Class                                                                 | Interface                                                                 |
|--------------------|---------------------------------------------------------------------------------|---------------------------------------------------------------------------|
| **Methods**        | Can have both abstract (no body) and concrete (with body) methods               | Only method signatures (no body), until C# 8.0 which allows default implementations |
| **Fields**         | Can contain fields, constants, and static members                               | Cannot contain fields (only properties, events, indexers)                 |
| **Constructors**   | Can have constructors                                                           | Cannot have constructors                                                  |
| **Access Modifiers** | Supports access modifiers (public, protected, private)                        | Members are public by default; no access modifiers allowed                 |
| **Inheritance**    | A class can inherit only one abstract class (single inheritance)                | A class can implement multiple interfaces (supports multiple inheritance) |
| **Purpose**        | Used when classes share a common base behavior and need partial implementation  | Used to define a contract that unrelated classes can follow                |
| **Relationship**   | Represents an **“is-a”** relationship (e.g., Dog *is an* Animal)                | Represents a **“can-do”** relationship (e.g., Dog *can-do* IRun, IPlay)   |


### Example

```csharp
// Abstract class example
public abstract class Animal
{
    // Abstract method (must be implemented by derived classes)
    public abstract void MakeSound();

    // Concrete method (already implemented, can be reused)
    public void Eat()
    {
        Console.WriteLine("Eating food...");
    }
}

// Interface example
public interface IRun
{
    void Run();  // Contract only, no implementation
}

public interface IPlay
{
    void Play(); // Another contract
}

// Concrete class implementing both abstract class and interfaces
public class Dog : Animal, IRun, IPlay
{
    // Implement abstract method from Animal
    public override void MakeSound()
    {
        Console.WriteLine("Bark!");
    }

    // Implement interface methods
    public void Run()
    {
        Console.WriteLine("Dog is running fast!");
    }

    public void Play()
    {
        Console.WriteLine("Dog is playing fetch!");
    }
}

// Usage
class Program
{
    static void Main()
    {
        Dog dog = new Dog();
        dog.MakeSound(); // Bark!
        dog.Eat();       // Eating food...
        dog.Run();       // Dog is running fast!
        dog.Play();      // Dog is playing fetch!
    }
}
```


### Why Abstract Classes Are Still Needed Even Though Interfaces Allow Default Implementations (C# 8+)

#### 1. State vs. No State
• 	Abstract Class → Can hold fields, constructors, and state (data).
• 	Interface → Cannot hold instance fields or constructors. It’s still just a contract, even with default methods.
👉 If you need to share data + behavior, abstract class is the right choice.

#### 2. Access Modifiers
• 	Abstract Class → Members can have different access levels (`public`,`protected` ,`private` ).
• 	Interface → Members are public by default; you cannot restrict access.
👉 Abstract classes give more control over encapsulation.

#### 3. Inheritance Model
- Abstract Class → Supports single inheritance. A class can inherit only one abstract class.
- Interface → Supports multiple inheritance (a class can implement many interfaces).
👉 Abstract classes are better when you want a common base hierarchy

#### 4. Partial Implementation
• 	Abstract Class → Lets you provide partial implementation and enforce some abstract members.
• 	Interface → Default methods are optional helpers, but they don’t allow shared state or constructors.
👉 Abstract classes are better when you want a template + enforced rules.



### ✅ Interview Summary
- Interfaces with default methods are useful for adding helper behavior across many classes.
- Abstract classes are still essential when you need:
  
     Shared state (fields)

     Constructors

     Access modifiers
 
     Base hierarchy with partial implementation







