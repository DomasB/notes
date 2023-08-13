**What is an inference pipeline?**
----------------------------------

**‍**An inference pipeline is a program that takes input data, optionally transforms that data, then makes predictions on that input data using a model. Inference pipelines can be either batch programs or online services. In general, if you need to apply a trained machine learning model to new data, you will need some type of inference pipeline.

**Do I need an inference pipeline?**
------------------------------------

If you are building a machine learning model that will be used in production to make predictions on new data, then you will likely need an inference pipeline to take that new input data and apply the trained model to make predictions.

**How do I implement an inference pipeline?**
---------------------------------------------

An inference pipeline typically involves first an initialization step that includes downloading the trained model from a [model registry](https://www.hopsworks.ai/dictionary/model-registry), loading any necessary dependencies (such as importing libraries), and establishing a connection to a [feature store.](https://www.hopsworks.ai/dictionary/feature-store) The inference step involves setting up the input [data pipeline](https://www.hopsworks.ai/dictionary/data-pipelines), making predictions on the input data using the model, and optionally post-processing the predictions. If a feature store is used, the inference pipeline can read [precomputed features](http://www.hopsworks.ai/dictionary/precomputed-features) directly from the feature store, perform any necessary on-demand feature [transformations](https://www.hopsworks.ai/dictionary/transformation) and any [feature encodings](https://www.hopsworks.ai/dictionary/encoding-for-features), and then pass the transformed features to the model for prediction. 

**What is the difference between an online inference pipeline and an offline (batch) inference pipeline?**
----------------------------------------------------------------------------------------------------------

Model deployments run 24x7 and serve inference requests over the network, typically using some model serving infrastructure. The [online inference pipeline](https://www.hopsworks.ai/dictionary/online-inference-pipeline) is the code that is executed before and after the trained model makes predictions as part of an online inference request. In contrast, a [batch inference pipeline](https://www.hopsworks.ai/dictionary/batch-inference-pipeline) is a program that is run on a schedule to make predictions on (typically) new inference data that has arrived since the last time the batch inference pipeline ran. 

