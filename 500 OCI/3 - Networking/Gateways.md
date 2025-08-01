## Internet Gateway
- Only one per VCN is allowed
## NAT Gateway
- Has a public IP on behalf of private instances 
	- **Ephemeral**: bound to the lifetime of the GW
	- **Reserved**
- Rejects connections initiated from the Internet
- Max of 20,000 concurrent connections
### Traffic Blocking
- Regardless of any route or security rule, you can set to block traffic flowing through the NATGW
## Service Gateway
- Connect to Oracle Services Network without going through the Internet
	- Only connects to resources in the same **region**
### Services CIDR Label
- String that represents all regional public IP address ranges
