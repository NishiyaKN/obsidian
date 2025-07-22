- Fully managed service thar provides LLMs via a single API to build gen AI apps
- Choice of pretrained models from Meta and Cohere
- Flexible Fine-tuning with your own dataset 
	- **Uses T-Few fine-tuning:** inserts new layers in the base model and selectively updates a fraction of the weights
		- Reduces time and cost for fine-tuning, since it does not update the entire model
- **Dedicated AI Clusters**: GPU based compute resource for fine-tuning and inference
## Pretrained Foundational Models
### Chat
Conversational responses
- **command-r-plus (Cohere)**
	- Powerful but expensive
	- Large amounts of requests
	- User prompt up to 128,00 tokens
 - **command-r-16k (Cohere)**
	- More economic
	- User prompt up to 16,000 tokens
- **llama 3-70b-instruct (Meta)**
### Embedding
Used for semantic search 
- **embed-english-v3.0**
- **embed-multiligual-v3.0** (100+ languages)
## OCI Playground
- Allows to visually explore and test pre-trined and fine-tuned models without writing code
## Model Endpoints
- Hosts and serves fine-tuned models for inference via API