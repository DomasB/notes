**What is model evaluation?**
-----------------------------

Model evaluation (or model validation) is the process of assessing the performance of a trained ML model on a (holdout) dataset. You want to establish the model’s ability to generalize - to make good predictions on new, unseen data.

**How do you perform model evaluation?**
----------------------------------------

Typically, you split your [training data](https://www.hopsworks.ai/dictionary/training-data) into a train set, optionally a [validation set](https://www.hopsworks.ai/dictionary/validation-set) if you will perform [hyperparameter tuning](https://www.hopsworks.ai/dictionary/hyperparameter-tuning), and a [test set](https://www.hopsworks.ai/dictionary/test-set) used to evaluate the trained model’s performance. The model is trained on the train set, [hyperparameters](https://www.hopsworks.ai/dictionary/hyperparameter) can be tuned using the validation set, and the model’s generalization performance is measured on the test set using one or more evaluation metrics.

If you evaluate a model for bias, you can further split your test set into slices, with one slice for each group you are investigating for [model bias](https://www.hopsworks.ai/dictionary/model-bias) (e.g., gender, ethnicity, geographic, etc). Then you evaluate the model’s performance for each group using one or more evaluation metrics and compare the results across all your groups to ensure there is similar [model performance](http://www.hopsworks.ai/dictionary/model-performance) across all groups.

**What are the most common model evaluation metrics?**
------------------------------------------------------

For a binary classification problem, common evaluation metrics include accuracy, precision, recall, F1 score, and area under the receiver operating characteristic curve (ROC AUC). For multi-class classification problems, a confusion matrix is often used that shows the counts of TPs (true positives), FPs (false positives), TNs (true negatives), and FNs (false negatives) for all predictions made using the test set. For regression problems, metrics such as mean squared error (MSE) and R-squared are commonly used.

