# Large Language Models
- Specializes in processing and generating human language.
- Probabilistic model of text, tries to predict the next word based on past words.
- Based on transformer architecture (deep learning)
	- Allows for effienct processing of text and adaptable attention
## Base LLM
- LLMs by itself are trained to predict the next word rather than to performe a task the user wants
	- This base training gives the LLM a deep understanding of language, grammar, facts and reasoning patterns 
	- If given a input, it will complete the input text rather than doing what the prompt says
- To a LLM perform tasks, it needs instruction tuning
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
## Storing LLM's Knowledge
- After trained, it's knowledge is stored in the parameters
- **Knowledge** is encoded in numerical weights assigned to the connections within the neural network
	- These weights are adjusted during training
- Stored as a binary format (.bin or .h5)
	- Contains the entire model, including its architecture and learned weights
## Foundation Models
- Pre-trained on extensive datasets
- Broad applicability, very generalized
- Can be fine-tuned for downstream tasks (serve as a base for specilized models)
- Ex: BERT, GPT-3, T5