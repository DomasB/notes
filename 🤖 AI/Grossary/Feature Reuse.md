**What is feature reuse?**
--------------------------

***‍***[Features](https://www.hopsworks.ai/dictionary/feature) are computed in a [feature pipeline](https://www.hopsworks.ai/dictionary/feature-pipeline) and stored in the feature store. Features are reused if the same feature is used in more than one model. That is, the feature is included in one or more feature views, and therefore is included in more than one training/inference pipeline. It is also possible to reuse the same [feature logic](https://www.hopsworks.ai/dictionary/feature-logic) in one or more feature pipelines, also enabling feature reuse. 

**Why is feature reuse important?**
-----------------------------------

Feature reuse is important because it can help reduce the time and cost required for [feature engineering](https://www.hopsworks.ai/dictionary/feature-engineering), since pre-existing features can be reused across multiple models. Without feature reuse, you would have to re-write feature logic for one or more feature pipelines for each model you put in production. Every additional feature pipeline you need to operate adds additional costs, so lack of feature reuse massively increases the cost and complexity of putting models in production. Lack of feature reuse results in non-DRY feature logic across your code base, while DRY feature logic promotes more consistent and accurate features when used across multiple models.

**Can I reuse encoded features across different models?**
---------------------------------------------------------

In general, you can’t reuse features that have been encoded, because [feature encodings](https://www.hopsworks.ai/dictionary/encoding-for-features) are computed against a reference dataset, which is typically the training dataset for the model. When you one-hot-encode a categorical feature or min-max scale a numerical feature, you encode with respect to a reference dataset. If the reference dataset is a set or subset of the data in a [feature group](https://www.hopsworks.ai/dictionary/feature-groups), you will typically need to re-encode the existing feature data in the feature group when new data is inserted (which should happen at a well-defined cadence). The solution for feature reuse is to only encode feature data in the [training](https://www.hopsworks.ai/dictionary/training-pipeline) and [inference pipelines](https://www.hopsworks.ai/dictionary/inference-pipeline) (and to ensure consistent encodings - no skew). 

**Example of feature reuse**
----------------------------

**‍**An example of feature reuse would be a customer churn prediction model and a customer lifetime value model both using the same feature for customer purchase history. Instead of re-computing the feature for each model, the pre-existing feature code or feature data could be reused, reducing the time and cost required for feature engineering.

