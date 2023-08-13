**What is a Point-in-Time (PiT) Correct Join?**
-----------------------------------------------

A point-in-time correct join is a database operation that performs a join between two tables in a way that ensures the results reflect the state of the tables at a specific point in time. 

**When is a Point-in-Time (PiT) Correct Join needed when creating training data?**
----------------------------------------------------------------------------------

When constructing a snapshot of data (e.g., training data or batch inference data) from [precomputed features](http://www.hopsworks.ai/dictionary/precomputed-features) spread across different [feature groups](https://www.hopsworks.ai/dictionary/feature-groups), we often need to construct a snapshot of [feature values](http://www.hopsworks.ai/dictionary/feature-value) at a specific point in time. For example, a training dataset for supervised ML is a snapshot of feature values at the time of the observation of each label in each row in the training dataset.

A problem with creating a point-in-time-correct training data snapshot is that the underlying tables (feature groups) are typically updated at different cadences by different [data pipelines](https://www.hopsworks.ai/dictionary/data-pipelines). As such, it is not always possible to utilize an exact time-based join to obtain the desired result. The solution is a Point-in-Time correct Join that starts with the timestamps for the labels and retrieves the most recent feature values for the features from all the tables joined with the table containing the labels.

‍

![architecture graph](https://assets.website-files.com/618399cd49d125734c8dec95/62bd624ae8ee7763c2de8506_JDGtcnBU0m4B76ZX8XrXLrLJm67q7aCTdyZBHYN6LPLuhCYMAaNDZFZee6Q2xFbiaL6nR_XsHR2HZsL3U2oI2PhmDZNtAcYx9ZkKztu43DCrSsjGW2zXMSPbY4IRHCz4Vnh6YVdsXZ4hSX83.png)**What problems can arise if you do not implement a PIT-Correct Join?**
-----------------------------------------------------------------------

1. **Avoiding label leakage:** Ensuring that the features used for training are only derived from data available at the point in time corresponding to the label prevents label leakage. Label leakage occurs when information from the future is unintentionally used for training, leading to over-optimistic [model performance](http://www.hopsworks.ai/dictionary/model-performance) that does not generalize well to real-world scenarios.
2. **Reproducibility**: PIT-Correct Join makes it possible to recreate historical snapshots of data consistently, which is essential for model reproducibility, debugging, and auditing purposes.
