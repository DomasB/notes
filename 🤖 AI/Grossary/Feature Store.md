**What is a feature store?**
----------------------------

A feature store is a data platform that provides APIs for (1) ingesting features, (2) an Offline API for reading historical feature data, and (3) an Online API for reading the latest feature data at low latency. Internally, a feature store is typically a dual-database system, with an [offline store](https://www.hopsworks.ai/dictionary/offline-store) (used by the offline API) that is typically a columnar store, and an [online store](https://www.hopsworks.ai/dictionary/online-store) (used by the online API) that is typically a row-oriented database or key-value store. The implementation of the write API should ensure that feature data is consistently replicated between the online and offline stores.

**Do I need a feature store?**
------------------------------

Feature stores have historically been part of big data ML platforms, such as [Uber’s Michelangelo](https://www.uber.com/en-SE/blog/michelangelo-machine-learning-platform/), that manage the entire ML workflow, from specifying [feature logic](https://www.hopsworks.ai/dictionary/feature-logic), to creating and operating [[Feature Pipeline|feature pipelines]], [training pipelines](https://www.hopsworks.ai/dictionary/training-pipeline), and [inference pipelines](https://www.hopsworks.ai/dictionary/inference-pipeline). 

More recent open-source feature stores provide open APIs enabling easy integration with existing ML pipelines written in Python, Spark, Flink, or SQL. Serverless feature stores further reduce the barriers of adoption for smaller teams. The key [[Feature|features]] needed by most teams include APIs for consistent reading/writing of point-in-time correct feature data, monitoring of features, [feature discovery and reuse](https://www.hopsworks.ai/dictionary/feature-reuse), and the versioning and tracking of feature data over time. Basically, feature stores are needed for [MLOps](https://www.hopsworks.ai/dictionary/mlops) and governance. Do you need Github to manage your source code? No, but it helps. Similarly, do you need a feature store to manage your features for ML? No, but it helps.


LLM Tags:   #offlinestore, #onlineapi
LLM Tags:  #mlplatforms, #feature-store, #feature-logic, #feature-pipeline, #trainingsystems
LLM Tags:  #ml, #feature-store, #open-source, #api, #python, #spark, #flink, #sql