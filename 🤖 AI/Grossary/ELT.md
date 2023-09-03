**What is ELT?**
----------------

ELT stands for Extract, Load, and Transform of data. ELT is a process whereby a system first extracts data from various sources and then loaded as-is into a data warehouse. Finally, the data is transformed directly in the data warehouse (normally using SQL) into a standardized format suitable for analysis/ML. Compared to the traditional [ETL](https://www.hopsworks.ai/dictionary/etl) process, where data is transformed in an external engine, like Spark, before it is loaded into the warehouse, in ELT, the data is transformed in-place using SQL in the data warehouse.

**Where is ELT important in ML systems?**
-----------------------------------------

ELT is often found in [[Feature|feature pipelines](https://www.hopsworks.ai/dictionary/feature-pipeline) that extract data from existing data stores, load it into a data warehouse or [feature store](https://www.hopsworks.ai/dictionary/feature-store), and then transform the raw data into [features]] in the data warehouse or feature store. 


LLM Tags:  #ELT #data-warehouse #SQL #ETL #ml
LLM Tags:  #data-warehouse #transformations, #pipelines