## Ways to access
- OCI Console - browser based interface
- Rest API
- Language SDKs
- CLI
# AI Services
### Language
- Text analysis
	- Detects the language
	- Identifies entities (names, places, dates, etc)
	- Identifies sentiment fo each aspect of text
	- Identifies key phrases
	- Classifies the general topic
- Process unstructured text (no data science expertise required)
#### Pretrained
- Language Detection
- Sentiment Analysis
- Key Phrase Extraction
#### Custom Models
- (used for domain specific datasets)
- Named entity recognition
- Text classification
#### Text Translation
- Neural Machine translation
### Vision
#### Image Analysis
- Object detection
- Image classification
- Optical character recognition
#### Document AI
- Works with JpPEG, PNG, Tiff or photos containing text 
- OCR
- Document Classification
	- Based on visual appearance and keywords
- Language Detection
- Table Extraction
- Key Value Extraction
### Speech
- Convert media files to readable texts stored in JSON or SRT
- Transcriptions are timestamped
- Batching support (multiples files with one call)
- Processes 10 hours in <10 minute
- Confidence score per word and transcription
- Punctuates transcription
- Profanity filtering by removing, masking or tagging
### Document Understanding
- Detect and classify text, key-value pair and table in documents
- Individual or batches
### Digital Assitant
- Create and deploy digital assistants
# ML Services
## OCI Data Science
- Cloud service that builds, trains and deploys ML models
- Serves the data scientist throughout the full ML life cycle
- Uses Jupyter Lab notebook
- Can select CPU, GPU, storage without need of manual provisioning
### Core Principles of OCI Data Science
- Accelerated: automated workflows, streamlined approach to building models
- Collaborative: share and reproduce models
- Enterprise-Grade: fully managed platform
#### Model Catalog
- Serves as a repository for storing, tracking and managing machine learning models
# Others
- RDMA: data transfer or network communication taht bypasses CPU
	- Extremely low latency, high bandwidth, low overhead for CPU
# Skill Check Questions
- What is the advantage of using OCI Superclusters for AI workloads?
	- Deliver exceptional performance and scalability for complex AI tasks.
- Which data type is used Oracle Database 23ai to compare documents?
	- Vector
- Which OCI Data Science Feature allows you to use catalogued models as HTTP endpoints on fully managed infrastructure?
	- Model Deployments
- Which OCI Data Science feature enables you to define and run repeatable machine learning tasks on fully managed infrastructure?
	- Jobs