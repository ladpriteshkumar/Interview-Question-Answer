## Why do we need OOP ?

### 🎯 Purpose of OOP
Object-Oriented Programming (OOP) is needed because it provides a structured way to design and build software that is scalable, maintainable, and reusable. Instead of writing procedural code, OOP organizes logic around objects that represent real-world entities.


### ✅ Key Reasons We Need OOP
#### Encapsulation 🛡️
- Encapsulation is the principle of wrapping data (fields) and behavior (methods) together inside a single unit (class) and restricting direct access to the internal state.
- It ensures that an object’s internal representation is hidden from the outside world.
- Controls access to data using access modifiers (public, private, protected)
- Protects internal state by exposing only what’s necessary through public access modifiers.
- Example: A `BankAccount` class hides its balance field and only allows deposits/withdrawals via methods.
#### Car Example of Encapsulation
##### Think of a Car object:
- Private Data (hidden internals)
- Engine details, fuel injection system, brake hydraulics, transmission gears.
- As a driver, you don’t directly manipulate these — they’re hidden inside the car.
- Public Interface (controlled access)
- Steering wheel, accelerator pedal, brake pedal, gear shift, dashboard.
- These are the methods/properties you use to interact with the car.
- The car internally decides how pressing the brake pedal slows the wheels — you don’t need to know the mechanics.

#### Abstraction 🎭
- **Abstraction** is the process of **hiding implementation** details and exposing only the essential features of an object.
- Achieved using **abstract classe** and **interfaces** in C#.
- Helps developers work at a higher level of design without worrying about low-level details.
- Example:  An IVehicle interface defines Start and Stop methods. Whether a car uses ignition or a bike uses kick start is hidden inside the concrete class. The user only cares about calling Start and Stop, not how they’re implemented."

```csharp
// Abstraction: defines WHAT should be done
public interface IVehicle
{
    void Start();
    void Stop();
}

// Implementation: defines HOW it is done
public class Car : IVehicle
{
    public void Start()
    {
        Console.WriteLine("Car engine started with ignition key.");
    }

    public void Stop()
    {
        Console.WriteLine("Car stopped using hydraulic brakes.");
    }
}

public class Bike : IVehicle
{
    public void Start()
    {
        Console.WriteLine("Bike engine started with kick start.");
    }

    public void Stop()
    {
        Console.WriteLine("Bike stopped using disc brakes.");
    }
}

// Client code
class Program
{
    static void Main()
    {
        IVehicle vehicle = new Car();
        vehicle.Start();   // User only knows "Start" exists, not HOW it works
        vehicle.Stop();

        vehicle = new Bike();
        vehicle.Start();   // Same abstraction, different hidden implementation
        vehicle.Stop();
    }
}  
```

#### Inheritance 🧬
- Inheritance is an OOP principle that allows one class (child/derived class) to reuse and extend the properties and behaviors of another class (parent/base class).
- Promotes code reuse by allowing classes to derive from existing ones.
- It promotes code reuse.
- In C#, inheritance is implemented using the `:` symbol.
- Example: `Employee`  base class `Manager` →  and `Developer`  subclasses.
```csharp
// Base class
public class Employee
{
    public string Name { get; set; }
    public void Work()
    {
        Console.WriteLine($"{Name} is working.");
    }
}

// Derived class
public class Manager : Employee
{
    public void ConductMeeting()
    {
        Console.WriteLine($"{Name} is conducting a meeting.");
    }
}

// Derived class
public class Developer : Employee
{
    public void WriteCode()
    {
        Console.WriteLine($"{Name} is writing code.");
    }
}

// Client code
class Program
{
    static void Main()
    {
        Manager mgr = new Manager { Name = "Alice" };
        mgr.Work();             // Inherited from Employee
        mgr.ConductMeeting();   // Manager-specific

        Developer dev = new Developer { Name = "Bob" };
        dev.Work();             // Inherited from Employee
        dev.WriteCode();        // Developer-specific
    }
}
```

  
#### Polymorphism 🔄
- Same interface, different implementations.
- Achieved via method overriding (virtual/override) and overloading.
- Enables one interface to be used for different underlying forms (method overriding/overloading).
- Makes systems extensible and flexible.
- Example: A `shape` class with a   `Draw()` method, implemented differently by `Circle` and `Tringle` .


# 🚗 Car Analogy: Encapsulation vs Abstraction

| Concept          | Car Analogy                                                                 | OOP Mapping                                                                 |
|------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| **Encapsulation** 🛡️ | The car hides its internal mechanics (engine, brake hydraulics, transmission). You cannot directly manipulate them — you only interact through pedals, steering, and dashboard. | Data (fields) are kept private, and access is controlled via public methods/properties. Protects the internal state of the object. |
| **Abstraction** 🎭   | The car exposes only the *essential controls* you need to drive: steering wheel, accelerator, brake, dashboard. You don’t need to know *how* pressing the brake slows the car — just that it does. | Focuses on *what* an object does, not *how*. Achieved via abstract classes and interfaces that define behavior without implementation. |

---

## 🔑 Key Difference
- **Encapsulation** = *Hiding the data* and controlling access to it.  
- **Abstraction** = *Hiding the implementation* and exposing only the necessary functionality.  

👉 In short:  
- Encapsulation is about **data protection**.  
- Abstraction is about **simplifying complexity**.

