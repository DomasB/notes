What is a data contract?
------------------------

A data contract provides [schema](https://www.hopsworks.ai/dictionary/schema) level guarantees for a [feature group](https://www.hopsworks.ai/dictionary/feature-groups) and includes metadata such as how/where a feature may be used, the expected freshness of the feature, when it last updated, and optionally the service level agreement (SLA) for lookups.

‍**Why are data contracts important?**
--------------------------------------

Data contracts are important because they ensure consistency and compatibility of feature data across the different stages of a machine learning system ([feature pipelines](https://www.hopsworks.ai/dictionary/feature-pipeline), [training pipelines](https://www.hopsworks.ai/dictionary/training-pipeline), [inference pipelines](https://www.hopsworks.ai/dictionary/inference-pipeline)). By providing schema level guarantees, data contracts help to prevent issues with [data quality](http://www.hopsworks.ai/dictionary/data-quality), reliability, and versioning, ensuring that [downstream](https://www.hopsworks.ai/dictionary/downstream) systems and models can depend on the data being provided. Data contracts can also help to enforce governance and compliance requirements for feature data usage.

**How to implement an example data contract**
---------------------------------------------

Create a feature group containing customer purchase data, which includes features such as product name, price, and purchase date. The feature group should also include a schema version and metadata such as the description, owner, last updated when and by whom. Use custom metadata (e.g., schematized tags) to define governance and compliance requirements for the feature group. Then, for a model staged for deployment, you can use provenance to automatically find the features used by the model, and then check the governance and compliance requirements by looking up the custom metadata for all those features.

