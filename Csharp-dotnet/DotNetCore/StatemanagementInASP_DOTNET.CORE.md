[REF](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/app-state?view=aspnetcore-10.0)
## State Management in ASP.NET   
State management refers to preserving data across requests in a web application. Since HTTP is stateless, ASP.NET provides multiple techniques to maintain user data.

- Session state
  - Server-side storage tied to a user session.
     
- Cookies
  - Client-side storage in the browser.

- TempData
- Query Strings
- Route Values
- Hidden Fields
- caching



## ViewBag vs ViewData vs TempData

| Feature | ViewBag | ViewData | TempData |
| --- | --- | --- | --- |
| Type | Dynamic | Dictionary | Dictionary |
| Lifetime | Current request | Current request | One redirect |
| Syntax | ``ViewBag.Name`` | ``ViewData["Name"]`` | ``TempData["Name"]`` |
| Use Case | Simple data | Simple data | Redirect messages |
