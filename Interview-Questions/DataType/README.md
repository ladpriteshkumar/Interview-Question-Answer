### 1) What are Value types & Reference types?
### 2) What is Data Type? (Explain Data type in C#)

Data Type refers to the type of data that can be stored in a variable.C# is rich in data type which is mainly divided into two categories.

1. Value Type
    
2. Reference Type

![Screenshot](CsharpDataType.png)
          
## Value Type: 
* A value type variable stores actual values.
     
* Value types are stored in a stack and derived from System.ValueType class.

#### Behavior:
• 	When assigned to another variable, the data is copied.

• 	Each variable has its own independent copy.

• 	Changing one does not affect the other.


## Reference Type:   
* A reference type variable stores a reference to the actual value. Typically, a reference type contains a pointer to another memory location that stores the actual data. 
    
* Reference types are stored in a heap and derived from System.Object class.

#### Behavior:
• 	When assigned to another variable, the reference is copied, not the data.

• 	Both variables point to the same object in memory.

• 	Changing one affects the other.


## Key Differences between Value Types and Reference Types

| Aspect              | Value Types                          | Reference Types                     |
|---------------------|--------------------------------------|-------------------------------------|
| **Storage**         | Stored on the **stack**              | Stored on the **heap** (reference on stack) |
| **Copy Behavior**   | Copies the actual value              | Copies the reference (pointer)      |
| **Independence**    | Each variable has its own copy       | Multiple variables share the same object |
| **Examples**        | `int`, `float`, `struct`, `enum`     | `class`, `array`, `string`, `delegate` |
| **Default Value**   | Depends on type (e.g., `0` for int)  | `null`                              |




# 
# DataType in C#

[Reference](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/built-in-types)



# Built in Value Type
`bool`

`byte`
`sbyte` 

`char` 

`decimal` 
`double` 
`float` 
`int` 
`uint` 

`nint` 
`nuint` 

`short` 
`ushort` 

`long` 
`ulong` 



# Built in Reference Type
`object`
`string`
`dynamic`


# User Define Value Type
`struct`
`enum`


# User Define Reference Type
`class`
`interface`
`delegate`
`record`



# Record Types in C#
1. Reference Types (Record Class)
- Declared with record class (or just record by default).
- Behave like normal classes but with built-in value-based equality.
- Equality is based on the values of properties rather than object references.
- Example:
public record Person(string FirstName, string LastName);

var p1 = new Person("Alice", "Smith");
var p2 = new Person("Alice", "Smith");

Console.WriteLine(p1 == p2); // True (value equality)



2. Value Types (Record Struct)
- Declared with record struct.
- Behave like structs but also support value-based equality.
- Useful when you want lightweight, immutable data carriers.
- Example:
public record struct Point(int X, int Y);

var pt1 = new Point(10, 20);
var pt2 = new Point(10, 20);

Console.WriteLine(pt1 == pt2); // True (value equality)



3. Value Equality
- Unlike normal classes (which use reference equality by default), records automatically implement:
- Equals()
- GetHashCode()
- == and != operators
- This makes them perfect for data-centric applications like DTOs, immutable models, or pattern matching.

4. Extra Features
- With-expressions: Create modified copies easily.
var p3 = p1 with { LastName = "Johnson" };
- Deconstruction: Break records into components.
var (first, last) = p1;



👉 In short:
- Record class = reference type with value equality.
- Record struct = value type with value equality.
Both are designed to make working with immutable, data-focused objects much easier.

Would you like me to also show you when to choose record class vs record struct in real-world scenarios (like performance trade-offs and memory usage)?



