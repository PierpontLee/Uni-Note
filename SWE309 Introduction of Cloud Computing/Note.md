# Lecture 1
## 1.1 What is Cloud Computing
A model for obtaining shared computing resources (processing, storage, network, and application) over a network when needed.
[model for enabling ubiquitous (everywhere), convenient, on- demand network access to a shared pool of configurable computing resources (e.g., networks, servers, storage, applications, and services)]
5 essential characteristics:
- On demand service
- Broad network access
- Resource Pooling
- Rapid elasticity
- Measured Service

3 Service Models:
![[Pasted image 20261012132325.png]]
- Software as a Service (SaaS)
- Platform as a Service (PaaS)
- Infrastructure as a Service (IaaS)

## IT Resources
- Physical Server
- Virtual Server
-  Software Program
- Service 
- Storage device
- Network Device

## Benefits
1. Share the scale > potentially lower cost per unit
2. Pay for usage > Lower upfront, pay by usage
3. Global workforce: shared cloud application and data between office and remote team
4. Simpler process: Use shared tools and data to reduce repeated work
5. Reduce capital cost: Reduce initial hardware and software purchases
6. Open workspace: access remotely using supported device e.g phone
7. Monitor project more effectively
8. Focus on the work: learn the app not the server maintenance
9. Minimize maintenance and licensing software

## Risk and Drawback

| Risk          | What can go wrong?  | Ask before adopting           |
| ------------- | ------------------- | ----------------------------- |
| Connection    | Connection outage   | Can the work continue offline |
| Bandwith      | Slow transfer speed | Is connection fast?           |
| Response time | High ping           | Is ping low enough?           |
| Feature fit   | Missing feature     | Does it support your task?    |
| Data security | unauthorized access | Who get access to this data?  |
| Data loss     | Files lost          | Can we restore using backup?  |

## Computing Concept
- High-Performance Computing (HPC): Uses substantial computing capacity and parallel execution for demanding workload such as scientific scientific simulation, weather modeling, engineering analysis.
- Serial vs. Parallel Computing: **Serial** task execute in sequence on **single processor**, where **parallel** task execute suitable sub-task **con-currently across multiple processor**
- Distributed Computing: Multiple networked computers coordinate to provide a service or solve a task.
- Cluster Computing: A form of distributed computing featuring closely connected homogeneous nodes located close to each other and communicating via fast interconnects (e.g., Message Passing Interface - MPI)
- Grid Computing: A distributed computing model that connects heterogeneous compute and storage resources across wide geographical distances, where each site remains autonomous.
![[Pasted image 20261012151714.png]]

## Cloud Provider Examples:
- Amazon Web Services (AWS): Provides on-demand cloud computing platforms to individuals, companies and governments, on a subscription basis.
- Microsoft Azure: For building, testing, deploying, and managing applications And services through Microsoft-managed data centers
- Google Cloud: For its end user product such as Google Search, Gmail, Drive, etc.

## Cloud Data Center
- Built around economies of scale, redundant power cooling subsystems, cabling, and strict physical security.
- Virtualization: Uses physical host combines with a hypervisor to allocate resources dynamically to multiple virtual machines (VMs) running guest operating systems and applications.