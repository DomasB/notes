**What are hyperparameters in machine learning?**
-------------------------------------------------

**‍**In [training pipelines](https://www.hopsworks.ai/dictionary/training-pipeline), a hyperparameter is a parameter that influences the performance of [model training](http://www.hopsworks.ai/dictionary/model-training) but the hyperparameter itself is not updated during model training. 

Examples of hyperparameters include the learning rate, batch size, number of hidden layers, and regularization strength (e.g., dropout rate). You set these hyperparameters to fixed value before training and they will affect [model performance](http://www.hopsworks.ai/dictionary/model-performance) and generalization capability. So, you often experiment with different hyperparameters (hyperparameter tuning) to find good values for them. Hyperparameters contrast with model parameters that are updated during model training.

**Model-centric experiment tracking frameworks and hyperparameters**
--------------------------------------------------------------------

Model-centric experiment tracking frameworks, such as [MLFlow](https://mlflow.org/), [Weights & Biases](https://wandb.ai/site), and [Neptune.ai](https://neptune.ai/), help track the results of model training experiments with different combinations of hyperparameters (and different model architectures). The experimentation can be automated, in which case it is called [AutoML](https://www.hopsworks.ai/dictionary/auto-ml).

**Examples of hyperparameters**
-------------------------------

Examples of hyperparameters include the learning rate, batch size, number of epochs, number of layers in a feedforward deep learning model, and the model architecture itself. 


LLM Tags:  #ml #trainingpipelines #hyperparameter
LLM Tags:  #experimentation #hyperparameter #AutoML