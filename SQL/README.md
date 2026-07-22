> ## [`In` VS `Exist`](https://github.com/ladpriteshkumar/Interview-Question-Answer/blob/main/SQL/In_V_Exists.md)

> ## [Materialized View OR Indexed View](https://github.com/ladpriteshkumar/Interview-Question-Answer/blob/main/SQL/materialized_OR_Indexed_View.md)

> ## `SET NO COUNT NO`
`SET NOCOUNT ON` prevents SQL Server from returning the informational message like “(5 rows affected)” after each DML or SELECT statement; `SET NOCOUNT OFF` (the default) returns that message

### Why you might use it
**Performance and network reduction**  
When a stored procedure executes many statements or loops, each “rows affected” message is an extra small result set sent to the client. Suppressing those messages reduces network traffic and client-side processing, which can yield measurable performance gains for high-volume or chatty procedures.


> ## What `@@ROWCOUNT` does  `
`@@ROWCOUNT` returns the number of rows affected by the last statement and is still updated even when NOCOUNT is ON;

```SQL
CREATE PROCEDURE dbo.ExampleProc
AS
BEGIN
  SET NOCOUNT ON;  -- suppress "(N rows affected)" messages
  UPDATE dbo.MyTable SET Col = 1 WHERE SomeFlag = 0;
  IF @@ROWCOUNT = 0
    PRINT 'No rows updated';
  ELSE
    PRINT 'Rows updated: ' + CAST(@@ROWCOUNT AS varchar(10));
END

```

> ## `COALESCE` Function
`COALESCE` takes two or more expressions and returns the first one that is not NULL. If all arguments are NULL, it returns NULL.

### Common uses and examples
- **Replace NULL with a default value:**

```sql
SELECT COALESCE(bonus, 0) AS bonus_or_zero FROM employees;
```
- **Choose the first available value across columns:**

```sql
SELECT COALESCE(phone_mobile, phone_home, phone_work) AS contact_phone FROM contacts;
```
> ## Difference Between Count(*) and Count(column) ?

| Function | What it counts | Includes NULLs? | Example result |
| --- | --- | --- | --- |
| **`COUNT(*)`** | Every row in the result set | **Yes** | If a table has 10 rows → returns **10** |
| **`COUNT(column)`** | Only rows where *column is NOT NULL* | **No** | If column has 7 non‑NULL values → returns **7** |


> ### Ranking Function Comparison Table

| Function | How It Handles Ties | Sequence Example (tie at 2nd place) |
| --- | --- | --- |
| **ROW_NUMBER()** | Assigns numbers arbitrarily. No duplicates. | 1, 2, 3, 4, 5 |
| **RANK()** | Assigns the same rank, but *skips* the next number(s). | 1, 2, 2, 4, 5 |
| **DENSE_RANK()** | Assigns the same rank, and *does not* skip numbers. | 1, 2, 2, 3, 4 |

