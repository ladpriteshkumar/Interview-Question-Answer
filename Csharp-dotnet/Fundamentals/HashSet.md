## What is Hashset ?

A HashSet<T> in C# is an unordered collection of unique elements optimized for very fast lookups, insertions, and deletions, typically in O(1) time. It is implemented internally using a hash table, which is why it enforces uniqueness and provides high performance. 

⭐ Core Definition
A HashSet is a collection that:

Stores only unique values (duplicates are automatically ignored).

Does not preserve order — elements are not stored by index.

Provides fast Add, Remove, and Contains operations due to hashing.

Supports set operations like union, intersection, and difference. 

---
# What is Hashtable ?
A Hashtable in C# is a non‑generic key/value collection that stores items based on the hash code of the key. The key is hashed to determine where the value is stored, which makes lookups generally fast.
