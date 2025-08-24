- **Active Monitoring:** probing resources to assess health and resources
- **Passive Monitoring**: observing a data point as it happnes naturally
- **Single Pane of glass**: dashboards to visualize metric data
- **MQL:** Monitoring Query Language, used to filter data
- **OCI Connector Hub:** used to transfer metrics from the Monitoring to other services
## Concepts
### Metrics
- Measurement related to the health capacity or performance of a resource
- Grouped within different metric namespaces (for different resources)
- **Service Metrics**: native to the OCI compute agent
- **Custom Metrics**: user's own custom metrics, published using post-metric data API 
- **Dimension:** filters to the metric data
- **Metric stream:** individual set of aggregated data
	- Ex: 10 instances, 10 metric streams
- **Grouping function:** combine multiple metric streams into a single stream
- **Interval:** time window used to aggregate a set of data points
- **Resolution:** period between the time windows, only used through APIs
 ![[Pasted image 20250824005956.png]]
