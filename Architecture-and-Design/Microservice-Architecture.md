[<< Back to Architecture and Design](index.md)

# Microservice Architecture
Microservice architecture is a variant of SOA that structures an application as a collection of loosely coupled services that implement business capabilities.  Services are fine-grained and lightweight, decomposed into small services that improves modularity and makes an application easier to understand, develop, test and resist architecture erosion.  It also encourages parallel development and encourages continuous delivery and deployment.

# Characteristics
There is currently no industry consensus yet on the characteristics of microservices, but they have some common properties:

- Expose an API
- Often communicate over a network using technology-agnostic protocols
- Independently versioned, deployable and scalable
- Have a bounded context
- Easy to replace
- Organized around capabilities
- Can be implemented with different technology stacks
- Release with automated processes
- Emphasis on real-time monitoring and health checks
- Encourages decentralized governance
- Favors an evolutionary approach to design and development

# Drawbacks
Microservice architecture has drawbacks just like any other approach:

- Network calls over a bounded context have performance overhead vs in-process calls
- Code should be aggressively designed for failure and graceful degradation
- Moving responsibilities between services is difficult
- Testing and deployment are potentially more complicated
- Too fine-grained services become nano-services, which are not as helpful

# Containerization
Containers are a method of operating system virtualization that allow you to run an application and its dependencies in resource-isolated processes.  Containers package an application’s code, configuration and dependencies into easy to use building blocks.  They benefits of using containers include:

- Environmental consistency: Containers enable portability by encapsulating all the necessary files and dependencies, which can then be deployed on any computing resource.  Applications in development can be deployed identically in production.
- Operational efficiency: Multiple containers can be run at the same time, with explicitly specified computing resources (CPU, memory, disk, etc). They have small footprints and can boot up quickly, allowing for rapid scale-up or scale-down.  They support blue / green deployment strategies.  They are completely isolated from one another.  Containers can also depend on and inherit from one another, abstracting issues like server configuration.
- Developer productivity: Cross-service dependencies and conflicts are removed.  Each application component can be broken down into different containers running different microservices.  Containers are isolated, so library versioning issues are eliminated, and each service can be upgraded independently.  
- Version control: Containers themselves can be versioned, such as with the Docker manifest file.  
- Consistency of deployment regardless of deployment environment

# References
- [Microservices (Martin Fowler)](https://www.martinfowler.com/articles/microservices.html)
