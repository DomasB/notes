**What is ETL?**
----------------

ETL stands for Extract, Transform, and Load of data. ETL is a process whereby a standalone compute engine, such as Spark, reads data from various data sources (operational databases, message queues, files), transforms the data into a standardized format suitable for analysis/ML, before storing the clean/formatted data to a target data warehouse or [lakehouse](https://www.hopsworks.ai/dictionary/data-lakehouse).

**Where is ETL important in ML systems?**
-----------------------------------------

ETL is a pattern often found in feature pipelines that extracts data from existing data stores, transforms the raw data into [features](https://www.hopsworks.ai/dictionary/feature) and then loads those features into a [feature store](https://www.hopsworks.ai/dictionary/feature-store).

