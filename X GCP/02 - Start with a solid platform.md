### The Google Cloud console
- Web GUI
- Find resources, check health, management control, set budgets
- Search facility to find resources and connect to instances via SSH in the browser
### Understanding projects
![](Pasted%20image%2020250609105830.png)
##### Resources
- VM, cloud storage buckets, tables in big query, etc
- Resources are organized into projects
- Each resource belongs to one project
##### Projects
- Can have different owners and users
- Billed and managed separately
- Each project has 3 identifying attributes:
	- **Project ID:**
		- Global
		- Immutable
		- Assigned by Google Cloud
	- **Project Name**
		- Need not be unique
		- Chosen by you
		- Mutable
	- **Project Number**
		- Same as ID
		- Used by GC internally
- **Resource Manager tool:**
	- API
	- List, create, update, delete, recover projects
	- Access through RPC and REST API.
##### Folders
- Group projects in a hierarchy
- Delegate administrative rights
- Needs to have a Organization Node
### Google Cloud billing
- **Established at the project level**
- Billing account can be linked to zero or more projects
- Charged automatically and invoiced every month or at every threshold limit
- Billing sub accounts can be used to separate billing by project
##### Tools to help budget and monitor usage
- Budgets: fixed limit or tied to another metric
- Alert: before the limit is reached
- Reports: visual tool to monitor spending by project or service
- Quotas: prevents overconsumption from errors os malicious attacks
	- Rate quota: rests after a specific time
	- Allocation quota: governs the number of resources in a project (such as no more than 5 VPN)
### Install and configure the Google Cloud SDK
- Set of CLI tools to manage resources:
	- **gloud CLI**: main CLI interface
	- **gcloud storage**: access to Cloud Storage
	- **bq**: BigQuery
- Install via the website
	- `gcloud init` to configure the SDK (login, project, zone, etc)
### Cloud Shell
- CLI access to resources from a browser
- Debian-based VM with persistent 5GB home directory
- Google Cloud SDK are always installed and authenticated
##### Cloud Shell code editor
- Edit files inside the environment in real time 
- Access via the browser
### LAB - Gettin Started with Cloud Shell and gcloud
### Google Cloud APIs
### The Cloud Console Mobile App