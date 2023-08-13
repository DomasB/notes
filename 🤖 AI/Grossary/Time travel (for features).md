**What is time travel for features?**
-------------------------------------

**‍**Time travel for features refers to the ability to access historical versions of [feature values](http://www.hopsworks.ai/dictionary/feature-value) at previous points in time. [Feature stores](https://www.hopsworks.ai/dictionary/feature-store) maintain versioned records of feature data in [feature groups](https://www.hopsworks.ai/dictionary/feature-groups), so that you can "travel back in time" to inspect previous values of the features.

**When and how is time travel useful?**
---------------------------------------

1. [**Point-in-time Correct Joins**](https://www.hopsworks.ai/dictionary/point-in-time-correct-joins): Time travel allows you to access historical feature data for creating training data with a PiT correct join.
2. **Reproducibility**: [Time travel](https://www.hopsworks.ai/dictionary/time-travel-for-features) helps you maintain the reproducibility of [training datasets](https://www.hopsworks.ai/dictionary/train-training-set), as it enables you to recreate the exact state of the feature data used during the development and training of a model.
3. **Debugging and diagnostics**: By accessing historical feature data, you can identify any changes in feature distributions or [data quality](http://www.hopsworks.ai/dictionary/data-quality) issues that may have impacted [model performance](http://www.hopsworks.ai/dictionary/model-performance).
4. **Auditing and compliance**: Time travel can be beneficial for auditing and compliance purposes. It allows you to demonstrate that they have followed the necessary processes and maintained the required data quality standards over time.
