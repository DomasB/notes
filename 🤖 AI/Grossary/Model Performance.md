**What is model performance in machine learning?**
--------------------------------------------------

Model performance in machine learning is a measurement of how accurate predictions or classifications a model makes on new, unseen data. You typically measure model performance using a [test set](https://www.hopsworks.ai/dictionary/test-set), where you compare the predictions on the test set to the actual outcomes. For classification, you can use accuracy as a measure of model performance, but you cannot use accuracy as a measure of model performance for regression problems, where metrics such as mean absolute error and (root) mean squared error are used.

**Causes of poor model performance**
------------------------------------

There can be many reasons for poor model performance, but some of the key things you should check for are:

* **Overfitting** - training for too long, so your model cannot generalize to perform well on unseen data;
* [**Data leakage**](https://www.hopsworks.ai/dictionary/data-leakage) - where the training data is polluted with test data or future data;
* **Model complexity** - has the model too many parameters compared to the number of training samples (a rule-of-thumb is that you should have 1 training sample for each model parameter/weight for DNNs);
* **Data quality** - is the data quality high enough?

LLM Tags:  #ml #modelperformance #overfitting
LLM Tags:  #data-leakage, #modelcomplexity