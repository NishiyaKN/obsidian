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
## Autoscaling	
- Scale horizontally by adding or removing instances of the same time
	- Metric-based: when a performance metric exceeds a threshold
	- Schedule-based: specific times that you schedule 
### Autoscaling Steps
1. Create Instance Configuration if it does not already exists
2. Create an instance pool from the config (can manage the instances as one single unit)
3. Write autoscaling rules (initial size, minimum size, maximum size, if CPU goes beyond X% add Y instances, etc)
## Infrastructure Maintenance
- When OCI's infra needs to receive some maintenance
### Live Migration
- Migrates VM to a health host
- Small disruption
- Only supported by specifi Linux shapes
### Reboot Migration
- Notifies 14 to 16 days in advance to reboot in order to migrate
	- Needs to reboot the instance, not only the OS
- If not rebooted in such time period, on the scheduled maintenance time it will auto reboot
- Short downtime due to reboot
### Manual Migration
- Instance will be terminated and recreated
- Boot volume needs to be preserved manually
## Shielded Instances
- Protects VM from rootkits and bootkits
- Not all images and shapes support
- Uses a combinations of
	 - Secure Boot: ensures every component in the boot process has avalid signature
	- Measured Boot: tracks boot measures
	- TPM: security cyhip used by Measured Boot to store boot measurements
