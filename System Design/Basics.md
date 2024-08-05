# What is System Design:
Systems Design is the process of defining the architecture, components, modules, interfaces, and data for a system to satisfy specified requirements. It involves translating user requirements into a detailed blueprint that guides the implementation phase.
## Scaling an application:
- Vertical Scaling: Optimizing processes and increasing throughput with the same resources.
- Preprocessing: Preprocessing before hand at non peak time.
- Backups: Keep backups and avoid single point failure. 
- Horizontal scaling: Hire more resources.
- Micro Services architecture: where the application is developed as a collection of services, every work is well defined.
- Distributed System: Partitioning.
- Load Balancer: a device that sits between the user and the server group and acts as an invisible facilitator, ensuring that all resource servers are used equally.
- Decoupling: separating the things.
- Logging and metrics calculations.
- Extensible.

### Heigh level design:
Explains the architecture that would be used to develop a system

### Low level design:
Actual coding, like making classes, objects, functions, signatures.

# Vertical Scaling and Horizontal scaling:
When our code is liked by users and want response for there request they interact with our code via API's, our code to be used by everyone in the world we need to use cloud servers like AWS etc.

Now if requesting are coming more, its time for scaling.

There are 2 types of scaling as the title suggest.

- Buying Bigger machine is Horizontal scaling.
- Buying more machines is Vertical scaling.

## Difference:
Horizontal scaling   |  Vertical scaling
---------------------|----------------------
Need a Load Balancer | Not needed
Resilience | Single point failure
Network calls (Remote procedural calls)| Inter process communication(ipc)
Data Inconsistency | Consistence
Scales well as users increase | Hardware limit

Finally we are going to used both the advantages to our application, that is we take goods form each.
- Resilience, Scales well as users increase from horizontal.
- Inter process communication(ipc), Consistence from vertical scaling.

That is we start with a vertical scaling and make it into horizontal based on demand.