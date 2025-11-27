## Why do we need OOP ?

### 🎯 Purpose of OOP
Object-Oriented Programming (OOP) is needed because it provides a structured way to design and build software that is scalable, maintainable, and reusable. Instead of writing procedural code, OOP organizes logic around objects that represent real-world entities.


### ✅ Key Reasons We Need OOP
#### Encapsulation 🛡️
- Wrapping data and methods into a single unit (class).
- Controls access to data using access modifiers (public, private, protected)
- Bundles data (fields) and behavior (methods) together.
- Protects internal state by exposing only what’s necessary through public interfaces.
- Example: A `BankAccount` class hides its balance field and only allows deposits/withdrawals via methods.
#### Abstraction 🎭
- Hiding implementation details and exposing only essential features.
- Achieved using abstract classes and interfaces in C#.
- Hides implementation details and shows only essential features.
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
