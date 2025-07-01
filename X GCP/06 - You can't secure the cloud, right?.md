### Security in the cloud
- **Hardware Infraestructure:** custom designed by Google
- **Premises Security:** owns most datacenters
- **Service Deployment:** services communicate with encrypted RPC (remote procedure call)
- **User Identity:** U2F compatible
- **Storage services:** encryption at rest, hardware encryption
- **Inter communication:** Google Front End (GFE) - all TLS connections follows best practices, DoS protection
### The shared security model
![](Pasted%20image%2020250701133336.png)
### Encryption options
##### Encryption by default
- At transit: TLS
- At rest: AES-256
###### CMEK - Customer managed encryption keys
- Cloud KMS automates encryption keys generation and management
- Managed by the customer
- Never leaves the cloud
###### CSEK - Customer-supplied encryption keys
- Greater control, but also management complexity
- Need to generate, store and provide the keys to Google Cloud API calls
- For Google, the key exists only in memory and is discarded after use 
### Authentication and authorization with IAM
- Policies that defines who can do what on which resources
- "who" can be a Google Account, Google Group, service account, Cloud Identity domain
- **Deny policy overrides any existing allow policy**
###### Types of roles
- **Basic**
	- Broad in scope
	- Owner, editor, viewer and billing administrator
- **Predefined roles**
	- Usually tied to a resource, such as "instanceAdmin" role for compute Engine
	- Predefined permissions
- **Custom role**
	- Use the least-privilege model
	- Define specific permissions 
	- Can be applied to project or organization level, not to folder level
###### Service account
- Uses an email and cryptographic keys (not passwd)
- Can be tied to specific roles
### IAP - Identity-Aware Proxy
- Used to set up auth to https-based apps without the use of a VPN
- Layer of protection between the outside world and an internal service
- Does not protect inside a VM or project
### IAM authorization best practices

