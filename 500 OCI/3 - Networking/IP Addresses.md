## Private IP Addresses
- Connects to other instances in the same VCN
- Connects to on-premises instances via Fastconnect or site-to-site VPN
- Each instance can have a Primary VNIC and a Secondary VNIC
	- Each VNIC has 1 primary private IP address
		- Each VNIC can have up to 32 secondary private IP addresses
			- So each instance can have 66 (33+33) private IP addresses in total
## Public IP Addresses
### Ephemeral
- Temporary 
- IP Address exists for the lifetime of the instance
- Can only be assigned to the VNIC's primary private IP
### Reserved
- Persistent
- Regional specific
- Can be assigned to a VNIC's primary or secondary private IP
- You can have up to 50 reserved IP addresses in a region
- When unassinging the IP, it returns to the tenancy's pool of reserved IPs
	- Exists untill you delete it
### BYOIP
- Bring Your Own IP
- Oracle performs a validation of whether you are the owner of the IPv4 or IPv6
	- IPv4 minimum of /24 and maximum of /8
	- IPv6 needs to be /48 or larger
Regional Internet Registry
#### BYOIP Process
1. You request to import the IP to OCI
2. Oracle issues a verification token 
3. You create ROA (Route Origin Authorization)
	1. Provides the Oracle BGP ASN for the commercal cloud to the RIR
4. You request that Oracle finish the import process 