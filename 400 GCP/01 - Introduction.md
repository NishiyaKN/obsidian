### Cloud Computing
Has these 5 characteristics:
- Computing resource on-demand and self-service
- Access from anywhere in the Internet
- Allocation of resources to users in pool
- Resources are elastic, increase or decrease as needed
- Pay only what you use
###  Cloud vs. traditional architecture
- **Colocation (First Wave)**: rent physical space to put your datacenter
- **Virtualized data center** (Second Wave):  enterprise maintains the infraestructure, user controls and configures
- **Container-based architecture** (Third Wave): automated services and scalable data
### IaaS, PaaS, SaaS
**IaaS - Infraestrucure as a Service:** 
- Raw compute, storage and network
- Pay for what allocate
**PaaS - Platform as a Service:** 
- Offers libraries for applications
- Pay for what use
**SaaS - Software as a Service:**
- Applications consumed directly over the internet
- Docs, Drive, Gmail
**Managed resources and services:**
- Deliver products and services more quickly and reliably
**Serverless:** 
- Allows developer to concentrate on code
- No infraestructure management needed
### Google Cloud architecture
![](Pasted%20image%2020250609103715.png)
###### Computing services
- Compute Engine
- Google Kubernetes Engine
- App Engine
- Cloud Run
- Cloud Run functions
###### Storage services
- Cloud Storage
- Cloud SQL (SQL)
- Spanner (SQL)
- Bigtable (NoSQL)
- Firestore (NoSQL)
###### Big Data and ML
- Cloud Storage
- Dataproc
- Bigtable
- BigQuery
- Dataflow
- Firestore
- Pub/Sub
- Looker
- Spanner
- AutoML
- Vertex AI
###### Google Network Infaestructure
**Regions**: independent geographical area, composed by zones, services can run in multiple regions (40+)
**Zone**: area where google cloud resources are deployed, can have redudancy with other zones or not (121+)