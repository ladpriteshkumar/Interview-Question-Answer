## What are events in C#?

Events in C# are a way for one object (the publisher) to notify other objects (subscribers) when something of interest occurs. They’re built on delegates, which define the method signature that event handlers must follow. Using the `event` keyword, C# enforces encapsulation so only the publisher can raise the event, while subscribers can attach or detach their handlers. This supports a clean publisher–subscriber model, promotes loose coupling, and allows multiple subscribers to react differently to the same event. Events are widely used in GUI programming, asynchronous operations, and messaging systems.

### 🧩 Example (Concise for Interview)
```csharp
public class Alarm
{
    public event EventHandler AlarmTriggered;

    public void TriggerAlarm()
    {
        AlarmTriggered?.Invoke(this, EventArgs.Empty);
    }
}

class Program
{
    static void Main()
    {
        Alarm alarm = new Alarm();
        alarm.AlarmTriggered += (s, e) => Console.WriteLine("Alarm received!");
        alarm.TriggerAlarm();
    }
}
```

#### Explanation:
- event EventHandler AlarmTriggered; → declares the event.
- AlarmTriggered?.Invoke(...) → raises the event.
- += → subscribes a handler.

### 🚀 Key Points to Emphasize in Interview
- Events = notification mechanism based on delegates.
- Publisher–Subscriber pattern → loose coupling.
- Only publisher can raise, subscribers can listen.
- Common in UI frameworks, async callbacks, and messaging.

#### Another Example
```csharp
using System;

public class BankAccount
{
    private decimal _balance;

    // Declare the event
    public event EventHandler<BalanceChangedEventArgs> BalanceChanged;

    public void Deposit(decimal amount)
    {
        _balance += amount;
        OnBalanceChanged(amount, _balance);
    }

    public void Withdraw(decimal amount)
    {
        if (amount <= _balance)
        {
            _balance -= amount;
            OnBalanceChanged(-amount, _balance);
        }
        else
        {
            Console.WriteLine("Insufficient funds!");
        }
    }

    // Protected virtual method to raise the event
    protected virtual void OnBalanceChanged(decimal change, decimal newBalance)
    {
        BalanceChanged?.Invoke(this, new BalanceChangedEventArgs(change, newBalance));
    }
}

// Custom EventArgs to carry extra data
public class BalanceChangedEventArgs : EventArgs
{
    public decimal Change { get; }
    public decimal NewBalance { get; }

    public BalanceChangedEventArgs(decimal change, decimal newBalance)
    {
        Change = change;
        NewBalance = newBalance;
    }
}

public class AccountListener
{
    public void OnBalanceChanged(object sender, BalanceChangedEventArgs e)
    {
        Console.WriteLine($"Balance changed by {e.Change}. New balance: {e.NewBalance}");
    }
}

class Program
{
    static void Main()
    {
        BankAccount account = new BankAccount();
        AccountListener listener = new AccountListener();

        // Subscribe to the event
        account.BalanceChanged += listener.OnBalanceChanged;

        // Perform operations
        account.Deposit(100);
        account.Withdraw(40);
        account.Withdraw(70);
    }
}
```

