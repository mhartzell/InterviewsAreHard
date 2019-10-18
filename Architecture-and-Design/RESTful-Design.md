[<< Back to Architecture and Design](index.md)

# RESTful Design
REST consists of a coordinated set of components, connectors, and data elements within a distributed hypermedia system, where the focus is on component roles and a specific set of interactions between data elements rather than implementation details. Its purpose is to induce performance, scalability, simplicity, modifiability, visibility, portability, and reliability. REST is the software architectural style of the World Wide Web.  To the extent that systems conform to the constraints of REST they can be called RESTful. RESTful systems typically, but not always, communicate over Hypertext Transfer Protocol (HTTP) with the same HTTP verbs (GET, POST, PUT, DELETE, etc).

The term representational state transfer was introduced and defined in 2000 by Roy Fielding in his doctoral dissertation at UC Irvine.  Fielding used REST to design HTTP 1.1 and Uniform Resource Identifiers (URI).
# Main Tenets
The main tenets of REST are defined as architectural constraints.  A system can be considered more or less RESTful to the degree that the system conforms to the architectural constraints mandated by RESTful design.

## Uniform Interface
All services and service consumers within a REST-compliant architecture must share a single, overarching technical interface. As the primary constraint that distinguishes REST from other architecture types, uniform interface is generally applied using the methods and media types provided by HTTP.

The technical contract established by this constraint is typically free of business context because, in order to be reusable by a wide range of services and service consumers, it needs to provide generic, high-level capabilities that are abstract enough to accommodate a broad range of service interaction requirements.
## Stateless Interactions
The communication between service consumer (client) and service (server) must be stateless between requests. This means that each request from a service consumer should contain all the necessary information for the service to understand the meaning of the request via  the URL, query parameters, body or headers.  All session state data should then be returned to the service consumer at the end of each request.

## Cacheable
Response messages from the service to its consumers are explicitly labeled as cacheable or non-cacheable. This way, the service, the consumer, or one of the intermediary middleware components can cache the response for reuse in later requests.

## Client-Server
Client-Server enforces the separation of concerns in the form of a client-server architecture. This helps establish a fundamental distributed architecture, thereby supporting the independent evolution of the client-side logic and server-side logic.

A service offers one or more capabilities and listen for requests for those capabilities. 
A consumer invokes a capability by sending the corresponding request message, and the service either rejects the request or performs the requested task before sending a response message back to the consumer

## Layered System
A REST-based solution can be comprised of multiple architectural layers, and no one layer can "see past" the next. Layers can be added, removed, modified, or reordered in response to how the solution needs to evolve.

The Layered System constraint builds on Client-Server to add middleware components (which can exist as services or service agents) to an architecture. 
Layered System requires that this middleware be inserted transparently so that interaction between a given service and consumer is consistent, regardless of whether the consumer is communicating with a service residing in a middleware layer or a service that represents the ultimate receiver of a message.

## Code on Demand
This optional constraint is primarily intended to allow logic within clients (such as Web browsers) to be updated independently from server-side logic. Code-On-Demand typically relies on the use of Web-based technologies, such as Web browser plug-ins, applets, or client-side scripting languages (i.e. JavaScript).

# References
- [Representational state transfer](https://en.wikipedia.org/wiki/Representational_state_transfer)
- [Representational State Transfer (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
- [REST Constraints](http://whatisrest.com/rest_constraints/index)
