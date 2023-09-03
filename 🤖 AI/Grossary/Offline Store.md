**What is an offline store in a feature store?**
------------------------------------------------

The offline store in a [[Feature|feature store](https://www.hopsworks.ai/dictionary/feature-store) stores the historical values of [features]], enabling efficient and scalable access to large volumes of historical feature data for [model training](http://www.hopsworks.ai/dictionary/model-training) and batch inference. The offline store is typically implemented as a column-oriented store, which offers advantages in terms of storage efficiency, query performance, cost, and scalability.  By maintaining a comprehensive record of feature history, the offline store contributes to the reproducibility of models and allows data scientists to perform time-based analysis, identify trends, and uncover insights.

A popular offline feature store is to store feature data in an object store or distributed file system in a lakehouse file format (Apache Hudi, Delta Lake, Apache Iceberg). Another popular option is to use a data warehouse as an offline feature store.


LLM Tags:  #offlinestore #feature-store #modeltraining
LLM Tags:  #data-warehouse #offlinestore #lakehouserescue