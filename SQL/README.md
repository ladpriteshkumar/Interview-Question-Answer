### Ranking Function Comparison Table

| Function | How It Handles Ties | Sequence Example (tie at 2nd place) |
| --- | --- | --- |
| **ROW_NUMBER()** | Assigns numbers arbitrarily. No duplicates. | 1, 2, 3, 4, 5 |
| **RANK()** | Assigns the same rank, but *skips* the next number(s). | 1, 2, 2, 4, 5 |
| **DENSE_RANK()** | Assigns the same rank, and *does not* skip numbers. | 1, 2, 2, 3, 4 |

