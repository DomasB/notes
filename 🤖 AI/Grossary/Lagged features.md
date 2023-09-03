**What are lagged features?**
-----------------------------

Lagged features are a [feature engineering](https://www.hopsworks.ai/dictionary/feature-engineering) technique used to capture the temporal dependencies and patterns in time series data. A lagged feature is created by taking the value of a variable at a previous time point and including it as a [[Feature|feature]] in the model at the current time point. This is done by shifting the time series data by a certain number of time steps, which is referred to as the lag or time lag.

For example, if we have a time series of daily temperatures for the past 7 days, we can create lagged features by including the temperature values at the previous day, two days ago, three days ago, and so on. This allows the model to capture patterns in the data that are related to the previous values of the feature.


LLM Tags:  #time-series #feature-engineering #temporal_dependencies