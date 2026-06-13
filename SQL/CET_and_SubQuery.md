# CTE (Common Table Expression) and a Subquery

The primary difference between a CTE (Common Table Expression) and a Subquery is readability and reusability

| Feature | CTE (WITH ...) | Subquery (SELECT (SELECT ...)) |
| --- | --- | --- |
| **Performance** | Same as a subquery | Same as a CTE |
| **Readability** | High — organized top‑to‑bottom | Low — nested inside brackets |
| **Reusability** | Can be referenced multiple times in the same query | Must be repeated or copy‑pasted |
| **Recursion** | Yes — supports recursion | No recursion support |
| **Scope** | Only lasts for the single query immediately following it | Only lasts for the immediate outer statement |



## CTE (Common Table Expression)
A **CTE (Common Table Expression)** is a **temporary, named result set** defined at the start of a SQL statement using the `WITH` keyword. It exists **only for the duration of the single query that follows it** and helps make complex queries easier to read, organize, and maintain.

CTE behaves like a virtual table that improves readability and allows you to structure logic step‑by‑step.

---

###  Key Characteristics
- **Defined using `WITH`**  
- **Exists only for one query**  
- **Improves readability** 
- **Can be referenced multiple times**  
- **Supports recursion**
---

###  Simple Example
```sql
WITH SalesCTE AS (
    SELECT EmployeeID, SUM(Amount) AS TotalSales
    FROM Sales
    GROUP BY EmployeeID
)
SELECT *
FROM SalesCTE
WHERE TotalSales > 50000;
```

### Example ( referenced multiple times )
```
WITH SalesCTE AS (
    SELECT 
        EmployeeID,
        SUM(Amount) AS TotalSales
    FROM Sales
    GROUP BY EmployeeID
)
SELECT 
    s.EmployeeID,
    s.TotalSales,
    -- First reference: filter
    CASE 
        WHEN s.TotalSales > 50000 THEN 'Top Performer'
        ELSE 'Regular'
    END AS PerformanceCategory,
    -- Second reference: percentage of total
    s.TotalSales * 1.0 / (SELECT SUM(TotalSales) FROM SalesCTE) AS PercentOfCompanySales
FROM SalesCTE s
ORDER BY s.TotalSales DESC;

```



---

### **Recursive CTE Example (Generate Numbers 1–10)**
This example generates a sequence of numbers from **1 to 10** using a recursive CTE.
**clean, real SQL example** showing how a **CTE supports recursion** — something subqueries cannot do.

```sql
WITH RECURSIVE Numbers AS (
    -- Anchor member (starting point)
    SELECT 1 AS n
    
    UNION ALL
    
    -- Recursive member (keeps adding 1)
    SELECT n + 1
    FROM Numbers
    WHERE n < 10
)
SELECT *
FROM Numbers;
```

---

## 🧠 How it works

### 1️⃣ **Anchor Query**
Runs once.

```sql
SELECT 1 AS n
```

This creates the first row:  
`n = 1`

### 2️⃣ **Recursive Query**
Runs repeatedly, each time using the previous result.

```sql
SELECT n + 1 FROM Numbers WHERE n < 10
```

This produces:

2  
3  
4  
…  
10

### 3️⃣ **Termination**
The recursion stops when:

```sql
WHERE n < 10
```

is no longer true.

---

## 📌 Output

| n |
|---|
| 1 |
| 2 |
| 3 |
| … |
| 10 |


