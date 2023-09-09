**What is a model registry?**
-----------------------------

A model registry is a version control system for models that provides APIs to store and retrieve models and [model-related artifacts](https://www.hopsworks.ai/dictionary/ml-artifacts). A model registry stores different versions of models, including metadata about their performance metrics, author, creation date, dependencies, usage, and lineage (training experiment code/[hyperparameters](https://www.hopsworks.ai/dictionary/hyperparameter) and /[[Training Data|training data]]).

**When is a model registry needed?**
------------------------------------

Model registries are recommended for projects involving [ML pipelines](https://www.hopsworks.ai/dictionary/ml-pipeline) and/or those that require stringent [governance](https://www.hopsworks.ai/dictionary/model-governance), traceability, and management. The model registry stores the models and their metadata as the output of [training pipelines](https://www.hopsworks.ai/dictionary/training-pipeline), decoupling training pipelines from [inference pipelines](https://www.hopsworks.ai/dictionary/inference-pipeline). Inference pipelines download a versioned model from the model registry during initialization, and keep it cached (this is safe, as models are immutable) for inference requests. In general, a model registry enables better collaboration, versioning, and organization of models in [MLOps](https://www.hopsworks.ai/dictionary/mlops).

**Examples of a model registry**
--------------------------------

Some model registries provide a unified API for storing and retrieving models and their metadata, such as [Hopsworks](https://docs.hopsworks.ai/latest/concepts/mlops/registry/), [Sagemaker](https://aws.amazon.com/sagemaker/), and [Weights & Biases](https://wandb.ai/site), while others, such as [MLFlow](https://mlflow.org/) or [Verta.ai](https://docs.verta.ai/), separate the metadata store for model metadata from an artifact store, where the serialized models are stored.

Example code for registering a Scikit-Learn model to Hopsworks is shown below:


```Python
from hsml.schema import Schema
from hsml.model_schema import ModelSchema

input_schema = Schema(X_train)  # take schema from train-set features DataFrame
output_schema = Schema(y_train) # take schema from train-set labels DataFrame

fraud_model = mr.sklearn.create_model("the_model",
                                      # 'accuracy' for the model is computed on the test set
                                      metrics={'accuracy': accuracy},
                                      # 'input_example' is used as a test row for a deployment
                                      input_example=X_train.sample().to_numpy(), 
                                      model_schema=ModelSchema(input_schema=input_schema, output_schema=output_schema))
fraud_model.save('the_model')

```

LLM Tags:  #model-registry,  #api, #artifact, #metadatamgmt
LLM Tags:  #model-registry #ml-pipeline #governance #training-pipeline #inference-pipeline #versioning #caching #collaboration #organization #mlops
LLM Tags:  #hobbies, #maths, #ml
LLM Tags:  #ml, #neural-network, #deep-learning