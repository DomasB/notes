**What is data-centric machine learning?**
------------------------------------------

Data-centric ML describes a set of practices for iteratively improving the quality of and set of available feature data for models. Data-centric ML practices can help iteratively improve a model’s performance by making improvements in the feature data used to train the model. Examples of improvements include adding more (high quality) feature data, adding [[Feature|features]] that have predictive power, and removing irrelevant/redundant features. Data-centric ML contrasts with [model-centric ML](https://www.hopsworks.ai/dictionary/model-centric-ml) that is concerned with iteratively improving [model architecture](https://www.hopsworks.ai/dictionary/model-architecture) and [hyperparameters](https://www.hopsworks.ai/dictionary/hyperparameter) to improve [model performance](http://www.hopsworks.ai/dictionary/model-performance).

**Why is data-centric ML important?**
-------------------------------------

It is important to note that while data-centric ML practices can greatly improve the quality of available feature data and thus model performance, every new [[Feature Pipeline|feature pipeline]] introduces development and operational costs. [Reusing features](https://www.hopsworks.ai/dictionary/feature-reuse) that are in the [feature store](https://www.hopsworks.ai/dictionary/feature-store) has negligible cost impact, but adding new features introduces costs. Therefore, it is crucial to prioritize the development and maintenance of new features. 

‍**Example of a data-centric approach with a feature store**
------------------------------------------------------------

**‍**Add existing features from the feature store or new features to your feature store for your model. The new features should have predictive power for your model, not be redundant, and are allowed to be used based on the model’s regulatory environment. Another alternative is to modify the [[Training Data|training data]] snapshot (e.g., include more recent feature data if it is available). 


LLM Tags:   #ml, #data-mining
LLM Tags:  #feature-pipeline, #reusingfeatures, #feature-store
LLM Tags:  #ml, #feature-engineering