[<< Back to Architecture and Design](index.md)

# Service-Oriented Architecture
A service oriented architectureis an architectural pattern wherein services are provided to the other components by application components, through a communication protocol over a network. The basic fundamental principles of service oriented architecture is independent of vendors, products and technologies.   SOA is an architectural approach to creating systems built from autonomous services (typically web services).

There are four characteristics of a service:

- It logically represents a business activity with a specified outcome.
- It is self-contained.
- It is a black box for its consumers.
- It may consist of other underlying services.

# Main Tenets

## Boundaries are Explicit
Services interact through explicit message-passing over well-defined boundaries. Crossing service boundaries may be costly, depending upon geographic, trust or execution factors. A boundary represents the border between a service’s public interface and its internal, private implementation. A service’s boundary is published via WSDL and may include assertions dictating the expectations of a given service.

- Services provide a contract to define the public interfaces it provides. All interaction with the service occurs through the public interface. The interface consists of public processes and public data representations. The public process is the entry point into the service while the public data representation represents the messages used by the process.
- Service invocations are subject to network latency, network failure, and distributed system failures, but a local implementation is not. A significant amount of error detection and correction logic must be written to anticipate the impacts of using remote object interfaces.
- Internal (private) implementation details should not be leaked outside of a service boundary. Leaking implementation details into the service boundary will most likely result in a tighter coupling between the service and the service’s consumers.
- Avoid RPC interfaces. Explicit message passing should be favored over an RPC-like model.
- Services should be easy to consume, despite the incurred cost of crossing a service boundary.
- Keep service surface area small. The more public interfaces that a service exposes the more difficult it becomes to consume and maintain it.

## Services Are Autonomous
Services are entities that are independently deployed, versioned, and managed. Developers should avoid making assumptions regarding the space between service boundaries since this space is much more likely to change than the boundaries themselves.

- Services are not subservient to other code
- A service reacts to a message, and the action of the service is independent of how this message was created or what the response will be.
- Services should be deployed and versioned independent of the system in which they are deployed and consumed.
- Contracts should be designed with the assumption that once published, they cannot be modified.
- Service designers should adopt a pessimistic view of how their services will be consumed – services will fail and their associated behaviors (service levels) are subject to change.   Service providers also cannot trust consumers to “do the right thing”.

## Services Share Schema and Contract, Not Class
Service interaction should be based solely upon a service’s policies, schema, and contract-based behaviors. A service's contract is generally defined using WSDL

- Only messages are passed to services, not code.
- Messages follow an agreed upon format.
- Ensure a service contract remains stable to minimize impact upon service consumers. The contract in this sense refers to the public data representation (data), message exchange pattern (WSDL) and configurable capabilities and service levels (policy).
- Contracts should be designed to be as explicit as possible to minimize misinterpretation. Additionally, contracts should be designed to accommodate future versioning of the service
- A service’s internal data should be hidden.
- A service must be able to convert native data types to technology-neutral representation.
- Version services when changes to the service’s contract are unavoidable. 

## Service Compatibility is Based Upon Policy
It is not possible to communicate some requirements for service interaction in WSDL alone. Policy expressions can be used to separate structural compatibility (what is communicated) from semantic compatibility (how or to whom a message is communicated).

- Service must express what it does and how it interacts through standard policy representation
- Every service must provide a policy (machine-readable)
- Service will not operate if policies are not satisfied
- Policies allows the behavior of a service to be separated from the constraints of accessing the service

# Key Terminology

| Term | Definition                          |
|------|-------------------------------------|
| BPEL | Business Process Execution Language |
| Business Process | A structured description of the activities or tasks that have to be done to fulfill a certain business need. |
| Callback | A message exchange pattern where a service consumer sends a request message but does not block and wait for a reply. Instead, it defines a callback function that is called later, when the response message sent by the service provider arrives.  |
| Consumer | The channels that are used to access business processes, services, and applications. |
| Contract | The complete description of a service interface between one consumer and one provider. It includes the technical interface (signature), the semantics, and nonfunctional aspects such as service-level agreements.  |
| CORBA | Common Object Request Broker Architecture |
| Domain | A definable (business) area or scope that plays a specific role and/or has a specific responsibility. |
| Enterprise Architecture | The practice of applying a comprehensive and rigorous method for describing a current and/or future structure and behavior for an organization's processes, information systems, personnel and organizational sub-units, so that they align with the organization's core goals and strategic direction. |
| Enterprise Service Bus | The infrastructure of a SOA landscape that enables the interoperability of services. Its core task is to provide connectivity, data transformations, and (intelligent) routing so that systems can communicate via services. |
| Event | A notification sent to a more or less well-known set of receivers (consumers). Usually, the receivers of an event have to subscribe for a certain type of event (sent by a certain system or component). |
| Fire and Forget | A one-way message. |
| Governance | The task of "making sure that people do what’s right", in terms of architectural decisions, processes, tools, and policies.  |
| HTTP | Hypertext Transfer Protocol. The fundamental protocol of the World Wide Web. |
| Idempotency | The ability of services to deal with messages that are delivered more than once so that redeliveries do not have unintended effects.  |
| Interoperability | The ability of different systems to communicate with each other. |
| Message | A chunk of data sent around as part of a service call. |
| OASIS | Organization for the Advancement of Structured Information Standards |
| Request | A message that is sent by a consumer as an initial message in most message exchange patterns. |
| Response | A message that is sent by a provider as an answer to a service request. |
| Service | A discoverable resource that executes a repeatable task, and is described by an externalized service specification. |
| Service Components | The building blocks of a service.  Can potentially be reused across multiple services. |
| SOAP | SOAP is the basic protocol of Web Services. As an XML-based format, it defines the format of the header and body of a Web Services message. |


# References
- [Four Tenets of Service Orientation, The](http://www.soainstitute.org/resources/articles/four-tenets-service-orientation)
- [Service-oriented architecture](https://en.wikipedia.org/wiki/Service-oriented_architecture)
- [Service Oriented Architecture (SOA)](https://msdn.microsoft.com/en-us/library/bb833022.aspx)
- [Service Orientation SOA Glossary](http://serviceorientation.com/soaglossary/index)
- [SOA in Practice: SOA Glossary](http://www.soa-in-practice.com/soa-glossary.html)
- [SOA terminology overview, Part 1](http://www.ibm.com/developerworks/library/ws-soa-term1/)
