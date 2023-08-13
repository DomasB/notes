**What are on-demand features?**
--------------------------------

**‍**If a [feature](https://www.hopsworks.ai/dictionary/feature) is used in an [online inference pipeline](https://www.hopsworks.ai/dictionary/online-inference-pipeline) and it is created using data only available at request-time, then it is an on-demand feature. If you have historical data, you would like to be able to create the same [feature values](http://www.hopsworks.ai/dictionary/feature-value) in your feature pipeline using the same code as is used in the online inference pipeline (to avoid [online-offline skew](https://www.hopsworks.ai/dictionary/online-offline-feature-skew)).

**What is the use case for on-demand features?**
------------------------------------------------

On-demand features are typically used when real-time data is critical to the machine learning model's performance or when data availability constraints require the feature to be calculated at request-time.

‍**When should you use on-demand features?**
--------------------------------------------

**‍**In general, it is preferable to precompute features in [feature pipelines](https://www.hopsworks.ai/dictionary/feature-pipeline) and store them in a [feature store](https://www.hopsworks.ai/dictionary/feature-store), retrieving them when needed in your online inference pipeline. Having a single place (the feature pipeline) where features are computed prevents online-offline skew, and enables materialized feature values to be shared across multiple models, promoting collaboration and reducing duplication of effort. By centralizing and precomputing features, teams can maintain a single source of truth for features, which simplifies the development process and fosters consistency across projects. On-demand can lead to increased latency or computational overhead in the online inference pipeline, negatively impacting prediction latency. However, if the input data used to compute a feature is only available at request time, then you will need to implement an on-demand feature. For example, if you are predicting credit-card fraud online, some credit card transaction features (computed from the transaction purchase amount, category of purchase, location of purchase, timestamp for the purchase) will only be available as on-demand features.

