
## What Is Middleware in ASP.NET Core?   
Middleware in ASP.NET Core is a component that sits in the HTTP request pipeline and processes incoming requests and outgoing responses.

Every request passes through a sequence of middleware components before it reaches your controller, and then passes back through them on the way out.

## Simple Definition   
Middleware is code that runs before and after your request reaches your controller, allowing you to inspect, modify, or block the request or response.

## What Middleware Can Do  
- Run logic before the request reaches the controller
- Run logic after the controller sends a response
- Modify the request
- Modify the response
- Stop the request completely
- Handle errors globally
- Add cross‑cutting features (logging, auth, caching, etc.)

## Why Middleware Is Useful   
Middleware is ideal for logic that applies to many endpoints, such as:

- Logging
- Authentication / JWT validation
- CORS
- Exception handling
- Rate limiting
- Adding custom headers
- URL rewriting
- Response compression

Instead of repeating code in every controller, you write it once in middleware.


## How Middleware Works (Pipeline Flow)
```
Incoming Request
      ↓
[Middleware 1]
      ↓
[Middleware 2]
      ↓
[Middleware 3]
      ↓
Controller
      ↑
Response goes back through the same middleware
```

Each middleware can:   
- Pass the request to the next component
- Modify the request or response
- Stop the pipeline
- Handle errors


# ⭐ How to Create Custom Middleware in ASP.NET Core

Creating custom middleware in ASP.NET Core involves **three main steps**:

1. Create the middleware class  
2. Register it in the request pipeline  
3. (Optional) Add an extension method for cleaner usage  

---

## ✅ 1. Create a Middleware Class

A middleware class must:

- Accept `RequestDelegate` in the constructor  
- Contain an `Invoke` or `InvokeAsync` method  
- Call `_next(context)` to continue the pipeline  

### **Example: Logging Middleware**

```csharp
public class LoggingMiddleware
{
    private readonly RequestDelegate _next;

    public LoggingMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        Console.WriteLine($"➡️ Request: {context.Request.Method} {context.Request.Path}");

        await _next(context); // Pass to next middleware

        Console.WriteLine($"⬅️ Response: {context.Response.StatusCode}");
    }
}
```

✅ 2. Register Middleware in Program.cs   
Add your middleware to the pipeline:
```
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.UseMiddleware<LoggingMiddleware>();

app.MapControllers();
app.Run();
```
Note: Middleware runs in the order it is registered.

## Example of Middleware

```csharp
public class AdminCheckMiddleware
{
    private readonly RequestDelegate _next;

    public AdminCheckMiddleware(RequestDelegate next)
    {
        _next = next;
    }

    public async Task InvokeAsync(HttpContext context)
    {
        if (context.Request.Headers["role"] != "admin")
        {
            context.Response.StatusCode = 403;
            await context.Response.WriteAsync("Forbidden");
            return;
        }

        await _next(context);
    }
}
```
register it   
```csharp
app.UseMiddleware<AdminCheckMiddleware>();
```

## Explain Middleware in ASP.NET Core ?

A component that sits in the HTTP pipeline and processes requests and responses.

Every request your application receives passes through a pipeline of middleware components before it reaches your controller, and then passes back through them on the way out.

Think of it like airport security:   
Each checkpoint (middleware) can inspect, modify, allow, or stop the request.

{Ref](https://www.c-sharpcorner.com/article/overview-of-middleware-in-asp-net-core/)
