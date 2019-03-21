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

## Key Terminology

## References
