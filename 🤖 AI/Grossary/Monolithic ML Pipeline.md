**What is a monolithic ML pipeline?**
-------------------------------------

A monolithic ML pipeline is a single program that can be run as either (1) a [[Feature Pipeline|feature pipeline]] followed by a [training pipeline](https://www.hopsworks.ai/dictionary/training-pipeline) or (2) a feature pipeline followed by a [batch inference pipeline](https://www.hopsworks.ai/dictionary/batch-inference-pipeline). The monolithic ML pipeline is typically parameterized to run in either TRAIN mode or INFERENCE mode. Training mode takes historical raw data, computes features from it, trains the model and then saves the model to a [model registry](https://www.hopsworks.ai/dictionary/model-registry). Inference mode takes inference data, computes features from it (using the same [feature logic](https://www.hopsworks.ai/dictionary/feature-logic) as in training mode), downloads the model from the model registry, and makes predictions on the input features, with the results output to some storage sink. 

Monolithic ML pipelines are only possible for batch ML systems, as online systems will need a separate [online inference pipeline](https://www.hopsworks.ai/dictionary/online-inference-pipeline). Their advantage over separate feature/training/inference pipelines is that there is no need for a [feature store](https://www.hopsworks.ai/dictionary/feature-store), but the disadvantage is that materialized features cannot be reused across different models. Monolithic ML pipelines are also larger, more monolithic, systems that are harder to maintain and develop. 

![Architecture Graph](https://assets.website-files.com/618399cd49d125734c8dec95/6436a3b6eec4f7469587eaf7_Ifh1YS936z_Z1pCZrffbpz4W95K8vc-_jJvQQReUfqp1Vp_eutXNyQ4pzgVTZRq67NZSEvjlJCe4x1R06lMSf6xwhFPWR30wnx1ZQJDkDfUq9MfCeKBJHXAI6f6EtPnqRxfc4Acp-g2ROb4cTx7Tsw.png)
LLM Tags:  
#monolithicpipelines
LLM Tags:  #ml-pipeline #monolithicpipelines #training-pipeline #inference-pipeline #model-registry #feature-pipeline
LLM Tags:  #monolithicpipelines, #ml-pipeline, #online-inference, #feature-store