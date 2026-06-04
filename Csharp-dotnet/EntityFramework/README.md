## What is Entity Framework ?
Entity Framework is Microsoft’s object–relational mapper (ORM) for .NET that lets you work with a relational database using C# classes instead of SQL, dramatically reducing the amount of data‑access code you need to write.

Entity Framework (EF) sits between your C# code and the database. Instead of manually writing SQL queries, opening connections, and mapping results


## What EF Core Does   
EF Core acts as a middle layer between your .NET application and your database:

- Maps entities (C# classes) to tables and columns
- Generates SQL for CRUD operations
- Tracks changes to objects
- Executes queries using LINQ
- Manages relationships, constraints, and transactions
- Supports schema evolution through migrations
- Works with many databases (SQL Server, PostgreSQL, MySQL, SQLite, Oracle via providers)


## Key Features 

- Cross‑platform (Windows, Linux, macOS)
- Lightweight & modular — install only the database provider you need
- High performance compared to classic EF
- Open source with active development on GitHub
- Supports Code‑First and Database‑First approaches (Code‑First is primary)
- LINQ querying for strongly typed, compile‑time‑checked queries
- Migrations to evolve your database schema over time
