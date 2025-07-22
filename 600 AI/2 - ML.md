# Machine Learning
- Systems that can learn and predict outcomes from given examples (data)
## Methods of Machine Learning
### Supervised learning
- **Used to classify data or make predictions**
- Requires **labeled** data (with the correct answer)
- Train the AI to get the correct answer for each new data
- **Target variable**: specific variable in the dataset that it's being trained to predict (classify as dog, cat, bird; house price; spam or not spam)
#### Classification - Categorical Data
- **Predict a category or label**
	- **Binary classification**
		- Logistic regression
			- predicts if something is true or false
			- uses sigmoid function to fill the data (S-shape)
	- **Multi-class classification**
#### Regression - Continuous Data
- **Predict a numeric output**
- Linear regression (straigh-line relationship between n inputs to one single output)
	- Algorithm learns the **mapping function**, which represents the trained model
		- This function receives an input, and based on it's value, it calculates the result (output)
		- The entire purpose of a regression model is to perfect this function
#### Algorithms
##### KNN (K-Nearest Neighbors)
- Lazy learning algorithm (doesn't actually learn, just memorizes all training examples)
- Non-parametric
- Used for classification and regression
- Calculates the distance of the input to the trained data, 
	- Classify as "X" if the majority of "K" nearest neighbors belong to class "X"
	- Predicts based on the average of the values of "K" nearest neighbors
### Unsupervised Learning
- **Extracts trends and relationships from data**
- Main objective is to make the agent learn the **optimal policy** that will yield the most rewards
- Works with unlabeled data
- Finds patters or structures, grouping similar data into **clusters**
- Generation of songs, code, etc
### Reinforcement Learning
- **Used to make decision or choices**
- Trial and error (reward and penalty)
- AI learns from interections with the environment and feedback
- Playing videogames, robotics, etc
## Machine Learning Approaches
### Traditional Machine Learning
Best used for structured data
- **Decision Trees**: Flowchart decision structures (if/else)
- **Regression Algorithms**: Used to predict numerical values through relationships between variables
- **Clustering Algorithms**: Groups data into clusters based on similarity
### Deep Learning
Best used for large volumes of unstructured data and highly complex tasks
- **Artifical Neural Networks**: Like a human brain, process lots of datas and learn patterns from it
- **Convolutiona Neural Networks (CNNs)**: Specialized for vision tasks
- **Recurrent Neural Networks (RNNs)**: Efficient for sequential data, such as predictive text
### Advanced Deep Learning
- **Generative Models**: generate new data similar to input data
- **Transformer Architecture**: Consisting of encoders and decoders, used for language translation and code generation
