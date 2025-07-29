## VCN - Virtual Cloud Network
- Private network used for communication between resources
- Specific to each OCI region
- Allowable VCN size range is /16 to /30
- Up to 5 IPv4 and 5 IPv6 CIDR blocks
	- Oracle-allocated IPv6 prefix is /56
	- BYOIPv6 prefix is allowed
### Gateways
#### Internet Gateway
- Handles communication between the public subnet and the internet
#### NAT Gateway
- Handles one-way communication from the private subnet to the internet
	- Enables outbound to the internet
	- Disables inbout from the internet
#### Service Gateway
- Used for secured access to OCI public services
	- Don't need to go throught the internet
#### Dynamic Routing Gateway
- Routes traffic from the private subnet to on-premises environment
- Routes traffic between different VCNs
	- Don't need to go throught the internet
###  Routing
#### Route Tables 
- Used to direct network traffic from the VCN to the internet, on-premises network or peered VCN
- Consists of route rules
	- Specifies Destination CIDR block and Route Target
### Peering
- Cannot have overlapping CIDRs
- **Local Peering**: communication between 2 VCNs in the same region
	- Uses Local Peering Gateway (not created by default when creating a VCN)
- **Remote Peering**: communication between 2 VCNs in different regions
	- Uses Dynamic Routing Gateway on each each VCN
- **VCN Transit Routing:** communication between up to 300 VCNs
	- By linking all of them to a Dynamic Routing Gateway V2
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
- Works with TCP, UDP & ICMP
- Ultra-low latency, faster than Layer 7 LB
# CIDR Blocks
- Denotes the range of IP addresses
- Example: 10.0.0.0 to 10.0.255.255 = 10.0.0.0/16
	- /16 since the first 16 bits (10.0) does not change
	- To get the total IPs in this network, do 2^32-16
		- -16 since it is /16, so in total 2^16 = 65536
- The **network address** is derived from an IP address && subnet mask
>`192.168.1.2 = 11000000 10101000 00000001 00000010
> `/24 mask    = 11111111 11111111 11111111 00000000`
> `192.168.1.0 = 11000000 10101000 00000001 00000000`
### Reserved IPs
- 1st = Network Address
- 2nd = Subnet Default Gateway Address
- Last = Broadcast Address