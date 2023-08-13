**What is a test set in machine learning?**
-------------------------------------------

**‍**The test set is a portion (or partition) of the available training data that is “held back” and not used during [model training](http://www.hopsworks.ai/dictionary/model-training). The purpose of the test set is to evaluate the performance of the model on unseen data after it has been trained. As such, the test set should not be explicitly or implicitly used during training or [hyperparameter tuning](https://www.hopsworks.ai/dictionary/hyperparameter-tuning). The test set is typically 10-30% of the training data.

**How is a test set defined?**
------------------------------

**‍**A test set is defined by splitting the original dataset into distinct partitions. The dataset is typically divided into three parts: the [training set](https://www.hopsworks.ai/dictionary/train-training-set), the [validation set](https://www.hopsworks.ai/dictionary/validation-set), and the test set. The training set is used to train the model, the validation set is used for hyperparameter tuning and model selection, and the test set is used to evaluate the final [model performance](http://www.hopsworks.ai/dictionary/model-performance).

The splitting process should ensure that the distribution of data in the test set is representative of the overall dataset. This can be achieved by using random sampling, time-series partitions, or stratified sampling, depending on the nature of the data. In time-series partitions, you typically create the train/validation sets from an earlier time range of data, and the test set from a time range after the train set (to test if the model can generalize to work well in future unseen data). In stratified sampling, the data is divided in such a way that the proportion of each class or category in the test set is the same as in the original dataset, ensuring a balanced representation of different classes or categories.

