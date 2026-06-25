> ### [`In` VS `Exist`](https://github.com/ladpriteshkumar/Interview-Question-Answer/blob/main/SQL/In_V_Exists.md)

> ### Difference Between Count(*) and Count(column) ?

| Function | What it counts | Includes NULLs? | Example result |
| --- | --- | --- | --- |
| *COUNT(\\*)* | Every row in the result set | **Yes** | If a table has 10 rows → returns **10** |
| **COUNT(column)** | Only rows where *column is NOT NULL* | **No** | If column has 7 non‑NULL values → returns **7** |


> ### Ranking Function Comparison Table

| Function | How It Handles Ties | Sequence Example (tie at 2nd place) |
| --- | --- | --- |
| **ROW_NUMBER()** | Assigns numbers arbitrarily. No duplicates. | 1, 2, 3, 4, 5 |
| **RANK()** | Assigns the same rank, but *skips* the next number(s). | 1, 2, 2, 4, 5 |
| **DENSE_RANK()** | Assigns the same rank, and *does not* skip numbers. | 1, 2, 2, 3, 4 |

