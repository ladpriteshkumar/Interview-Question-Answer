
## Difference Web API Vs Rest API   
REST API is a design style; Web API is a framework used to build APIs that may or may not follow REST principles.

---
REST API is an architectural style for building APIs.

Web API is a framework (in .NET) used to build HTTP services — and it can be RESTful, but doesn’t have to be.


### ✅ REST API (Representational State Transfer)   
REST is not a technology or framework — it’s a set of rules/constraints for designing networked applications.

A REST API must follow principles like:
- Client–server architecture   
  The client (frontend) and server (backend) are separated.   
  Client handles UI/UX
  Server handles data and logic
- Stateless communication
- Resource-based URLs
- HTTP methods used properly (GET, POST, PUT, DELETE)
- Representations (JSON, XML, etc.)
- Cacheable responses



## How a Web API Can Not Be a REST API
A Web API is a framework for building HTTP services.
A REST API must follow REST architectural constraints.
A Web API becomes non‑REST when it violates these rules.

## 1. Not using proper HTTP verbs   
REST requires meaningful use of HTTP methods.

❌ Non‑REST:

```http
POST /GetAllProducts
POST /DeleteProduct
POST /UpdateProduct
```
✔️ RESTful:

```http
GET /products
DELETE /products/10
PUT /products/10
```

## 2. Not using resource-based URLs   
REST uses nouns, not verbs.

❌ Non‑REST:

```http
GET /GetProductsList
GET /FetchProductById?id=10
```
✔️ RESTful:

```http
GET /products
GET /products/10
```

## 3. Using server-side session state   
REST requires statelessness.

❌ Non‑REST:

```csharp
HttpContext.Session.SetString("UserId", "123");
```
✔️ RESTful:

No server session

Client stores state (JWT, cookies, tokens)

## 4. Returning HTML instead of JSON/XML   
REST returns representations, not views.

❌ Non‑REST:

Returning Razor views

Returning HTML pages

✔️ RESTful:

JSON responses

XML if needed

## 5. Not supporting caching   
REST requires cacheable responses.

❌ Non‑REST:

Disabling caching everywhere

Missing cache headers

✔️ RESTful:

Proper Cache-Control, ETag, Expires

## 6. Using RPC-style endpoints   
RPC is allowed in Web API but not REST.

❌ RPC-style:

```http
POST /api/user/login
POST /api/user/logout
POST /api/user/validate
```
✔️ REST-style:

```http
POST /auth/login
DELETE /auth/session
```

## 7. Not using HATEOAS (strict REST requirement)   
Strict REST includes links in responses.

✔️ REST example:

```json
{
  "id": 10,
  "name": "Laptop",
  "links": [
    { "rel": "self", "href": "/products/10" },
    { "rel": "delete", "href": "/products/10" }
  ]
}
```
Most Web APIs skip this → technically not fully REST.
