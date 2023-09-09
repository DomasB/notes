---
aliases:
  - Feature storage
tags: "#offline-store #onlineapi #ml-platform #feature-store #feature-logic #feature-pipeline #ml #api #python #spark #flink #sql"
---
## What is a feature store?
A feature store is a data platform that provides APIs for (1) ingesting features, (2) an Offline API for reading historical feature data, and (3) an Online API for reading the latest feature data at low latency. Internally, a feature store is typically a dual-database system, with an [[offline store]] (used by the offline API) that is typically a columnar store, and an [[online store]] (used by the online API) that is typically a row-oriented database or key-value store. The implementation of the write API should ensure that feature data is consistently replicated between the online and offline stores.

## Do I need a feature store?
Feature stores have historically been part of big data ML platforms, such as [Uber’s Michelangelo](https://www.uber.com/en-SE/blog/michelangelo-machine-learning-platform/), that manage the entire ML workflow, from specifying [[feature logic]], to creating and operating [[Feature Pipeline|feature pipelines]], [[Training Pipeline|training pipelines]], and [[Inference Pipeline|inference pipelines]]. 

More recent open-source feature stores provide open APIs enabling easy integration with existing ML pipelines written in Python, Spark, Flink, or SQL. Serverless feature stores further reduce the barriers of adoption for smaller teams. The key [[Feature|features]] needed by most teams include APIs for consistent reading/writing of point-in-time correct feature data, monitoring of features, [[Feature Reuse|feature discovery and reuse]], and the versioning and tracking of feature data over time. Basically, feature stores are needed for [[MLOps]] and governance. 

Examples: [Feast](https://docs.feast.dev/)
