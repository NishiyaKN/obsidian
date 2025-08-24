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
 ![[Pasted image 20250824005956.png|700]]
 > Request A: interval of 5 minutes, no resulution value is defined
 > Request B: interval of 5 minutes, 1 minute resolution
### Statistics
- Aggregation function
- **Sum**: returns all values added together for the time interval
	- `BytesIngested[1d].sum()`
- **Mean**: returns the value of Sum divided by Count during the specified time period
	- `CpuUtilization[1h].mean()`
- **Count**: returns the number of observations received in the specified time period.
	- `ServiceConnectorHubErrors[6h].count()>1`
- **Max**: returns the highest value observed during the specified time period
	- `CpuUtilization[1m].max()`
- **Percentile**: returns the value of the given percentile during the specified time period
	- `CpuUtilization[1m].percentile(0.90)`
### Alarms
- Alarm query must specify a metric, statistic, interval and trigger rule
- Alarm states:
	- **OK** - no issue
	- **Firing** - sends notification, triggers automation task
	- **Reset** - not detecting the metric firing 
	- **Repeat** - when in a firing state, repeatedly sends notification
- Supression: avoid publishing alarm messages (pause)
- 