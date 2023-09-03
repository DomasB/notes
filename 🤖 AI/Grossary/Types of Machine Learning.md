ML models are trained to solve different business prediction problems like classification (predict what class an example falls into), regression (predict a number), and language modeling (predict the text tokens to output based on some input text).  Training a ML model involves collecting and managing training data examples, using a ML algorithm that includes an error function to evaluate the accuracy of examples, and then an optimization process to fit the data points to the model.

‍

The most popular machine learning types are:

1. Supervised Machine Learning
	* Requires input features and labels (or target columns) as training data.
	* In model inference, it predicts labels/targets using input features and the trained model.
	* Classification and Regression are the two main types of supervised ML
	
		1. Predicting whether a passenger on the Titanic will survive or not is an example of a classification problem.
			+ The input features are the passenger’s gender, the ticket price, the passenger class, and the label (or target column) defines whether the passenger survived or not.
		2. Predicting the price of a property is an example of a regression problem.
			+ The input features are the property’s location, size, and number of rooms.
			+ The target (label) column is the price of the property.
2. Unsupervised Machine Learning
	* Learn hidden patterns, differences, and similarities in data without any labels for the data.
	* Requires input features, but no labels in training data.
	* Often used to pre-train a model using huge volumes of data.
	* Unsupervised self-training with masking
		+ When training a LLM with semi-supervised ML, you mask out some text, and train the model to predict the masked-out text. The input features and labels are string tokens, created by tokenizing the text in the training data.
		+ When training an image segmentation model with semi-supervised ML, you mask out some of the image, and train the model to predict the masked-out part of the image. The input features/labels are the images, and a segmenter will select.
	* Clustering and Anomaly Detection
		+ Unsupervised ML is used to cluster input data into inherent groups. It is a way to group the objects into a cluster such that the objects with the most similarities remain in one group and have fewer or no similarities with the objects of other groups. An example of the clustering algorithm is grouping the customers by their purchasing behavior.
	* In model inference for LLMs, the trained model predicts output text tokens given some input text.
	* In model inference for image segmentation, the trained model predicts the segments in an image or missing parts of an image.
3. Semi-Supervised Machine Learning
	* Train an initial model on a few labeled training examples and then continue to train the model on larger volumes of unlabeled data.
4. Reinforcement Learning
	* In reinforcement learning, an agent learns its behavior over time by taking actions in an environment, receiving feedback (rewards) on those actions (if they were good or bad), and optimizing the actions it takes to maximize the reward. The rewards can also be costs, in which case the agent attempts to minimize the costs of its actions. The agent’s environment can be a model of the environment, model-free, or learn using deep learning.
	* In reinforcement learning, there is no labeled data like supervised learning, and agents learn from their experiences (and potentially experiences of other agents).
5. In-Context Learning
	* In a pre-trained transformer model, in-context learning (ICL) (or zero-shot/few-shot learning) is the ability of the model to learn a new task from a small set of examples presented within the prompt at inference time. In-context learning can help improve the performance of the predictions produced by LLMs for a specific task. It can also be used to personalize a LLM by providing history and context about a user as part of a prompt.

LLM Tags:  #ml, #mlmodels, #predictionproblems, #supervisedlearning
LLM Tags:  #ml, #regression, #unsupervisedlearning, #selftraining
LLM Tags:  #image-segmentation #anomaly-detection #unsupervisedml
LLM Tags:  #reinforcementlearning #ml #deeplearning #in-context-learning
LLM Tags:  #in-context-learning, #llm, #personalization