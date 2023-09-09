**What is a DAG processing model?**
-----------------------------------

A DAG (directed acyclic graph) processing model is a method of representing the dependencies between tasks in a workflow or pipeline. In a DAG processing model, tasks are represented as nodes in a directed acyclic graph, where the edges represent the dependencies between tasks. This means that a task can only be executed once all of its dependencies have been completed. 

Apache Spark/Flink/Beam implement a **dataflow processing model as a DAG**, where data flows between nodes via edges. In contrast, Airflow/Dagster are only [orchestration](https://www.hopsworks.ai/dictionary/orchestration) engines - they use a DAG to define tasks and dependencies, e.g., the steps to execute in an [ETL](https://www.hopsworks.ai/dictionary/etl) job.

DAGs are a more challenging programming paradigm compared to imperative programs, as tasks should be implemented as [[Idempotent ML Pipelines|idempotent]] steps. However, the benefits include enabling scalable data processing (parallel execution of tasks), fault tolerance (by transparently retrying failed tasks), and automatic lineage for processing steps.

**Where are DAGs found in FTI pipelines?**
------------------------------------------

DAGS are used in [[Feature Pipeline|feature pipelines]] when you implement your [feature engineering](https://www.hopsworks.ai/dictionary/feature-engineering) in a data processing system such as Apache Airflow and Apache Spark. DAGs are encountered in both online and offline inference pipelines, where predictions from one model may be inputs to another model. For [batch inference pipelines](https://www.hopsworks.ai/dictionary/batch-inference-pipeline), again Airflow and Spark are popular execution engines. For [online inference](https://www.hopsworks.ai/dictionary/online-inference-pipeline), frameworks such as KServe support the definition and execution of multi-stage pipelines where predictions from one model are fed as input to [downstream](https://www.hopsworks.ai/dictionary/downstream) models.

LLM Tags:  #programmingmodels, #data-processing, #ml-pipeline, #parallelprocessing
LLM Tags:  #data-processing, #feature-engineering, #spark, #kserve, #prediction, #inference-pipeline