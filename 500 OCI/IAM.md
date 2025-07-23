# Identity and Access Management Service
- Fine-grained Access Control
## Principal
- Users
-  Resources
	- Instance principal - can make API calls to other OCI services
-  Groups
## AuthN - Authentication
- Username and password
- API signing keys - public-private key pair to authenticate API calls
- Authentication Tokens - Oracle generated token strings for third-party APIs 
### Identity Domain
- Container for users and groups and security configuration
## AuthZ - Authorization
- Permissions via IAM policies
	- Can be attached to a compartment or tenancy
- **Everything is denied by default**
- Example: `Allow <domain_name>/<group_name> to <verb> <resource-type> in <location> wehre <conditions>`
### Verbs
- **Inspect:** list resources
- **Read:** inspect + user-specified metadata
- **Use:** read + actions varies by resource type
- **Manage:** all permissions for the resource
### Resource Type
- all-resources
- specific resource
- database-family
- instance-family
- object-family
- virtual-network-family
- volume-family 
# Compartment
- When creating an account in OCI, you get a tenancy (user account environment) and a **Root Compartment**
- Inside the root compartment, you can create compartments for isolation and controlling access of the cloud resources
	- Resources from different compartments can communicate to each other
	- Resources can be moved between compartments
	- Every compartment is global, available in every region
	- Up to 6 levels of nesting of compartments
	- Can set budgets and quotas in each compartment
# OCID (Oracle Cloud ID)
- Unique Oracle-assigned identifier for each OCI resource 
