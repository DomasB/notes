**What is a feature platform?**
-------------------------------

**‍**A feature platform is a [feature store](https://www.hopsworks.ai/dictionary/feature-store) that also provides support for a domain-specific language (DSL) to define [feature logic](https://www.hopsworks.ai/dictionary/feature-logic) and [[Feature Pipeline|feature pipelines]]. Feature platforms include an [orchestration](https://www.hopsworks.ai/dictionary/orchestration) engine for both feature pipelines and [on-demand features.](https://www.hopsworks.ai/dictionary/on-demand-features)

**Do I need a feature platform?**
---------------------------------

Feature platforms can provide benefits of a feature store such as centralization, standardization, and scalability. The DSL lowers the barrier for defining and productionizing common feature logic/pipelines. However, the DSL for feature logic/pipelines limits the scope of available feature transformations, data sources, [feature engineering](https://www.hopsworks.ai/dictionary/feature-engineering) frameworks, and orchestration support. In addition to a feature platform, you will need platforms for [training pipelines](https://www.hopsworks.ai/dictionary/training-pipeline) and [inference pipelines](https://www.hopsworks.ai/dictionary/inference-pipeline). In practice, this means you may have different orchestration engines for different ML pipelines (e.g., the feature platform for the feature pipeline, and Airflow for training and [batch inference pipelines](https://www.hopsworks.ai/dictionary/batch-inference-pipeline)).


LLM Tags:  #feature-store, #domainspecificlanguage, #feature-logic, #feature-pipeline, #orchestrationengine, #on-demand-features
LLM Tags:  #mlpractice #feature-engineering #trainingpipelines #inferencing