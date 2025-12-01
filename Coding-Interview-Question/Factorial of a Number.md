
### Given the non-negative integers n , compute the factorial of a given number.
Note: Factorial of n is defined as n * (n -1) * (n - 2) * ... * 1, for n = 0, factorial is 1.


```csharp

// Iterative Solution (Loop)
static int Factorial_Iterative(int n)
{
    if (n < 0) throw new ArgumentException("Negative numbers not allowed");
    var result = 1;
    for (int i = 1; i <= n; i++)
    {
        //result = result * i;
        result  *= i;
    }
    return result;
}
Console.WriteLine(Factorial_Iterative(4)); //output 24



// Recursive Solution
int Factorial_Recursive(int n)
{
    if (n < 0) throw new ArgumentException("Negative numbers not allowed");
    return n == 0 ? 1 : n * Factorial_Recursive(n - 1);
}
Console.WriteLine(Factorial_Recursive(5)); //output 120



//Using LINQ
int Factorial_LINQ(int n)
{
    if (n < 0) throw new ArgumentException("Negative numbers not allowed");
    return Enumerable.Range(1, n).Aggregate(1, (acc, val) => acc * val);
}
Console.WriteLine(Factorial_LINQ(6));  //output 720

```
