## Compute Offerings
- Can to run on AMD, Intel or Ampere (Arm) CPU
### Instance Types
- **Virtual Machine**: shared, multi-tenant
- **Bare Metal**: direct and exclusive access to the entire physical server hardware (no hypervisor)
- **Dedicated Host**: run VMs without sharing the host with any other user (uses OCI's provided hypervisor)
- **Preemptible VM:** 
	- Low cost short lived VMs
	- Suited for batch jobs and fault-tolerant workloads
	- 50% cheaper than normal VM instance
## Compute Networking
- To create a compute instance, a VCN is needed
- Instance gets an private IP by virtualizing it's physical NIC (VNIC)
- Uses a remote boot disk for OS and data disk 
	- Both are backed by the OCI Block Volume service
## High Availability
### Live Migrate
- If any compute host goes down, the VM is migrated to another host
	- No need to reboot
	- No downtime
### Autoscaling	
- Scale vertically by increasing or decreasing compute & RAM from a single instance
- Scale horizontally by adding or removing instances of the same time
#### Autoscaling Steps
1. Create config (template of an instance)
2. Create an instance pool from the config (can manage the instances as one single unit)
3. Write autoscaling rules (initial size, minimum size, maximum size, if CPU goes beyond X% add Y instances, etc)