**What is a precomputed feature?**
----------------------------------

A precomputed feature is a [[Feature|feature]] that has been created by a [[Feature Pipeline|feature pipeline]] and is stored in a [feature store](https://www.hopsworks.ai/dictionary/feature-store). [Training](https://www.hopsworks.ai/dictionary/training-pipeline) and [inference pipelines](https://www.hopsworks.ai/dictionary/inference-pipeline) can read precomputed features and use them directly for training or inference. Precomputed features are typically stored unencoded if they are intended for reuse across multiple models, but they can also be stored encoded if an online model has low latency SLAs and encoding the feature at runtime is too expensive.

‍


LLM Tags:  #precomputedfeatures #feature-pipeline #feature-store #training #inferencepipeline