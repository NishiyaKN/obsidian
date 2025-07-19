- Specializes in processing and generating human language.
- Probabilistic model of text, tries to predict the next word based on past words.
- Consists of a vast number of parameters
- Parameters are aspects of the model learned from training data
- Trained on a lot of data
- Based on transformer architecture (deep learning)
	- Allows for effienct processing of text and adaptable attention
## Base LLM
- LLMs by itself are trained to predict the next word rather than to performe a task the user wants
	- This base training gives the LLM a deep understanding of language, grammar, facts and reasoning patterns 
	- If given a input, it will complete the input text rather than doing what the prompt says
- To a LLM perform tasks, it needs instruction tuning, 
	- Involves fine-tuning a LLM on a varied set of instructions, each paired with a desired output
## Model Creation Process
1. **Data collection**: books, websites, articles, etc
2. **Pre-processing**: cleaning data to train
3. **Model Design**: choose the architecture (usually transformer architecture)
4. **Training**: learns from the dataset, tries to predict the next word
5. **Additional Training**: using specific datasets for particular tasks
6. **Deploy:** set as a server, waiting for a prompt to process
##  Evolution of LLM
### Rules-based
- Manually programmed
- Limited and inflexible
### Statistical Models
- Relies on probability 
- Faster and more capable
### Transformer-based
- Uses **self** **attention** mechanism
	- Each token dynamically receives a value that represents how much attention the token may need over others
	- Allows weighting the importance of different parts of a sentence
- Deep understanding of **context** and **relationships** within a text
- Handles long sequence of complex data
## Embeddings
- During **Tokenization**, words are converted into tokens and then embeddings
- Embeddings are formats that the neural network understands 
	- **Numerical** representation of words/tokens
	- Either **vectors** or real **numbers** (no meaning to humans)
	- Usually a vector for each token, and also a vector for the entire sentence
	- Simplified (inaccurate) example: `Alice -> [-0.342, 1.547, 0.234, -1.876, 0.765]`
		- Each of this numeric values represents attributes associated to the word, such as
			- 0.342 = name
			- 1.547 = possible main character
			- 0.234 = human
			- -1.876 = female
			- 0.765 = curious
#### Embeddings Use Case (OCI)
1. User's question is encoded as a vector and sent to a Vector Database
2. Vector DB finds private contente that closely match the user's questin
3. The content is sent to the LLm to help answer the user's question
4. LLM uses the content plus general knowledge to provide an informed answer
## Encoders and Decoders
Uses layers of self-attention mechanisms in order to understand the input and generate an output
### Encoders
- Process and understands the input tokens
- Converts tokens into context-rich embeddings (whole sentence)
- Used for semantic search
### Decoders
- Converts tokens into embeddings (can use embeddings from encoders for sequence-to-sequence task, like translation) 
- Generates text based on the embeddings and previously generated output
	- Produces only a single token at a time
- Used for text generation
##### Decoding Strategies
- **Greedy Decoding:** picks the most likely word at each step, may lead to suboptimal sequences
- **Beam Search:** tries different possible sequences, explores a tree of possibilities and chooses the best
- **Top-k Sampling :** randomly picks the next word from the top-k most likely candidates, more creative and diverse, less deterministic
- **Top-p Sampling :** same as above, but instead of just the top most likely, picks any of the candidates that pass a threshold of probability
## Temperature
- A **hyperparameter** that can affect decoding
- Control the randomness of token prediction
- Higher temperature = more randomness
- Lower temperature = more confident predictions
## Storing LLM's Knowledge
- After trained, it's knowledge is stored in the parameters (connections between the nodes of the neural network)
- **Knowledge** is encoded in numerical weights assigned to the connections within the neural network
	- These weights are adjusted during training
- Stored as a binary format (.bin or .h5)
	- Contains the entire model, including its architecture and learned weights
## Foundation Models
- Pre-trained on extensive datasets
- Broad applicability, very generalized
- Can be fine-tuned for downstream tasks (serve as a base for specilized models)
- Ex: BERT, GPT-3, T5