# Content Negotation
Content Negotiation is a REST mechanism that allows a client and server to agree on the best format for the data being exchanged.

The client tells the server what format it prefers, and the server responds in the format requested by client.

## Why Content Negotiation Exists
Different clients may need different representations of the same resource:   
- A browser may want HTML   
- A mobile app may want JSON   
- A legacy system may want XML   
- A data pipeline may want CSV   

Content negotiation ensures flexibility without changing the API endpoint.
