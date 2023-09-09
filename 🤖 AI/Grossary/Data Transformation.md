**What is data transformation?**
--------------------------------

**‍**A data transformation is a function that is applied to some input data that changes the data in such a way that the data is easier to consume by [downstream](https://www.hopsworks.ai/dictionary/downstream) applications or users (often business intelligence or [[ML]]). Data transformations can take many forms, from simple operations such as filtering or sorting, to complex algorithms such as grouped aggregations, binning, dimensionality reduction, or data cleaning. 

‍**Why are Data Transformations important?**
--------------------------------------------

Data transformations are important because they allow raw data to be cleaned, processed, and standardized, making it easier to work with and analyze. By transforming data into a format that is compatible with downstream applications and systems, data transformations can help improve the accuracy and efficiency of machine learning models and other data-driven applications.

‍**Important classes of data transformations used for ML systems include**
--------------------------------------------------------------------------

* **Stateless transformations** - they can be implemented as[[Idempotent ML Pipelines|idempotent]]  functions, making them easy to re-execute in case of failures,
* **Partitionable** - the transformation can be run in parallel over many workers, enabling scalable/faster transformations,
* **Window-based aggregations** - streaming pipelines accumulate state in windows over time and fixed-sized window aggregations can be computed by batch pipelines,
* ML transformations that are based on a **reference window** (such as encoding of numerical/categorical features for [data compatibility](http://www.hopsworks.ai/dictionary/data-compatibility) or performance).

LLM Tags:  #data-transformation #ml-pipeline #data-processing
LLM Tags:  #data-analysis #data-transformation #ml #parquet
LLM Tags:  #mltransformations #streamingpipelines