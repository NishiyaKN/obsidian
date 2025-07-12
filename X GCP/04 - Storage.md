### Storage options in the cloud
- Cloud Storage
- Cloud SQL
- Spanner
- Firestore
- Bigtable
###### Use cases
- Content storage and delivery (such as images or videos)
- Data analytics and general compute (processing data)
- Backup and archival storage
### Structured and unstructured data storage
###### Unstructured data
- Non tabular form (80% of data is this)
	- Documents
	- Image
	- Audio
- Dificult to process such data since has no identifier
- Organizations are focusing on mining unstructured data for insights
###### Structured data
- Tables, rows, columns
- Organized, easy to analyze
- Understood by program languages
- There are two types:
	- **Transactional workload:** 
		- Online transaction processing systems
		- Fast data inserts and updates
		- Standardized queries that affect few records
		- Cloud SQL and Spanner for SQL
		- Firestore fro NoSQL
	- **Analytical workload**:
		- Online analytical processing systems
		- Used when entire datasets need to be read
		- Complex queries, such as aggregations
		- BigQuery for SQL
		- BigTable for NoSQL
### Unstructured storage using Cloud Storage
- Fully managed scalable service
- Used mostly for Binary large-object (BLOB) storage
- Unlimited storage with no min object size
- Geo-redundancy
- Files are organized into buckets
###### Object Storage
- Storage architecture that manages data as objects and not files / folder (file storage) or chunks of a disk (block storage)
- Objects are stored in a packaged format that contains:
	- binary form of the actual data
	- metadata 
	- globally unique indentifier (in the form of an URL)
- Data commonly stored as a objects:
	- videos
	- pictures
	- audio
###### CS Classes
- **Standard**
	- frequently accessed
	- stored for brief periods of time
- **Nearline**
	- infrequent accessed
	- 1 time per month avg
- **Coldline**
	- more infrequent accessed
	- accessing data at most once every 90 days
- **Archive**
	- lowest cost option
	- accessing once a year
	- high cost for data access
	- 365-day minimun storage duration
###### Buckets
- Globally unique name
- Specific to geo location
- Immutable, can't change what is inside a bucket
- Change content by new versions of the bucket
- Possible to do file versioning
### SQL managed services
Relational Database Management Systems
- Cloud SQL
- Spanner
### Exploring Cloud SQL
- Offers services of:
	- MySQL
	- PostgreSQL
	- SQL Server
- No software installation nor maintenance
- Up to 96 cpu, 624GB RAM, 64 TB storage
- Automatic replication
- Managed backups (cost of 1 instance includes 7 backups)
- Includes a network firewall
### Spanner as a managed service
- Scales horizontally (add and removes servers)
- Uses SQL (with joins and secondary indexes)
- Used for advertising, finance and marketing (manage end-user metadata
- High number of IO operations 
- Automatic replication across regions
### Firestore, a NoSQL document store
- Scales horizontally
- Document structure
- Used for mobile, web and server development
- Indexed by default
- App can manage data even offline, when it becomes online it synchronizes the changes
- Automatic replication across regions
### Bigtable as a NoSQL option
- Big data analysis
- Used in IoT, user analytics and financial data analysis
- Used if working with more than 1 TB of semi-structured or structured data
- Used with high throughput or rapidly changing data
- Used for machine learning algorithms on the data