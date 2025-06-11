### Compute Options in the Cloud
- IaaS: **Compute Engine** - VM
- PaaS: **App Engine** - Zero ops platform for apps
- Serverless logic: **Cloud Run functions** - trigger code based on some event
- Hybrid: **Google Kubernetes Engine** - container cluster orchestration
- Serverlesss platform: **Cloud Run** - develop and deploy containerized apps
### Exploring IaaS with Compute Engine
- No upfront investment
- VMs created via Google Cloud console or gcloud 
- Linux and Windows images
- Build and run other OS images
###### Billing
- By second
- Minimum of 1 minute
- Sustained-use discount (the longer they run): +25% of a month, apply discont for every additional minute
- Committed-use: up to 57% discount for 1 or 3 years
- Preemptible VMs: can be terminated any moment.  
### Configuring Elastic Apps with Autoscaling
- VMs can be added or removed from applications according to load metrics
- Balances incoming traffic among VMs
### Exploring PaaS with App Engine
- Serverless platform
- Focus on writing code without need to worry about infrastructure
- Choose languages, libraries and frameworks
- Automatically provisions servers and scales instances by demand
- Built-in services and APIs: health check, app logging, auth, etc
- SDK manages app locally, in a sandbox container environment 
###### Standard environment
Runs specified version of Java,Python, PHP, GO, Node.js, Ruby
- Preconfigured runtimes and libraries
- Persistent storage
- Auto scaling and balancing
- Async task queues for performing work outside the scope of a request
- Scheduled tasks for triggering events
###### Flexible environment
Supports Docker containers, microservices, auth, DB, traffic splitting, logging, CDN, etc
- Configure container by yourself
- Instances are health-checked, healed and co-located
- Auto updates the OS when needed
- VM instances auto located by geo region according to the projects
- VM instances restarted on a weekly basis
![](Pasted%20image%2020250610201539.png)
### Event-Driven Programs with Cloud Run Functions
For example: 
1. User uploads a image
2. Image gets converted
3. Thumbnails are generated
4. Files are stored
Step 1 triggers the code for the other 3
- Lightweight, async
- Used to create small single-purpose functions that repond to cloud events
- Billet to the nearest 100 milliseconds, only when code is running
- Supports JS, Python or Go inside a Node.js environment
### Containerizing and Orchestrating Apps with GKE
- Hybrid:
	- Manageable infraestructure like Compute Engine
	- Developer orientation like the App Engine
- 
### Managed serverless computing with Cloud Run