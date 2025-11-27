
### What is an Event in C#?
- An event in C# is a mechanism for communication between objects.
- It allows one object (the publisher) to notify other objects (the subscribers) when something happens.
- Events are built on top of delegates — they use delegates to hold references to methods that should be called when the event is triggered.
- Commonly used in GUI applications (like button clicks) and in scenarios where you want to implement the Observer pattern.

### 🛠 How Events Work
- Declare a delegate that defines the signature of the event handler.
- Declare an event based on that delegate.
- Subscribe methods to the event.
- Raise (trigger) the event to call all subscribed methods.

#### Example
```csharp
using System;

public class Publisher
{
    // Step 1: Declare delegate
    public delegate void Notify(string message);

    // Step 2: Declare event based on delegate
    public event Notify OnProcessCompleted;

    public void StartProcess()
    {
        Console.WriteLine("Process started...");
        
        // Step 4: Raise event
        OnProcessCompleted?.Invoke("Process finished successfully!");
    }
}

public class Subscriber
{
    public void HandleNotification(string msg)
    {
        Console.WriteLine("Subscriber received: " + msg);
    }
}

class Program
{
    static void Main()
    {
        Publisher pub = new Publisher();
        Subscriber sub = new Subscriber();

        // Step 3: Subscribe to event
        pub.OnProcessCompleted += sub.HandleNotification;

        pub.StartProcess();
    }
}
```

### Ways to Subscribe to an Event in C#
- Named Method Subscription
  
Attach a method that matches the event delegate signature.
```csharp
publisher.MyEvent += SubscriberMethod;
```

- Anonymous Method
  
    Use the delegate keyword inline.
```csharp
publisher.MyEvent += delegate(string msg)
{
    Console.WriteLine("Anonymous handler: " + msg);
};
```

- Lambda Expression
  
    Use a lambda for concise inline handlers.
```csharp
publisher.MyEvent += (msg) => Console.WriteLine("Lambda handler: " + msg);
```

- Multiple Subscriptions (Multicast)
  
    Attach more than one handler to the same event.
```csharp
publisher.MyEvent += HandlerOne;
publisher.MyEvent += HandlerTwo;
```

- Static Method Subscription
  
    Subscribe a static method instead of an instance method.
```csharp
publisher.MyEvent += StaticHandler;
```

- Unsubscribe (for completeness)
  
    Detach a handler when you no longer need it.
```csharp
publisher.MyEvent -= SubscriberMethod;
```


✅ Interview-Ready Short Answer
"You can subscribe to an event in C# using a named method, an anonymous method, or a lambda expression. You can also attach multiple handlers (multicast) or even static methods. And you can unsubscribe using the -= operator."

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

