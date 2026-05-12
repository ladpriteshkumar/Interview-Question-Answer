## What is REST API ?
REST API (Representational State Transfer Application Programming Interface) is a type of web service that adheres to the principles of REST architecture. REST is a set of guidelines for designing networked applications and relies on HTTP for communication between clients and servers.

[Ref-1](https://medium.com/asp-dotnet/basic-10-principles-of-rest-api-development-using-net-54ea4eb2ccdb)

## What Makes an API RESTful?  or Rest Principle

# REST Principles

## 1. Client–Server Architecture
The client (frontend) and server (backend) are separated.  
- Client handles UI/UX  
- Server handles data and logic  
This separation improves scalability and portability.

## 2. Statelessness
Each request from the client must contain all necessary information.  
- Server does NOT store client session state  
- Every request is independent  
This makes systems more scalable and easier to distribute.

## 3. Cacheability
Responses must define whether they are cacheable or not.  
- Improves performance  
- Reduces server load  
- Enables CDN and browser caching  

## 4. Uniform Interface
A consistent way to interact with resources.  
Key constraints:  
- Resource identification (URI)  
- Resource manipulation via representations (JSON, XML)  
- Self-descriptive messages  
- HATEOAS (optional in practice)  

## 5. Layered System
A client cannot tell if it is connected directly to the server or an intermediary.  
- Enables load balancers  
- Enables proxies  
- Improves security and scalability  

## 6. Code-on-Demand (Optional)
Server can send executable code to the client.  
- Example: JavaScript sent to browsers  
This is the only optional REST constraint.

## 7. Resource-Based Architecture
Everything is treated as a **resource** identified by a URI.  
- `/users/123`  
- `/orders/456/items`  
Resources are manipulated using standard HTTP methods.

## 8. Use of Standard HTTP Methods
REST relies on HTTP verbs to define actions:  
- **GET** – Retrieve a resource  
- **POST** – Create a resource  
- **PUT** – Replace a resource  
- **PATCH** – Update part of a resource  
- **DELETE** – Remove a resource  

## 9. Use of Standard HTTP Status Codes
REST APIs must use meaningful status codes:  
- `200 OK`  
- `201 Created`  
- `400 Bad Request`  
- `401 Unauthorized`  
- `404 Not Found`  
- `500 Internal Server Error`  

## 10. Representation of Resources
Resources can be represented in multiple formats:  
- JSON (most common)  
- XML  
- HTML  
- YAML  
Clients choose via **Content Negotiation** (`Accept` header).



---
RESTful APIs are characterized by:

- **Stateless Communication:**
  Communication between client and server should be stateless, meaning that each request from a client should contain all the information necessary for the server to understand and process the request.
 
- **Use HTTP Methods Correctly:**   
  Use standard HTTP methods to perform CRUD operations:   
    GET: Retrieve data.   
    POST: Create new resources.   
    PUT: Update existing resources.   
    DELETE: Remove resources.

- **Resource Identification:**
   Resources should be identified using URIs (Uniform Resource Identifiers). Each resource should have a unique URI, and the URI should be used to access and manipulate the resource.

- **Uniform Interface:**
   The API should have a consistent and uniform interface that makes it easy for clients to understand and interact with. This includes using standard conventions for naming resources and endpoints.

- **Response Formats:**
  Use standard formats such as JSON or XML for responses. JSON is typically preferred due to its lightweight nature and ease of use.

- **Versioning:**
  Include versioning in the API to handle future changes and ensure backward compatibility. This can be done via URL path (e.g., /api/v1/resource) or headers.

- **Error Handling:**
  Provide meaningful error messages and use standard HTTP status codes to indicate the outcome of API requests. For example, return 404 for not found, 400 for bad request, and 500 for internal server errors.

- **Security:**
  Implement security measures such as authentication and authorization to protect the API. Common practices include using API keys, OAuth tokens, or JWT (JSON Web Tokens).

- **Cacheability:** Responses can be cached

- **Layered System:** Architecture can have multiple layers

