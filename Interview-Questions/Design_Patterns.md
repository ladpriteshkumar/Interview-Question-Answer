# Design Patterns
A design patterns is general, reusable solution to a commonly occurring software problem. 

A design patterns is not a finished specification that can be transformed directly into code. instead it is template for solving a particular problem.  Thinking in terms of design patterns allows you to formulate a high-level solutation that is independent of the implementation details.  using established design patterns lead to a solution that is easily understandable, testeble, and maintainable.


# What is S.O.L.I.D ?
S.O.L.I.D is an acronym for the first five Object Oriented Design Principles

S - Single Responsibility Principle

O - Open Closed Principle

L - Liskov Substitution Principle

I - Interface Segregation Prinicple

D - Dependency Inversion Principle

When these 5 principle are applied to software development, it makes it easy to develop software that follows good architecture and is easy to maintain and extend.

[Ref youtube](https://www.youtube.com/watch?v=HLFbeC78YlU&list=PL6n9fhu94yhXjG1w2blMXUzyDrZ_eyOme)


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

# Dependency injection (DI)

Dependency injection (DI) is a software design pattern and programming technique where an object receives its required dependencies (other objects it depends on) from an external source rather than creating them itself. 

It promotes loose coupling, making code more modular, testable, and maintainable by separating object construction from usage. 


When we say **“external source”** in Dependency Injection, we simply mean **anything outside the class that needs the dependency**.  
The class does *not* create the dependency — something else provides it.

Here’s the clean, structured breakdown you can use in interviews.

---

# **What Counts as an External Source in DI?**

An **external source** is *any mechanism* that supplies the dependency to a class instead of the class creating it.

## **1. Dependency Injection Container (Most common)**
In .NET, this is the built‑in DI container:

```csharp
builder.Services.AddScoped<IEmailService, EmailService>();
```

The container creates and injects the dependency.

---

## **2. Another Class (Manual Injection)**
You can inject dependencies manually:

```csharp
var service = new EmailService();
var notification = new Notification(service);
```

Here, the **calling class** is the external source.

---

## **3. Framework or Runtime**
ASP.NET Core automatically injects dependencies into controllers, middleware, etc.

```csharp
public class HomeController
{
    public HomeController(ILogger<HomeController> logger) { }
}
```

The **framework** acts as the external source.

---

## **4. Configuration or Factory**
A factory can create and supply dependencies:

```csharp
var service = ServiceFactory.CreateEmailService();
```

The **factory** is the external source.

---

## **5. Unit Test (Mocking)**
In testing, mocks or fakes are injected:

```csharp
var mock = new Mock<IEmailService>();
var notification = new Notification(mock.Object);
```

The **test code** becomes the external source.

---

# **Simple Interview‑Ready Explanation**
> **“External source means anything outside the class that provides its dependencies — such as a DI container, framework, factory, or even another class.”**

If you want, I can also show you a diagram that visually explains how the external source injects dependencies into a class.

