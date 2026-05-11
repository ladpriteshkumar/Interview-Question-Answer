## What is REST API ?
REST API (Representational State Transfer Application Programming Interface) is a type of web service that adheres to the principles of REST architecture. REST is a set of guidelines for designing networked applications and relies on HTTP for communication between clients and servers.

[Ref-1](https://medium.com/asp-dotnet/basic-10-principles-of-rest-api-development-using-net-54ea4eb2ccdb)

## What Makes an API RESTful?  or Rest Principle
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

