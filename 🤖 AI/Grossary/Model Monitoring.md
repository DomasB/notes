**What is model monitoring?**
-----------------------------

Model monitoring involves continuously monitoring the performance of predictions made by models to identify potential problems such as anomalous predictions, label shift, or concept drift.

![Architecture graph](https://assets.website-files.com/618399cd49d125734c8dec95/64366b921f47efc565f0fa6b_qpq4SzYMGBII0EzcJufkXCjENZVGnmkbWgR52_u0bR1kFueSA-Ytfif-s62pGbmK2upHpJ3pq80NcxvdJBIQgAyImRxNE6lKZ9uKmzIGmCe8anWnYZBS5E1dyvZUZ9ZVyDyTEKem2NIkQRvimtLhPg.png)**What is Label Shift?**
------------------------

Label shift can be monitored by comparing the distribution of predictions in a reference dataset (typically, the training dataset) with a detection window of predictions (typically a window containing predictions made over a certain period of time, like the previous 24 hours). If there is a statistically significant difference between the distribution of predictions made by the model from those in the training dataset, then label shift has occurred. This may or may not have implications for whether your model needs to be retrained or not. It may be just that the detection window of inference requests is not representative of the [[Training Data|training data]] - for example, in an online ecommerce system, maybe users are searching more for a certain product because it is trending.

**What is Concept Drift?**
--------------------------

Concept drift is detected by comparing predictions to outcomes and if the predictions are statistically significantly worse than expected, based on the [model performance](http://www.hopsworks.ai/dictionary/model-performance) estimated after [model training](http://www.hopsworks.ai/dictionary/model-training), the model may need to be retrained. Sometimes it is not possible to observe the outcomes, and you can often use a ML proxy metric instead (for example, it may be a business KPI, such as increased revenue due to recommendations).

**What should I do if model monitoring detects problems?**
----------------------------------------------------------

When issues are detected, model monitoring can trigger alerts or notifications to the appropriate personnel, such as data scientists or machine learning engineers, who can investigate the issue and take action to address it. 


LLM Tags:  #monitoring, #model, #performance, #anomaly-detection, #label-shift
LLM Tags: #monitoring #predictionwindow #label-shift #trainingdataset
LLM Tags:  #monitoring #alerts #notifications #data-science #ml