**What is an ML pipeline?**
---------------------------

**‍**A ML pipeline is a program that takes input and produces one or more [ML artifacts](https://www.hopsworks.ai/dictionary/ml-artifacts) as output. Typically, a ML pipeline is one of the following: a [feature pipeline](https://www.hopsworks.ai/dictionary/feature-pipeline), a [training pipeline](https://www.hopsworks.ai/dictionary/training-pipeline), or an [inference pipeline](https://www.hopsworks.ai/dictionary/inference-pipeline). 

**Why are ML pipelines important?**
-----------------------------------

ML pipelines help ensure the reproducibility and scalability of machine learning workflows. By encapsulating the entire process in multiple pipelines, it is easier to manage, version control, and share the different stages of the process. 

**How are ML pipelines related to the feature store?**
------------------------------------------------------

If you have a [feature store](https://www.hopsworks.ai/dictionary/feature-store), you can decompose a monolithic ML pipeline into feature, training and inference pipelines. The feature store becomes the data layer for your ML pipelines, storing the outputs of the feature pipeline, and providing inputs to the training and inference pipelines. 

