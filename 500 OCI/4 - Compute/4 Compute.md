## Compute Configurations
- **Instance Shape** specifies the number of CPUs, amount of RAM, and other resources 
	- Can be based on AMD, Intel, or Ampere (Arm) CPUs.
	- **Fixed Shape:** can't be customized, bare metal or VM
	- **Flexible Shape**: customizable, only VM
- **Instance Configuration** is like a template
	- Has the shape, base image and metadata
- **Image** determines the OS and software
## Instance Types
- **Virtual Machine**: shared, multi-tenant
- **Bare Metal**: direct and exclusive access to the entire physical server hardware (no hypervisor)
- **Dedicated Host**: run VMs without sharing the host with any other user (uses OCI's provided hypervisor)
	- Not billed for individual VM instances (only for the host)
	- Host shape determines capacity and types of instances
	- Some OCPU are reserved for VM management, 
	- Not supported features: autoscaling, capacity reservation, instance configurations/pools, reboot migration, burstable instance
### Capacity
- **Preemptible VM:** 
	- Low-cost short-lived VMs (can be terminated any time with a 2-minute warning)
	- Suited for batch jobs and fault-tolerant workloads
	- Shape cannot be changed after creation
	- 50% cheaper than normal VM instance
- **Reserved:**
	- Reserve compute capacity in advance
		- Use this reserve when creating instances
	- No size nor time commitment
		- Reservation can be deleted anytime
	- Unused reserved capacity is billed at 85%
	- Used reserved capacity is billed at 100%
	- Specific to the selected AD
	- Cannot be used with dedicated VM Hosts
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