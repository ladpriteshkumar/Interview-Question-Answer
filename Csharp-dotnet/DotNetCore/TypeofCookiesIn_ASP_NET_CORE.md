
# Type of Cookies in ASP.NET core

# The Whole Picture of Cookies in ASP.NET Core

Cookies in ASP.NET Core can be understood across four dimensions:

1. **By Lifetime**  
2. **By Purpose**  
3. **By Security Behavior**  
4. **By Framework Feature**

This document provides a complete, copy‑paste‑ready Markdown reference for cookies in ASP.NET Core.

---

## 1. Cookies by Lifetime

### A. Session Cookies
- **Description:** No explicit expiration; deleted when the browser closes.  
- **Use cases:** Temporary data such as session identifiers or short‑lived authentication tickets.

### B. Persistent Cookies
- **Description:** Have an expiration date and are stored on disk.  
- **Use cases:** “Remember Me” login, long‑term preferences, language or theme settings.

---

## 2. Cookies by Purpose

### A. Authentication Cookies
- **Created by:** Cookie authentication middleware or ASP.NET Core Identity.  
- **Stores:** User identity, claims, authentication metadata, expiration.  
- **Example name:** `.AspNetCore.Identity.Application` (Identity) or custom names for cookie auth.

### B. Session Cookies (Session Middleware)
- **Created by:** `AddSession()` middleware.  
- **Stores in cookie:** Session ID only; actual session data is stored server‑side (in memory, distributed cache, etc.).  
- **Example name:** `.AspNetCore.Session`

### C. Anti‑Forgery Cookies
- **Purpose:** CSRF protection; used together with form tokens.  
- **Behavior:** Framework issues a cookie token and expects a matching form token on POST.  
- **Example name pattern:** `.AspNetCore.Antiforgery.*`

### D. TempData Cookies
- **Purpose:** Persist TempData when using the cookie TempData provider (instead of session).  
- **Behavior:** Stores TempData payload in an encrypted cookie for the next request.  
- **Example name:** `TempData` (or configured name)

### E. Custom Application Cookies
- **Created by:** `Response.Cookies.Append()` or middleware.  
- **Use cases:** UI preferences (theme, language), feature flags, lightweight tracking.

**Example:**
```csharp
var options = new CookieOptions
{
    Expires = DateTimeOffset.UtcNow.AddDays(30),
    HttpOnly = true,
    Secure = true,
    SameSite = SameSiteMode.Lax
};
Response.Cookies.Append("Theme", "Dark", options);
```

---

## 3. Cookies by Security Behavior

### A. HttpOnly Cookies
- **Description:** Not accessible via JavaScript (`document.cookie`).  
- **Benefit:** Mitigates risk from XSS attacks for sensitive cookies.
```csharp
options.HttpOnly = true;
```

### B. Secure Cookies
- **Description:** Sent only over HTTPS connections.  
- **Benefit:** Prevents cookie interception over insecure channels.
```csharp
options.Secure = CookieSecurePolicy.Always;
```

### C. SameSite Cookies
- **Description:** Controls cross‑site request behavior.
  - `Strict` — cookie not sent on cross‑site requests.
  - `Lax` — cookie sent on top‑level navigations (default for many scenarios).
  - `None` — cookie sent on cross‑site requests (requires `Secure`).
```csharp
options.SameSite = SameSiteMode.Strict;
```

### D. Essential Cookies
- **Description:** Marked as essential for site functionality; exempt from consent requirements in GDPR/consent middleware.  
- **Use cases:** Session cookie, auth cookie, anti‑forgery cookie.
```csharp
options.IsEssential = true;
```

---

## 4. Cookies by Framework Feature

| Framework Feature | Cookie Used | Purpose |
|-------------------|-------------|---------|
| Authentication | Auth cookie | Stores identity and claims |
| ASP.NET Core Identity | Identity cookie | Login, 2FA, external login flows |
| Session | Session cookie | Session ID for server‑side session store |
| Anti‑Forgery | Anti‑forgery cookie | CSRF protection token |
| TempData | TempData cookie | One‑time messages or data between requests |
| Custom Logic | Custom cookies | Preferences, UI state, tracking |

---

## Common Cookie Operations (Code Examples)

### Create a cookie
```csharp
var options = new CookieOptions
{
    Expires = DateTimeOffset.UtcNow.AddDays(7),
    HttpOnly = true,
    Secure = true,
    SameSite = SameSiteMode.Lax,
    IsEssential = true
};
Response.Cookies.Append("UserPref", "value", options);
```

### Read a cookie
```csharp
if (Request.Cookies.TryGetValue("UserPref", out var value))
{
    // use value
}
```

### Delete a cookie
```csharp
Response.Cookies.Delete("UserPref");
```

### Configure cookie authentication (Startup / Program)
```csharp
services.AddAuthentication(CookieAuthenticationDefaults.AuthenticationScheme)
    .AddCookie(options =>
    {
        options.Cookie.Name = ".MyApp.Auth";
        options.Cookie.HttpOnly = true;
        options.Cookie.SecurePolicy = CookieSecurePolicy.Always;
        options.Cookie.SameSite = SameSiteMode.Lax;
        options.ExpireTimeSpan = TimeSpan.FromDays(14);
        options.SlidingExpiration = true;
        options.Cookie.IsEssential = true;
    });
```

### Configure session (Startup / Program)
```csharp
services.AddDistributedMemoryCache();
services.AddSession(options =>
{
    options.Cookie.Name = ".AspNetCore.Session";
    options.Cookie.HttpOnly = true;
    options.Cookie.IsEssential = true;
    options.IdleTimeout = TimeSpan.FromMinutes(20);
});
app.UseSession();
```

---

## Best Practices

- **Use HttpOnly and Secure** for sensitive cookies (auth, session).  
- **Prefer SameSite=Lax** for most auth flows; use `None` only when cross‑site requests are required and ensure `Secure` is enabled.  
- **Minimize data stored in cookies.** Store identifiers in cookies and keep actual data server‑side.  
- **Set `IsEssential = true`** only for cookies that are strictly required for functionality; otherwise respect user consent.  
- **Use short lifetimes** for sensitive cookies and consider sliding expiration for auth cookies.  
- **Encrypt and sign cookie contents** when storing sensitive or structured data (use data protection or framework providers).  
- **Avoid storing secrets or large payloads** in cookies. Cookies should be small (typical browser limits ~4 KB per cookie).  
- **Use secure storage for session data** in production (distributed cache like Redis) when running multiple instances.

---

## Troubleshooting and Debugging Tips

- **Browser DevTools → Application → Cookies** to inspect cookie names, values, flags, and expiration.  
- **Check SameSite behavior** across browsers; older browsers may treat `SameSite=None` differently.  
- **Verify HTTPS** when using `SameSite=None` and `Secure`.  
- **Confirm cookie path and domain** if cookies are not being sent as expected.  
- **Use logging** in middleware to trace cookie creation and deletion.

---

## Summary Map

- **By Lifetime:** Session, Persistent  
- **By Purpose:** Authentication, Session, Anti‑Forgery, TempData, Custom  
- **By Security:** HttpOnly, Secure, SameSite, Essential  
- **By Framework:** Identity, Cookie Authentication, Session, TempData, Custom middleware

---

## Quick Cheat Sheet

- Create cookie: `Response.Cookies.Append("Name", "Value", options)`  
- Read cookie: `Request.Cookies["Name"]` or `TryGetValue`  
- Delete cookie: `Response.Cookies.Delete("Name")`  
- Mark essential: `options.IsEssential = true`  
- Make HttpOnly: `options.HttpOnly = true`  
- Require HTTPS: `options.Secure = CookieSecurePolicy.Always`  
- Control cross‑site: `options.SameSite = SameSiteMode.Lax`

---

End of document.
