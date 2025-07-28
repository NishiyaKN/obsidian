## Tenancy
- User account environment
- Tenancy Admin: who creates the account
- Best practices:
	- Don't use Tenancy Admin for day-to-day operations
		 - Have OCI Admin (a user or group of admins) with proper policies to do that
	- Create dedicated compartments to isolate resources
## Compartments
- When creating an account in OCI you get a **Root Compartment**
- Inside the root compartment, you can create compartments for isolation and controlling access of the cloud resources
	- Resources from different compartments can communicate to each other
	- Resources can be moved between compartments
	- Every compartment is global
		- Ex: can hold 2 instances on different regions
	- Up to 6 levels of nesting of compartments