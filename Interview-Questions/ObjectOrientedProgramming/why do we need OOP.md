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
- Abstraction is principle of OOP which Hides implementation details and shows only essential features.
- Achieved using abstract classes and interfaces in C#.
- Helps developers work at a higher level of design without worrying about low-level details.
- Example: An `IReoisitory`  interface abstracts data access logic, while implementations handle SQL Server or MongoDB specifics.
#### Inheritance 🧬
- Allows one class to derive from another, reusing code and extending functionality.
- Example: class Manager : Employee { }
- Promotes code reuse by allowing classes to derive from existing ones.
- Reduces redundancy and improves maintainability.
- Example: `Employee`  base class `Manager` →  and `Developer`  subclasses.
#### Polymorphism 🔄
- Same interface, different implementations.
- Achieved via method overriding (virtual/override) and overloading.
- Enables one interface to be used for different underlying forms (method overriding/overloading).
- Makes systems extensible and flexible.
- Example: A `shape` class with a   `Draw()` method, implemented differently by `Circle` and `Tringle` .
