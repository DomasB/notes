**What is feature monitoring?**
-------------------------------

Feature monitoring involves continuously monitoring the performance of the [[Feature|features]] used as model inputs in [inference pipelines](https://www.hopsworks.ai/dictionary/inference-pipeline) to identify potential problems such as anomalous inputs to models, out-of-distribution inputs for models, and drift in input [feature values](http://www.hopsworks.ai/dictionary/feature-value) such that the [model performance](http://www.hopsworks.ai/dictionary/model-performance) degrades. 

**How are features monitored?**
-------------------------------

A common method for feature monitoring is to analyze feature data in a reference dataset, typically the training dataset for a model, and compare a window of inference data (the detection dataset) for anomalies or drift with respect to the reference dataset. For numerical features, feature monitoring can involve calculating descriptive statistics (mean, standard deviation, min, max) and estimating the distribution of feature values in both the reference and detection datasets. For categorical features, this may involve identifying unseen categories in the inference data or detecting drift between the training data and a window of inference data.

Popular techniques for identifying drift between the distribution of feature values in reference and detection datasets include [Kullback-Leibler](https://towardsdatascience.com/understanding-kl-divergence-f3ddc8dff254) (KL) divergence, [Wasserstein Distance](https://kowshikchilamkurthy.medium.com/wasserstein-distance-contraction-mapping-and-modern-rl-theory-93ef740ae867), and [Jensen-Shannon](https://itsudit.medium.com/the-jensen-shannon-divergence-a-measure-of-distance-between-probability-distributions-23b2b1146550) (JS) Divergence. 

An alternative to these statistical methods is to train a classifier model on the reference dataset to try and distinguish between the reference and detection distributions. If the developed model can easily discriminate between the two sets of data, then training data drift (covariate shift) has occurred and the model will need to be recalibrated. It is also possible to monitor for drift in updates made by feature pipelines to feature groups by defining the reference window as the data (some subset of) in the feature group and the reference window as the data being written or some temporal window of data recently written to the feature group (e.g., data in the last week or the last 1GB of data written).  
  


![graph](https://assets.website-files.com/618399cd49d125734c8dec95/64366b921f47efc565f0fa6b_qpq4SzYMGBII0EzcJufkXCjENZVGnmkbWgR52_u0bR1kFueSA-Ytfif-s62pGbmK2upHpJ3pq80NcxvdJBIQgAyImRxNE6lKZ9uKmzIGmCe8anWnYZBS5E1dyvZUZ9ZVyDyTEKem2NIkQRvimtLhPg.png)**What should I do if feature monitoring detects problems?**
------------------------------------------------------------

When issues are detected, feature monitoring can trigger alerts or notifications to the appropriate personnel, such as data scientists or machine learning engineers, who can investigate the issue and take action to address it. 


LLM Tags:  #monitoring, #inference-pipeline #outofdistribution, #drift, #feature-value, #performancetracking
LLM Tags:  #monitoringtechniques, #anomaly-detection
LLM Tags:  #js
LLM Tags:  #ml, #classification, #driftmonitoring
 #ml