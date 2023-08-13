**What is an online-offline feature skew?**
-------------------------------------------

**‍**Feature [skew](https://www.hopsworks.ai/dictionary/skew) is when there are significant differences between the [feature logic](https://www.hopsworks.ai/dictionary/feature-logic) executed in an offline ML pipeline and the feature logic executed in the corresponding [online inference pipeline](https://www.hopsworks.ai/dictionary/online-inference-pipeline).

The necessary conditions for feature skew are:

1. the feature logic (either [model-dependent](https://www.hopsworks.ai/dictionary/model-dependent-transformations) or [model-independent transformations](https://www.hopsworks.ai/dictionary/model-independent-transformations)) is non DRY between an offline (feature or training) pipeline and the corresponding online inference pipeline;
2. there are unintended differences between the two implementations of the feature logic leading to significantly different [feature values](http://www.hopsworks.ai/dictionary/feature-value) being computed for the same input data.

[On-demand feature transformations](https://www.hopsworks.ai/dictionary/on-demand-transformation) are applied in both the feature and online-inference pipelines and different implementations can result in on-demand feature skews. [Training-inference skew](https://www.hopsworks.ai/dictionary/training-inference-skew) can occur when model-dependent transformations are implemented differently in the training and online inference pipelines. Feature skew can silently and negatively affect [model performance](http://www.hopsworks.ai/dictionary/model-performance) making such issues difficult to detect.

**Why is it important to prevent feature skew?**
------------------------------------------------

Feature skew can result in silently degraded model performance that is difficult to discover. It will show up during online inference, as the model may not generalize well to the new data during inference due to the discrepancies in feature transformations. 

**Example of training-inference skew**
--------------------------------------

Consider a feature transformation where the raw data is scaled using the mean and standard deviation calculated from the training dataset. Suppose the following code snippets are used for the transformations during the training pipeline and online inference pipeline:

**Feature Pipeline:** 


```
 import numpy as np

# Training data
data = np.array([1, 2, 3, 4, 5])

# Calculate mean and std
mean = np.mean(data)
std = np.std(data)

# Scale the data
scaled_data = (data - mean) / std

```
**Online inference pipeline:**


```
 import numpy as np

# New data for inference
new_data = np.array([6, 7, 8, 9, 10])

# Calculate mean and std using new data (incorrect)
new_mean = np.mean(new_data)
new_std = np.std(new_data)

# Scale the new data (incorrect transformation)
scaled_new_data = (new_data - new_mean) / new_std

```
In this example, the feature transformation at the inference stage incorrectly calculates the mean and standard deviation from the new data instead of using the values from the training dataset. This discrepancy leads to training/inference skew and can negatively impact the model's performance during inference.

