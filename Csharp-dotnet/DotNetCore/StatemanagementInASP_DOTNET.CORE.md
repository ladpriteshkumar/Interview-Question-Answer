[REF](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/app-state?view=aspnetcore-10.0)
## State Management in ASP.NET Core
State management in .NET Core is the technique of preserving data across multiple requests in a web application. Since HTTP is stateless, the server forgets every interaction as soon as a request finishes.   
ASP.NET provides multiple techniques to maintain user data.   
*OR*
State management in .NET Core (specifically ASP.NET Core) refers to the techniques used to preserve data across multiple HTTP requests. Because HTTP is stateless, every request is independent.   
— so ASP.NET Core provides several mechanisms to maintain user data, application data, and UI state across requests.


## Types of State Management in ASP.NET Core
### 1️⃣ Client‑Side State Management   
Data stored in the browser.

**Cookies**   
- Small text data stored in the browser
- Good for user preferences, identifiers
- Limited to ~4 KB
- Sent with every request

**Query Strings**   
- Data appended to URLs
- Useful for navigation, bookmarking
- Visible to users

**Hidden Fields**   
- Used in forms to persist data across postbacks

**Local Storage / Session Storage (client-side JS)**
- Persistent (localStorage) or session‑based (sessionStorage)



### 2️⃣ Server‑Side State Management
Data stored on the server.

**Session State**   
- Stores user-specific data across requests
- Backed by server-side cache
- Good for carts, login info, temporary user data

Example:

```csharp
HttpContext.Session.SetString("UserName", "JohnDoe");
var user = HttpContext.Session.GetString("UserName");
```

**TempData**
- Persists data for one request (or until read)
- Great for redirect messages (e.g., “Profile updated!”)

**HttpContext.Items**
- Lives only for the current request
- Good for passing data between middleware

**Caching**   
- Stores frequently used data to improve performance
- Not user-specific

---



## ViewBag vs ViewData vs TempData

| Feature | ViewBag | ViewData | TempData |
| --- | --- | --- | --- |
| Type | Dynamic | Dictionary | Dictionary |
| Lifetime | Current request | Current request | One redirect |
| Syntax | ``ViewBag.Name`` | ``ViewData["Name"]`` | ``TempData["Name"]`` |
| Use Case | Simple data | Simple data | Redirect messages |
