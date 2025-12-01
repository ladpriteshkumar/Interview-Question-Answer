
### sum of n natural numbers

```csharp

static int SumofNaturialNumbers(int n) {
    var result = 0;
    for (int i = 1; i <= n; i++) {
        result += i;
    }
    return result;       
}

Console.WriteLine(SumofNaturialNumbers(5)); //output 15
```
