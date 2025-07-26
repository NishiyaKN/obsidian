## Compute Offerings
- A **Instance Shape** specifies the number of CPUs, amount of RAM, and other resources allocated to an instance.
	- Shapes can be based on AMD, Intel, or Ampere (Arm) CPUs.
- An **Instance Configuration** is like a template
	- It has the shape, base image and metadata
### Instance Types
- **Virtual Machine**: shared, multi-tenant
- **Bare Metal**: direct and exclusive access to the entire physical server hardware (no hypervisor)
- **Dedicated Host**: run VMs without sharing the host with any other user (uses OCI's provided hypervisor)
- **Preemptible VM:** 
	- Low-cost short-lived VMs (can be terminated any time with a 2-minute warning)
	- Suited for batch jobs and fault-tolerant workloads
	- 50% cheaper than normal VM instance
## Compute Networking
- To create a compute instance, a VCN is needed
- Instance gets an private IP by virtualizing it's physical NIC (VNIC)
- Uses a remote Boot Volume for OS and a remote Block Volume for additional data
## High Availability
### Live Migrate
- During scheduled infrastructure maintenance, VMs are migrated to another host
	- No need to reboot
	- No downtime
### Autoscaling	
- Scale horizontally by adding or removing instances of the same time
#### Autoscaling Steps
1. Create Instance Configuration if it does not already exists
2. Create an instance pool from the config (can manage the instances as one single unit)
3. Write autoscaling rules (initial size, minimum size, maximum size, if CPU goes beyond X% add Y instances, etc)