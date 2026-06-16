### Tracking versus No‑Tracking in EF Core

**Tracking** means EF Core’s **ChangeTracker** keeps references to entities returned from a query and monitors their property values so it can detect changes and persist them on `SaveChanges()`. **No‑tracking** queries return detached objects that EF does not monitor, which is faster and uses less memory for read‑only scenarios.

---

### How they work
- **Tracking**
  - EF materializes entities and stores them in the `ChangeTracker`.
  - Navigation fix‑up and identity resolution are applied (same DB row → same CLR instance).
  - When you modify a tracked entity, EF detects changes and generates minimal `UPDATE` statements on `SaveChanges()`.

- **No‑Tracking**
  - Use `AsNoTracking()` to skip the `ChangeTracker`.
  - Entities are returned detached; changes are ignored by EF unless you explicitly attach them.
  - Faster materialization and lower memory usage, but no automatic change detection or identity resolution (unless you use `AsNoTrackingWithIdentityResolution()`).

---

### When to use each
- **Use Tracking**
  - Typical CRUD flows where you read, modify, then save within the same `DbContext` lifetime.
  - When you rely on navigation property fix‑up or need identity resolution to maintain single instances.

- **Use No‑Tracking**
  - Read‑only endpoints, reporting, dashboards, or any large result sets.
  - High‑throughput APIs where you never update the returned entities.
  - When you want lower memory and CPU overhead.

---

### Common patterns and code examples
- **Default tracking query**
```csharp
var blog = await context.Blogs.SingleAsync(b => b.Id == id);
blog.Rating = 5;
await context.SaveChangesAsync(); // ChangeTracker detects and updates
```

- **No‑tracking read**
```csharp
var blogs = await context.Blogs
    .AsNoTracking()
    .Where(b => b.IsActive)
    .ToListAsync();
```

- **No‑tracking with identity resolution**
```csharp
var result = await context.Orders
    .AsNoTrackingWithIdentityResolution()
    .Include(o => o.Items)
    .ToListAsync();
```

- **Disconnected update (DTO → attach → partial update)**
```csharp
var dto = new BlogDto { Id = 1, Name = "New" };
var blog = new Blog { Id = dto.Id };
context.Blogs.Attach(blog);
context.Entry(blog).Property(b => b.Name).CurrentValue = dto.Name;
context.Entry(blog).Property(b => b.Name).IsModified = true;
await context.SaveChangesAsync();
```

---

### Pitfalls and practical tips
- **Unintended full updates**: Calling `Update()` on a detached/no‑tracking entity marks all properties modified and can overwrite columns. Prefer attaching and marking only changed properties.
- **Identity duplication**: `AsNoTracking()` can produce multiple instances for the same DB row when it appears multiple times in results; use `AsNoTrackingWithIdentityResolution()` if you need single instances without full tracking.
- **Default behavior**: You can change default query tracking via `ChangeTracker.QueryTrackingBehavior`, but do so carefully to avoid surprising behavior across the app.
- **Debugging**: Inspect `context.ChangeTracker.Entries()` or `context.Entry(entity).State` to see what EF will do on `SaveChanges()`.

---

### Quick interviewer‑ready summary
**“Tracking keeps entities in the ChangeTracker so EF can detect and persist changes; use it for CRUD. No‑tracking returns detached objects for faster, read‑only queries; use `AsNoTracking()` for performance and `AsNoTrackingWithIdentityResolution()` when you need identity resolution without full tracking.”**
