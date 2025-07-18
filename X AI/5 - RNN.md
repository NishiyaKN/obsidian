# Recurrent Neural Networks
- **Feedback loop**
	- Allows information to persists across different timesteps
- **Hidden state** (short-term memory)
- **Vanishing gradient problem** (old information is forgotten)
- Data used must be **sequential**
- Goal is to find **patterns** and make **predictions**
- Types of RNN architecture:
	- **One-to-one**: 
		- similar to feedforward neural network
		- not suited for sequential data
	- **One-to-many**:
		- multiple output values for one input value
		- used for music or sequrence generation
	- **Many-to-one**:
		- one output value from multiple input values
		- used for ex for sentiment analysis
	- **Many-to-many**: 
		- multiple output values from multiple input values
		- used for ex in machine translation
## RNN Architectures
### LSTM (Long-Short-Term Memory)
- **Remember information over long periods**
- Capture long-term dependencies in the sequential data
	- Uses specialized **memory cell** and **gate** mechanisms
- Selectively remembers or forgets information over time
#### Memory Cell (Cell State)
- Long-term memory of the LSTM
- Acts as a memory conveyor belt
- Gates control which information should be added discarded 
#### Gates
- **Forget Gate:** decides what info from the previous memory cell state should be discarded
- **Input Gate:** decides what new info from the current input should be added to the memory cell
- **Output Gate:** decides what info from the updated memory cell should be outputted as the hidden state
