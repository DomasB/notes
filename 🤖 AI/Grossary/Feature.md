**What are features in machine learning?**
------------------------------------------

A feature is a measurable property of some data-sample that is used as input for a [ML](https://www.hopsworks.ai/dictionary/ml) model for training and serving. A feature should have predictive power for the model it is being used in. 

**What questions do I need to ask about whether it is ok to use a particular feature in my model or not?**
----------------------------------------------------------------------------------------------------------

Predictive power is a necessary but not a sufficient condition for including a feature in a model. The feature 

* should have predictive power for your model,
* should be feasible for use in the model (i.e., you are able to compute the feature and use it when needed - online or offline),
* should not be redundant (e.g., highly correlated with an existing feature),
* should not be cost-prohibitive (i.e., using the feature means the model will not generate a ROI), and
* should not be prohibited from use or unethical to use.

**How important is it to select or create good features?**
----------------------------------------------------------

Features matter because they directly impact the accuracy and performance of machine learning models. Choosing the right set of features is critical for building effective models, and [feature engineering](https://www.hopsworks.ai/dictionary/feature-engineering) (now often called data-centric AI) is an iterative process of adding and removing features to find the best model given the available data and the available resources for training and inference.

‍**Example of features**
------------------------

**‍**In a model that tries to predict fraud for credit card transactions, the features might include the transaction amount and location for the current transactions as well as the number and location of transactions in recent windows of time (the last 5 minutes, 30 minutes, 1 hour, 6 hours). These features can help the model identify patterns such as chain attacks and geographic attacks that are indicative of fraudulent behavior.

