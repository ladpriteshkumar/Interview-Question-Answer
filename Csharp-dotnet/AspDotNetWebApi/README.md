## What is REST API ?
REST API (Representational State Transfer Application Programming Interface) is a type of web service that adheres to the principles of REST architecture. REST is a set of guidelines for designing networked applications and relies on HTTP for communication between clients and servers.

[Ref-1](https://medium.com/asp-dotnet/basic-10-principles-of-rest-api-development-using-net-54ea4eb2ccdb)

## What Makes an API RESTful?
RESTful APIs are characterized by:

- **Stateless Communication:**
  Communication between client and server should be stateless, meaning that each request from a client should contain all the information necessary for the server to understand and process the request.
  Each request from a client to a server must contain all the information the server needs to fulfill the request. The server does not store any state about the client between requests.
  
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
  
- **Cacheability:** Responses can be cached
- **Layered System:** Architecture can have multiple layers
- **Code on Demand:** Optional execution of client-side code
