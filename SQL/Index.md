### Indexes at a glance
| **Attribute** | **Benefit** | **Cost** | **When to use** | **Mitigation** |
|---|---:|---:|---|---|
| **Read performance** | **Speeds SELECTs** by avoiding full table scans; faster lookups | **Extra storage** for index pages | Frequent point lookups and range queries | Create targeted indexes; avoid indexing low‑selectivity columns |
| **Sort and seek** | **Speeds ORDER BY and JOIN** operations by providing ordered access | **Slower writes** (INSERT/UPDATE/DELETE) due to maintenance | Queries with ORDER BY, JOIN keys, or WHERE filters | Use covering indexes and include only needed columns |
| **Covering index** | Can satisfy query from index alone; eliminates lookups | Larger index size if many included columns | Hot read queries that select few columns | Include only non‑key columns that are frequently returned |
| **Composite index** | Supports multi‑column filters and left‑prefix searches | Wrong column order makes it ineffective | Queries filtering on multiple columns in same order | Order columns by selectivity and query patterns |
| **Unique index** | Enforces uniqueness and speeds lookups | Same write overhead; may require careful design | Keys that must be unique (natural keys) | Use when business rules require uniqueness |

---

### What an index is
An **index** is a separate data structure (usually a B‑tree or similar) that maps key values to row locations so the database can find rows without scanning the entire table. Indexes can be **single‑column**, **composite**, **covering** (includes non‑key columns), or **unique**.

---

### Pros of indexes
- **Much faster reads** for lookups, range scans, and ordered results.  
- **Efficient joins** when join keys are indexed.  
- **Reduced I/O** because fewer pages are read from disk.  
- **Can enforce constraints** (unique indexes).  
- **Enables covering queries** so the engine can return results from the index alone.

---

### Cons of indexes
- **Write penalty**: every INSERT/UPDATE/DELETE must update indexes, increasing latency.  
- **Storage overhead**: indexes consume disk space and memory (buffer pool).  
- **Maintenance cost**: fragmentation requires rebuilds/reorgs; more indexes mean more maintenance.  
- **Can be misused**: too many or poorly ordered indexes can be useless or harmful.  
- **Planner complexity**: optimizer may choose a suboptimal index if statistics are stale.

---

### When to add an index
- **High‑frequency read paths** where the same WHERE/JOIN/ORDER BY appears.  
- **Selective predicates** (filters that return a small fraction of rows).  
- **Columns used in JOINs or foreign keys**.  
- **Columns used in ORDER BY or GROUP BY** when sorting is a bottleneck.  
- **When a query is I/O bound and the index can reduce scanned pages.**

---

### How to design and mitigate downsides
- **Measure first**: capture query plans and timings; add indexes for the highest‑impact queries.  
- **Prefer narrow indexes**: index only the columns needed for seeks; use `INCLUDE` for extra return columns.  
- **Composite index order**: put the most selective and most commonly filtered column first.  
- **Use covering indexes** for hot read queries to avoid lookups.  
- **Limit number of indexes** on write‑heavy tables; consider filtered indexes for sparse predicates.  
- **Maintain statistics and rebuild fragmented indexes** on a schedule appropriate for your workload.  
- **Test write throughput** after adding indexes to ensure acceptable latency.

---

### Quick examples
- **Create a simple index**
```sql
CREATE INDEX IX_Orders_CustomerId ON Orders(CustomerId);
```
- **Create a composite covering index**
```sql
CREATE INDEX IX_Orders_CustomerDate ON Orders(CustomerId, OrderDate)
INCLUDE (TotalAmount);
```
- **Filtered index for sparse predicate**
```sql
CREATE INDEX IX_Orders_StatusOpen ON Orders(Status)
WHERE Status = 'Open';
```

---

### Interview‑ready summary
**“Indexes speed reads and joins by providing ordered access paths, but they add storage and slow writes because the database must maintain them. Add indexes only after measuring query hotspots, prefer narrow and covering indexes for read‑heavy paths, order composite keys by selectivity, and balance the number of indexes on write‑heavy tables. Monitor statistics and rebuild indexes as needed.”**

If you want, I can analyze a specific slow query or table schema and recommend exact indexes and expected tradeoffs.
