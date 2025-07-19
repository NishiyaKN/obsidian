# Prompt Engineering
## In-context learning (AKA Prompt Engineering)
- Conditioning a model with instructions and or demonstrations of the task it is meant to complete
- Not exactly learning since the parameters don't change
### K-shot prompting
#### Zero-Shot Prompting
- Provide a task without giving any examples of hwo the task should be performed.
- Must be well-crafted and clear
- LLM relay only in it's knowledge from training
#### Few-Shot Prompting
- Gives a few examples of the task along with the prompt
- Basically a guide to the model
### Chain of Thought Prompting
- Guides the model through a step-by-step reasoning
	- You show the intermediate reasoning steps to reach an desired outcome
	- Model will follow this reasoning in it's output, improving its performance in complex tasks
	
# RAG (Retrieval-Augmented Generation)
- LLM can query enterprise knowledge bases (databases, wikis, vector databases, etc) 
- Does not require fine-tuning
- Retrieval: search over a corpus of information
- Augmented Generation: use retrieved information to forma a more informed response
- Used when data changes rapidly or to mitigate hallucinations
# Fine-tuning
- Takes a pre-trained model and provides additional training with custom data
- Used to teach something new or to specialize in a domain
- Improve efficiency by reducing the number of tokens (since it creates a smaller model)
# RLHF (Reinforcement Learning from Human Feedback)
- Model training procedure that is applied to a fine-tuned language model to further align model behavior with human preferences and instruction following
	- Uses human feedback to train a reward model
- 