
Core questions   
### What is .NET Core, and how is it different from .NET Framework?
.NET Core is a modern, open‑source, cross‑platform, high‑performance software development framework, designed for cloud and microservices. whereelse .NET Framework is the older, Windows‑only runtime mainly used for legacy enterprise applications.

### What are the main benefits of ASP.NET Core?   
Key benefits include built-in dependency injection, middleware-based request pipeline, better performance, cross-platform support, and strong support for cloud-native applications.

### What is middleware in ASP.NET Core?
Middleware in ASP.NET Core is a lightweight software component that sits in the HTTP request pipeline and processes incoming requests and outgoing responses.    
It can inspect, modify, or short‑circuit the pipeline.

  #### What Middleware Does
  - **Handles requests and responses** — every HTTP request passes through a chain of middleware components before reaching your endpoint, and the response travels back through them in reverse.
  - **Decides whether to continue the pipeline** — a middleware can pass the request to the next component or stop the pipeline (terminal middleware).
  - **Runs code before and after the next middleware** — enabling tasks like logging, authentication, routing, and error handling. 


A: Middleware is software that runs in the HTTP request/response pipeline. Each component can process a request, pass it to the next component, or short-circuit the pipeline.

Q: What is dependency injection in ASP.NET Core?
A: Dependency injection is a design pattern where dependencies are provided from outside the class rather than created internally. ASP.NET Core has built-in support for DI with transient, scoped, and singleton lifetimes.

Q: What is the difference between transient, scoped, and singleton services?
A: Transient creates a new instance every time it is requested. Scoped creates one instance per request. Singleton creates one instance for the entire application lifetime.

Advanced backend questions
Q: How do you design a production-grade Web API in .NET Core?
A: A senior design usually includes layered or clean architecture, proper validation, logging, global error handling, versioning, authentication, caching, health checks, and observability. The exact structure should support maintainability and independent deployment.

Q: How do you secure a .NET Core Web API?
A: Common practices include JWT authentication, authorization policies, HTTPS, input validation, secrets management, rate limiting, and secure token handling. For enterprise systems, identity integration and role/claim-based access are also important.

Q: What is the difference between authentication and authorization?
A: Authentication verifies who the user is. Authorization determines what that user is allowed to do.

Q: What is the purpose of API versioning?
A: API versioning helps you evolve endpoints without breaking existing clients. In .NET Core, versioning can be done using URL segments, query strings, or headers.

Q: Why is IHttpClientFactory recommended?
A: It helps avoid socket exhaustion, supports better handler management, and makes named or typed clients easier to configure and test.

Entity Framework Core questions
Q: What is the difference between IEnumerable and IQueryable?
A: IEnumerable works on in-memory collections, while IQueryable builds queries that can be translated and executed by a remote provider such as a database. In EF Core, IQueryable is usually preferred until query execution.

Q: What are migrations in EF Core?
A: Migrations are a way to evolve the database schema as your model changes. They let you keep schema and code aligned across environments.

Q: How do you handle performance issues in EF Core?
A: Common improvements include projecting only needed columns, avoiding unnecessary Include, using pagination, avoiding N+1 queries, and choosing the correct tracking behavior.

Architecture and patterns
Q: What is Clean Architecture?
A: Clean Architecture separates core business logic from infrastructure and UI concerns. The goal is to keep business rules independent of frameworks and databases.

Q: What is CQRS?
A: CQRS separates read and write models. It can improve clarity, scalability, and performance when read and write concerns differ significantly.

Q: What is the Saga pattern?
A: Saga manages distributed transactions across services using a sequence of local transactions and compensating actions instead of a single database transaction.

Q: When would you use a message broker instead of REST between services?
A: Use a broker when you need asynchronous communication, loose coupling, resilience, and better handling of spikes or eventual consistency. REST is better for synchronous request-response interactions.

Senior-level scenario questions
Q: How do you diagnose a production performance issue you cannot reproduce locally?
A: Start with metrics, logs, tracing, and infrastructure signals. Then narrow down whether the issue is CPU, memory, database latency, lock contention, thread starvation, network, or downstream dependency related.

Q: How would you handle a critical production outage?
A: First stabilize the system, then identify blast radius, roll back if needed, communicate clearly, and verify recovery with monitoring. Afterward, perform root-cause analysis and preventive actions.

Q: How do you structure a multi-tenant SaaS application in .NET Core?
A: Common approaches include shared database with tenant discriminator, separate schema per tenant, or separate database per tenant. The choice depends on isolation, cost, compliance, and scaling requirements.

Strong answer style for interviews
For 10 years’ experience, interviewers usually want more than definitions. They expect you to explain trade-offs, mention production experience, and justify decisions with examples from real systems.

A good answer structure is:

Define the concept briefly.

Explain why it matters in real projects.

Mention one trade-off or pitfall.

Give one practical example from production.

For example, if asked about caching, you can say that in-memory caching is fast but local to one instance, while distributed caching is better for scaled-out deployments. That kind of answer shows both technical understanding and system thinking.

Suggested prep topics
Focus your preparation on these areas:

ASP.NET Core pipeline, middleware, filters, and hosting model.

Dependency injection and lifetimes.

Authentication, authorization, JWT, and claims.

EF Core, LINQ, migrations, and query performance.

Clean Architecture, CQRS, messaging, and microservices.

Logging, monitoring, health checks, and incident handling.

Docker, containers, caching, and scalability
