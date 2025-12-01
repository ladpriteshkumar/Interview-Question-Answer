### Multiplication table

Given a number n, we need to print its table. 

Examples : 

Input:  5
Output: 
5 * 1 = 5

5 * 2 = 10

5 * 3 = 15

5 * 4 = 20

5 * 5 = 25

5 * 6 = 30

5 * 7 = 35

5 * 8 = 40

5 * 9 = 45

5 * 10 = 50


```csharp
static void PrintTableOfNumber(int number)
{
    for (int i = 1; i <= 10; i++) {
    
        var result = number * i;
        Console.WriteLine($"{number} X {i} = {result}" );
    }
   
}
PrintTableOfNumber(5);
```
