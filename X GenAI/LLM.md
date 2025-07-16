- Specializes in processing and generating human language.
- Consists of a vast number of parameters
- Parameters are aspects of the model learned from training data
- Trained on a lot of data
- Based on transformer architecture
	- Allows for effienct processing of text and adaptable attention
### Model Creation Process
1. **Data collection**: books, websites, articles, etc
2. **Pre-processing**: cleaning data to train
3. **Model Design**: choose the architecture (usually transformer architecture)
4. **Training**: learns from the dataset, tries to predict the next word
5. **Additional Training**: using specific datasets for particular tasks
6. **Deploy:** set as a server, waiting for a prompt to process
###  Evolution of LLM
##### Rules-based
- Manually programmed
- Limited and inflexible
##### Statistical Models
- Relies on probability 
- Faster and more capable
##### Transformer-based
- Uses **self** **attention** mechanism
	- Each token dynamically receives a value that represents how much attention the token may need over others
	- Allows weighting the importance of different parts of a sentence
- Deep understanding of **context** and **relationships** within a text
- Handles long sequence of complex data
### Embeddings
- During **Tokenization**, words are converted into embedding
- Embeddings are formats that the neural network understands 
	- **Numerical** representation of words/tokens
	- Either **vectors** or real **numbers** (no meaning to humans)
	- Simplified (inaccurate) example: `Alice -> [-0.342, 1.547, 0.234, -1.876, 0.765]`
		- Each of this numeric values represents attributes associated to the word, such as
			- 0.342 = name
			- 1.547 = possible main character
			- 0.234 = human
			- -1.876 = female
			- 0.765 = curious
# Encoders and Decoders
Uses layers of self-attention mechanisms in order to understand the input and generate an output
### Encoders
- Process and understands the input
- Converts words into embeddings
### Decoders
- Generates text based on the encoder's output (and the previous generated text)
-  Converts embeddings new text
- Some models may use only decoder, no encoder
##### Decoding Strategies
- **Greedy Decoding:** picks the most likely word at each step, may lead to suboptimal sequences
- **Beam Search:** tries different possible sequences, explores a tree of possibilities and chooses the best
- **Top-k Sampling :** randomly picks the next word from the top-k most likely candidates, more creative and diverse, less deterministic
- **Top-p Sampling :** same as above, but instead of just the top most likely, picks any of the candidates that pass a threshold of probability
### Temperature
- A **hyperparameter** that can affect decoding
- Control the randomness of token prediction
- Higher temperature = more randomness
- Lower temperature = more confident predictions
### Storing LLM's Knowledge
- After trained, it's knowledge is stored in the parameters (connections between the nodes of the neural network)
- **Knowledge** is encoded in numerical weights assigned to the connections within the neural network
	- These weights are adjusted during training
- Stored as a binary format (.bin or .h5)
	- Contains the entire model, including its architecture and learned weights
### Types of Prompts
##### Zero-Shot Prompting
- Provide a task without giving any examples of hwo the task should be performed.
- Must be well-crafted and clear
- LLM relay only in it's knowledge from training
##### Few-Shot Prompting
- Gives a few examples of the task along with the prompt
- Basically a guide to the model
##### Chain of Thought Prompting
- Guides the model through a step-by-step reasoning
- Encourages the model to show it's thought process
### Foundation Models
- Pre-trained on extensive datasets
- Can be fine-tuned for downstream tasks
- 