# CTE (Common Table Expression) and a Subquery

The primary difference between a CTE (Common Table Expression) and a Subquery is readability and reusability

| Feature | CTE (WITH ...) | Subquery (SELECT (SELECT ...)) |
| --- | --- | --- |
| **Performance** | Same as a subquery | Same as a CTE |
| **Readability** | High — organized top‑to‑bottom | Low — nested inside brackets |
| **Reusability** | Can be referenced multiple times in the same query | Must be repeated or copy‑pasted |
| **Recursion** | Yes — supports recursion | No recursion support |
| **Scope** | Only lasts for the single query immediately following it | Only lasts for the immediate outer statement |
