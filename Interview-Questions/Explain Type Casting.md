

### 🎯 What is Type Casting?
Type casting is the process of converting one data type into another. It allows you to treat a variable of one type as another type, either temporarily or permanently.

🧩 Types of Casting
1. Implicit Casting (Type Conversion)
- Definition: Automatically performed by the compiler when there is no risk of data loss.
- Direction: Smaller → larger type (safe conversion).
- Examples:
```csharp
int num = 100;
double d = num;   // implicit casting: int → double
```
- Notes: No explicit syntax required.


2. Explicit Casting
- Definition: Manually performed by the programmer using a cast operator (type).
- Direction: Larger → smaller type, or between incompatible types.
- Examples:
```csharp
double d = 9.78;
int i = (int)d;   // explicit casting: double → int (fraction lost)
```
- Notes: May cause data loss or runtime exceptions.


3. Boxing and Unboxing (Special Case in .NET)
- Boxing: Converting a value type into a reference type (object).
- Unboxing: Extracting the value type back from the object.
- Example:
```csharp
int num = 42;
object obj = num;       // boxing
int val = (int)obj;     // unboxing
```


4. Using as Operator (Safe Casting)
- Definition: Attempts to cast an object to a type. Returns null if it fails instead of throwing an exception.
- Example:
```csharp
object obj = "Hello";
string str = obj as string;   // str = "Hello"
int? num = obj as int?;       // num = null (safe failure)
```


5. Using is Operator (Type Checking)
- Definition: Checks if an object is of a given type before casting.
- Example:
```csharp
object obj = 42;
if (obj is int)
{
    int num = (int)obj;   // safe cast
}
```


# Summary of Type Casting in .NET

| Casting Type        | Description                                | Risk/Notes                          |
|---------------------|--------------------------------------------|-------------------------------------|
| **Implicit**        | Automatic, safe conversions                | No data loss, compiler handles it   |
| **Explicit**        | Manual, forced conversions                 | Possible data loss or exceptions    |
| **Boxing/Unboxing** | Value ↔ Reference type conversions         | Performance overhead, type safety   |
| **`as` Operator**   | Safe cast, returns `null` if fails         | No exception, but must check `null` |
| **`is` Operator**   | Type check before casting                  | Prevents runtime exceptions         |



### What can happen during explicit casting ?

##### Summary of Explicit Casting Outcomes

| Scenario                  | What Happens                                |
|---------------------------|---------------------------------------------|
| Correct type              | Cast succeeds                               |
| Wrong type                | `InvalidCastException` at runtime           |
| Numeric narrowing         | Data loss (precision/truncation)            |
| Boxing/unboxing mismatch  | Exception if types don’t match exactly      |
| Frequent casting          | Performance overhead                        |













