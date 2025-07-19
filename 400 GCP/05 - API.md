###  Apigee API Management
- Focus on business problems
	- rate limiting
	- quotas
	- analytics
- Provides software service to other companies
- Don't have to be in Google Cloud
- Used to take apart legacy applications, service by service (micro service)
### Pub/Sub
- Async messaging service
- Gets data from million different events, such as in IoT
- Ensures at-least-once delivery
- No provisioning is required
- APIs are open and global by default
###### Pub/Sub architecture
1. Ingests data from devices all over the globe
2. Read, store or broadcast to any subscriber of the data topic
3. Subscribers ingest, transforms and outputs into analytics data warehouse like BigQuery
4. Visualize and monitor the results of a pipeline or feed to AI/ML
##### Topics
- Named resource to which messages are sent by pub
- Pub can send data to a topic with no sub
- Sub can wait for data from a topic no one sends data to