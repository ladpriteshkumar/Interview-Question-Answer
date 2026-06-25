> # Design Patterns

> - A design patterns is general, reusable solution to a commonly occurring software problem. 
> - A design patterns is not a finished specification that can be transformed directly into code. instead it is template for solving a particular problem.      
> - A design patterns allows you to formulate a high-level solutation that is independent of the implementation details.    
> - using established design patterns lead to a solution that is easily understandable, testeble, and maintainable.   

---

# Gang of Four Design Patterns  
[Ref YouTube](https://www.youtube.com/watch?v=NU_1StN5Tkk)

there are 23 design patterns authored by Erich Gamma, Richard Helm, Ralph Johnson and John Vlissides knows as Gang of Four Design Patterns.
GoF Design Patterns are caregories in 3 categories, Cerational Patterns, Structural Patterns and Behavioral Patterns


Creational Patterns | Structural Patterns | Behavioral Patterns
| :--- | :--- | :---
Abstract Factory  | Adapter | Chain of Responsibility (CoR)
Factory Method  | Bridge | Command
Builder  | Composite | Interpreter
Prototype  | Decorator | Iterator
Singleton  | Facade | Mediator
--  | Flyweight | Memento
--  | Proxy | Observer
--  | -- | State
--  | -- | Strategy
--  | -- | Template Method
--  | -- | Visitor


---

# Repository Design Pattern

The Repository pattern abstracts(hide) data access behind a clean interface.   
it improves testability, decouples persistence, and centralizes CRUD operations.

## When to use it
**Decoupling:** when you want to isolate business logic from data access details. 

**Testability:** when you need to mock data access for unit tests. 

**Multiple data sources:** when the app may switch or combine storage technologies. 


Decoupling persistence means isolating data‑storage concerns (SQL, ORM, files, APIs) behind an abstraction so business logic works with domain objects and contracts instead of database code; the Repository pattern is a common way to achieve that, improving testability, maintainability, and swap‑ability of storage.
