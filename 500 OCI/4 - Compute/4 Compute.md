## Compute Configurations
- **Instance Shape** specifies the number of CPUs, amount of RAM, and other resources 
	- Can be based on AMD, Intel, or Ampere (Arm) CPUs.
	- **Fixed Shape:** can't be customized, bare metal or VM
	- **Flexible Shape**: customizable, only VM
- **Image** determines the OS and software
- **Instance Configuration** is like a template
	- Has the shape, base image, metadata, VNICs, storage (not the contents), subnets
- **Instance Pool**: set of instances managed as a group
	- Can only have one Instance Configuration in the pool
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