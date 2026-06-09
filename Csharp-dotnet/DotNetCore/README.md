
Core questions   
### What is .NET Core, and how is it different from .NET Framework?
.NET Core is a modern, open‑source, cross‑platform, high‑performance software development framework, designed for cloud and microservices. whereelse .NET Framework is the older, Windows‑only runtime mainly used for legacy enterprise applications.

### What are the main benefits of ASP.NET Core?   
Key benefits include built-in dependency injection, middleware-based request pipeline, better performance, cross-platform support, and strong support for cloud-native applications.

### [What is middleware in ASP.NET Core?](MiddlewareInDotNetCore.md)
Middleware in ASP.NET Core is a lightweight software component that sits in the HTTP request pipeline and processes incoming requests and outgoing responses.    
 
### What is dependency injection in ASP.NET Core?
Dependency injection is a software design pattern where dependencies are provided from outside the class rather than created internally.   
ASP.NET Core has built-in support for DI with transient, scoped, and singleton lifetimes.

### What is the difference between transient, scoped, and singleton services?
**Transient** creates a new instance every time it is requested.   
**Scoped** creates one instance per request.   
**Singleton** creates one instance for the entire application lifetime.

## Advanced backend questions   
### How do you design a production-grade Web API in .NET Core?
A senior design usually includes layered or clean architecture, proper validation, logging, global error handling, versioning, authentication, caching, health checks, and observability. The exact structure should support maintainability and independent deployment.

### How do you secure a .NET Core Web API?
Common practices include JWT authentication, authorization policies, HTTPS, input validation, secrets management, rate limiting, and secure token handling. For enterprise systems, identity integration and role/claim-based access are also important.

### What is the difference between authentication and authorization?
Authentication verifies who the user is. Authorization determines what that user is allowed to do.

### What is the purpose of API versioning?
API versioning helps you evolve endpoints without breaking existing clients. In .NET Core, versioning can be done using URL segments, query strings, or headers.

## Entity Framework Core questions   

### What is the difference between IEnumerable and IQueryable?
IEnumerable executes queries in memory, whereas IQueryable builds expression trees that EF Core can translate into SQL and execute on the database server.

### What are migrations in EF Core?
A: Migrations are a way to evolve the database schema as your model changes. They let you keep schema and code aligned across environments.

### How do you handle performance issues in EF Core?
A: Common improvements include projecting only needed columns, avoiding unnecessary Include, using pagination, avoiding N+1 queries, and choosing the correct tracking behavior.

## Architecture and patterns   

### What is Clean Architecture?
A: Clean Architecture separates core business logic from infrastructure and UI concerns. The goal is to keep business rules independent of frameworks and databases.

Q: What is CQRS?
A: CQRS separates read and write models. It can improve clarity, scalability, and performance when read and write concerns differ significantly.


## Senior-level scenario questions   
### How do you diagnose a production performance issue you cannot reproduce locally?
A: Start with metrics, logs, tracing, and infrastructure signals. Then narrow down whether the issue is CPU, memory, database latency, lock contention, thread starvation, network, or downstream dependency related.

### How would you handle a critical production outage?
A: First stabilize the system, then identify blast radius, roll back if needed, communicate clearly, and verify recovery with monitoring. Afterward, perform root-cause analysis and preventive actions.

### How do you structure a multi-tenant SaaS application in .NET Core?
A: Common approaches include shared database with tenant discriminator, separate schema per tenant, or separate database per tenant. The choice depends on isolation, cost, compliance, and scaling requirements.


Suggested prep topics
Focus your preparation on these areas:

ASP.NET Core pipeline, middleware, filters, and hosting model.

Dependency injection and lifetimes.

Authentication, authorization, JWT, and claims.

EF Core, LINQ, migrations, and query performance.

Clean Architecture, CQRS, messaging, and microservices.

Logging, monitoring, health checks, and incident handling.

Docker, containers, caching, and scalability
