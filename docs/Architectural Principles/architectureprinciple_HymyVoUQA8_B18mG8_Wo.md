

# Internet protocol (IP) address considerations

### Subject Area


Resiliency



### Topic


Internet protocol (IP) address considerations



### Ranked Priority


1



### Description


Network architecture must consider application availability, security and recovery needs.  production IP schema must consider the implications from a DR testing, partial and full failover perspective.  



### Rationale


IP addressing must support required levels of indirection for security, availability through load balancing and DR Test and Recovery. Since routing will fail if the same IP address exists in two places within one network; network design must account for that possibility when recovering workloads.



### Implications


DR Test requirements and production workload recovery to alternate hosts are frequently at odds with initial IP schema and network design for the live operational environment. Resolve these potential conflicts during initial design to avoid the pain of rework to meet recovery goals, or business interruption during DR Testing.



### Metrics




