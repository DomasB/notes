**What is Data Leakage?**
-------------------------

Data leakage occurs when data that should be outside the [training dataset](https://www.hopsworks.ai/dictionary/train-training-set) is explicitly or implicitly used to train a model. Data leakage can result in the incorrect estimation of the trained model’s performance. 

‍**Training data leakage** is when data from the [test set](https://www.hopsworks.ai/dictionary/test-set) or [validation set](https://www.hopsworks.ai/dictionary/validation-set) is explicitly or implicitly used to train a model. **Future data leakage** is when [training data](https://www.hopsworks.ai/dictionary/training-data) is constructed in such a way that training samples include [feature values](http://www.hopsworks.ai/dictionary/feature-value) from the future. That is, training leaks knowledge of the future into the model, resulting in a model that performs well on the training set, but poorly on unseen data. 

‍**Feature data leakage** is when you include a feature when training a model, but that feature is not available at inference time. You should, hopefully, discover feature data leakage when you try to write your [inference pipeline](https://www.hopsworks.ai/dictionary/inference-pipeline) and realize the feature is not available. The use of a [feature store](https://www.hopsworks.ai/dictionary/feature-store), that informs you whether your feature will be available for online models or only offline models, should help prevent you from training models with feature data leakage.

