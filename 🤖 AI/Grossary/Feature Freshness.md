**What is feature freshness in ML?**
------------------------------------

**‍**Feature freshness refers to the time lag between when the date required to compute a [[Feature|feature]] becomes available to when the feature is available for use in an [inference pipeline](https://www.hopsworks.ai/dictionary/inference-pipeline). 

**Why is feature freshness a useful system property of a ML system?**
---------------------------------------------------------------------

The freshness of features can be critical in applications where the decision(s) made by the [[ML]] model require that the features used to make the decision are not older than a certain amount of time. For example, if an online credit card fraud detection ML system only has features that are 1 hour old or older, then it will massively underperform during the first hour that a given credit card starts to be used fraudulently.

**What is feature freshness for training data?**
------------------------------------------------

Feature freshness for [[Training Data|training data]] is when the data used to train a model is not the most recent feature data available. You can improve feature freshness for training data by recreating or updating the training dataset with the latest available feature data. 

**How can you improve feature freshness in ML systems?**
--------------------------------------------------------

For [[Feature Pipeline|feature pipelines]], you can switch from batch feature pipelines to streaming feature pipelines. This will reduce the time between when data used to compute features becomes available and when it is written to a [feature store](https://www.hopsworks.ai/dictionary/feature-store), from where it can be used in model inference. If you have the possibility to use an [on-demand feature](https://www.hopsworks.ai/dictionary/on-demand-features) instead of a [precomputed feature](http://www.hopsworks.ai/dictionary/precomputed-features), you may be able to improve that feature’s freshness by switching to an on-demand feature. If you are using a high latency online feature store to retrieve precomputed features, you can improve feature freshness by switching to a lower-latency online feature store.

**What is feature freshness in a batch feature pipeline?**
----------------------------------------------------------

In batch systems, you have to add together the amount of time that has passed since the batch of features has been created until when the row is processed by the model in the batch inference program.

**What is feature freshness in a streaming feature pipeline?**
--------------------------------------------------------------

In a [streaming feature pipeline](https://www.hopsworks.ai/dictionary/streaming-feature-pipeline), the time between when the streaming event or batch of events has been created to when the streaming feature pipeline writes the updated [feature value](http://www.hopsworks.ai/dictionary/feature-value) to the online feature store.


LLM Tags:  #ml #feature-freshness #inferencepipeline
LLM Tags:  #ml, #trainingdata
LLM Tags:  #feature-pipeline #streamingfeatures #on-demand-features #precomputedfeatures #lowern latency
LLM Tags:  #streaming, #onlinelearning, #pipeline