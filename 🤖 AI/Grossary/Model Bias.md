
> “Algorithms trained on biased data are biased. But learning algorithms themselves are not biased.” - [Yann LeCun](https://twitter.com/ylecun/status/1203211859366576128?lang=en)

**What is model bias in machine learning?**
-------------------------------------------

Model bias refers to the presence of systematic errors in a model that can cause it to consistently make incorrect predictions. These errors can arise from many sources, including the selection of the [training data](https://www.hopsworks.ai/dictionary/training-data), the choice of [features](https://www.hopsworks.ai/dictionary/feature) used to build the model, or the algorithm used to train the model.

**What types of model bias are there?**
---------------------------------------

Common forms of model bias include selection bias, measurement bias, and algorithmic bias. Selection bias occurs when the training data is not representative of the population being modeled, leading to biased predictions. Measurement bias occurs when the measurements used to train the model are inaccurate or imprecise, leading to biased estimates. Algorithmic bias occurs when the algorithm used to train the model produces biased predictions due to inherent biases in the algorithm or the data used to train it.

**How do you prevent bias in ML models?**
-----------------------------------------

You can prevent selection bias by ensuring your training data is representative of the different groups that your model will make predictions for. You can use evaluation sets (slices of your test set with data from groups identified of being at risk of bias) to evaluate your [model performance](http://www.hopsworks.ai/dictionary/model-performance) across different groups (e.g., based on gender, ethnicity, location, etc) and identify any performance differences across those groups. 

