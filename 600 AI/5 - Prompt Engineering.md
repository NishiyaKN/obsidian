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

# RLHF (Reinforcement Learning from Human Feedback)
- Model training procedure that is applied to a fine-tuned language model to further align model behavior with human preferences and instruction following
	- Uses human feedback to train a reward model
- 