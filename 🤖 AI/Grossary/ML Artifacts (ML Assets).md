**What are ML artifacts?**
--------------------------

ML artifacts (or ML assets) are outputs of [[ML Pipeline|ML pipelines]] that are needed for execution of subsequent pipelines or ML applications. Models, [[Feature|features]], [[Training Data|training data]], and [inference data](https://www.hopsworks.ai/dictionary/inference-data) are the most well known ML artifacts. ML artifacts are typically not in a database (where metadata for ML pipelines is stored). Instead, popular artifact stores are file systems, object stores, feature stores, and model registries. 

**Why are ML artifacts important?**
-----------------------------------

ML artifacts are important because they capture the outputs of machine learning pipelines that are used as inputs for subsequent pipelines or for deployment in production systems. Artifacts should have a [version](https://www.hopsworks.ai/dictionary/versioning-ml-artifacts) and a [schema](https://www.hopsworks.ai/dictionary/schema), enabling [MLOps](https://www.hopsworks.ai/dictionary/mlops) patterns around upgrading and downgrading models in production.


LLM Tags:  #ml-artifacts #ml-pipeline #training-data #inference-data
LLM Tags:  #ml , #artifact, #versioning, #schemata, #mlops