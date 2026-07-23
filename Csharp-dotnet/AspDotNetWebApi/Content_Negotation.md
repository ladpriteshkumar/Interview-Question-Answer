[Ref](https://www.c-sharpcorner.com/article/content-negotiation-in-net-core-web-api/)
# Content Negotation
Content Negotiation is a REST mechanism that allows a client and server to agree on the best format for the data being exchanged.

The client tells the server what format it prefers, and the server responds in the format requested by client.

Content Negotiation ensures that one resource can be represented in multiple formats, and the client and server automatically agree on the best one without changing the endpoint.

## Why Content Negotiation Exists
Different clients may need different representations of the same resource:   
- A browser may want HTML   
- A mobile app may want JSON   
- A legacy system may want XML   
- A data pipeline may want CSV   

Content negotiation ensures flexibility without changing the API endpoint.

## Types of Content Negotiation

### 1. Header-Based (Most Common)   
Uses Accept and Content-Type headers.
```
Accept: application/json
```

### 2. URL-Based (Not pure REST, but widely used)
```
/users/123.json
/users/123.xml
```

### 3. Query Parameter-Based
```
/users/123?format=json
```

## Benefits of Content Negotiation   
- Same endpoint, multiple formats   
- Better client compatibility   
- Cleaner API design   
- Easier versioning and evolution
