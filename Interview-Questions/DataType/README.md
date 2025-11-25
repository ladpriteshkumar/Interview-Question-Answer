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
