# Identity and Access Management Service
- Fine-grained Access Control
## Principal
- Users
- Instance principal - resources that can make API calls to other OCI services
- Groups
## Identity Domain
- Container for managing users, groups and policies
- Each tenancy has at least one Identity Domain
### AuthN - Authentication
- Username and password
- API signing keys - public-private key pair to authenticate API calls
- Authentication Tokens - Oracle generated token strings for third-party APIs 
- Federation - uses an external Identity Provider (IdP)
### AuthZ - Authorization
- Permissions via IAM policies
	- Can be attached to a compartment or tenancy
- **Everything is denied by default**
- Example: `Allow <domain_name>/<group_name> to <verb> <resource-type> in <location> where <conditions>`
#### Verbs
- **Inspect:** list resources
- **Read:** inspect + user-specified metadata and the actual resource
- **Use:** read + work with existing resources
- **Manage:** all permissions for the resource
#### Resource Type
- all-resources
- specific resource
- database-family
- instance-family
- object-family
- virtual-network-family
- volume-family 
# Compartment
- When creating an account in OCI you get a **Root Compartment**
- Inside the root compartment, you can create compartments for isolation and controlling access of the cloud resources
	- Resources from different compartments can communicate to each other
	- Resources can be moved between compartments
	- Every compartment is global, available in every region
	- Up to 6 levels of nesting of compartments
# Tenancy
- User account environment
- Tenancy Admin: who creates the account
- Best practices:
	- Don't use Tenancy Admin for day-to-day operations
		 - Have OCI Admin (a user or group of admins) with proper policies to do that
	- Create dedicated compartments to isolate resources
# OCID (Oracle Cloud ID)
- Unique Oracle-assigned identifier for each OCI resource 
