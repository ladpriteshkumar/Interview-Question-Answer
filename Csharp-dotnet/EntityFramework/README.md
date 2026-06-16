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



## What is Dapper ? (ORM)

## What is EDM (Entity Data Model)
EDM helps separate your application logic from the physical database structure, which makes systems easier to query, maintain, and evolve.

“EDM as a concept exists in EF Core (entities, relationships, mappings), but EF Core dropped the EDMX/designer XML workflow used by EF6. EF Core uses code‑first conventions, the Fluent API, runtime metadata, and scaffolding tools to represent and map the model.” 


**In Entity Framework’s Entity Data Model, an entity can be in one of five states: Added, Unchanged, Modified, Deleted, or Detached. These states drive what `SaveChanges()` will do (insert, update, delete, or nothing) and are managed by the DbContext change tracker.**   [Microsoft Learn](https://learn.microsoft.com/en-us/ef/ef6/saving/change-tracking/entity-state)

### Entity States (EDM)
- **Added**  
  **Meaning:** The entity is tracked by the context and will be inserted into the database on `SaveChanges()`.   [Microsoft Learn](https://learn.microsoft.com/en-us/ef/ef6/saving/change-tracking/entity-state)  
  **How to get it:** `context.Set<TEntity>().Add(entity)` or `context.Entry(entity).State = EntityState.Added`.  
  **After SaveChanges:** Becomes **Unchanged**.

- **Unchanged**  
  **Meaning:** The entity is tracked and its property values match the database snapshot; no SQL will be generated for it.   [Microsoft Learn](https://learn.microsoft.com/en-us/ef/ef6/saving/change-tracking/entity-state)

- **Modified**  
  **Meaning:** The entity is tracked and EF has detected (or you have marked) changes; an UPDATE will be sent on `SaveChanges()`.   [Microsoft Learn](https://learn.microsoft.com/en-us/ef/ef6/saving/change-tracking/entity-state)  
  **How to set manually:** `context.Entry(entity).State = EntityState.Modified`.  
  **Note:** When attaching a detached object you often need to set `Modified` explicitly to update all properties.   [Stack Overflow](https://stackoverflow.com/questions/71904606/what-are-the-differences-between-detached-and-modified-entity-framework-state)

- **Deleted**  
  **Meaning:** The entity is tracked and marked for deletion; `SaveChanges()` will issue a DELETE.  
  **How to get it:** `context.Set<TEntity>().Remove(entity)` or `context.Entry(entity).State = EntityState.Deleted`.  
  **After SaveChanges:** The entity is detached.

- **Detached**  
  **Meaning:** The entity is not being tracked by any context; EF will ignore it until attached.   [Microsoft Learn](https://learn.microsoft.com/en-us/ef/ef6/saving/change-tracking/entity-state)  
  **Common scenarios:** DTOs from the client, objects created outside the context, or after explicit detach. To persist changes you must attach and set the appropriate state.   [Stack Overflow](https://stackoverflow.com/questions/71904606/what-are-the-differences-between-detached-and-modified-entity-framework-state)  [sqlpey.com](https://sqlpey.com/c%23/fixing-entity-framework-state-conflicts/)

---

### Typical workflows and pitfalls
- **Attach then set state** for disconnected update scenarios: if an entity is detached (e.g., from a web API), attach it and set `EntityState.Modified` to update. Failing to attach or set state correctly can result in no update or unintended deletes.   [Stack Overflow](https://stackoverflow.com/questions/71904606/what-are-the-differences-between-detached-and-modified-entity-framework-state)  [sqlpey.com](https://sqlpey.com/c%23/fixing-entity-framework-state-conflicts/)  
- **Use AsNoTracking()** for read-only queries to avoid tracking overhead and accidental state conflicts.   [sqlpey.com](https://sqlpey.com/c%23/fixing-entity-framework-state-conflicts/)  
- **Be careful with partial updates:** setting `Modified` updates all mapped properties; to update specific properties, mark individual properties as modified: `context.Entry(entity).Property(e => e.Name).IsModified = true`.   [Microsoft Learn](https://learn.microsoft.com/en-us/ef/ef6/saving/change-tracking/entity-state)  [sqlpey.com](https://sqlpey.com/c%23/fixing-entity-framework-state-conflicts/)

---

### Quick code examples
```csharp
// Add
context.Blogs.Add(blog); // Added

// Attach and update (disconnected)
context.Attach(blog);
context.Entry(blog).State = EntityState.Modified; // Modified

// Remove
context.Blogs.Remove(blog); // Deleted

// Detach
context.Entry(blog).State = EntityState.Detached; // Detached
```

