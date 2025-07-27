# Identity and Access Management Service
## Principal
- Users
- Instance principal - resources that can make API calls to other OCI services
- Groups
## Identity Domain
- Container for managing users, groups and policies
	- For example: separate production team, development team
- Each tenancy has at least one Identity Domain
### AuthN - Authentication
- Username and password
- API signing keys - public-private key pair to authenticate API calls
- Authentication Tokens - Oracle generated token strings for third-party APIs 
- Federation - uses an external Identity Provider (IdP)
#### AuthN glossary
- **SSO (Single Sign-On)** - use a single set of credentials (user & passwd) to access multiple independent applications
- **SAML (Security Assertion Markup Language)** - protocol used to exchange auth data between Identity Provider and Service Provider (SSO for web apps)
- **OAuth** - allow a third-party app to have limited access to a service (like login with Google or Facebook)
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
