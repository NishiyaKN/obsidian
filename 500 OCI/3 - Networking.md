## VCN - Virtual Cloud Network
- Private network used for communication between resources
- Specific to each OCI region
### Gateways
#### Internet Gateway
- Handles communication between the public subnet and the internet
#### NAT Gateway
- Handles one-way communication from the private subnet to the internet
	- Enables outbound to the internet
	- Disables inbout from the internet
#### Service Gateway
- Used for secured access to OCI public services, available on the internet
#### Dynamic Routing Gateway
- Routes traffic from the private subnet to on-premises environment
	- Don't need to go throught the internet
###  Routing
#### Route Tables 
- Used to send traffic from the VCN to the internet, on-premises network or peered VCN
- Consists of route rules
	- Specifies Destination CIDR block and Route Target
### Peering
- Cannot have overlapping CIDRs
- **Local Peering**: communication between 2 VCNs in the same region
	- Uses Local Peering Gateway ( not created by default when creating a VCN)
	- Up to 300 VCNs can communicate with each other, by linking all of them to a Dynamic Routing Gateway V2
- **Remote Peering**: communication between 2 VCNs in different regions
	- Uses Dynamic Routing Gateways
## Load Balancer (Reverse Proxy)
- High availability and scalability
### Layer 7 LB
- Understand HTTP/S
- Flexible shape: defines minimum and maximum bandwidth
	- 10 mbps to 8gbps
- Dynamic shape: automatically scales bandwidth according to demand
- Content-Based Routing
	- Can inspect the package to route the package
### Layer 4 LB
- Network Load Balancer
- Works with TCP & UDP
- Faster than Layer 7 LB
