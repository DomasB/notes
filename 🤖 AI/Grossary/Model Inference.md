Model inference (or machine learning inference) is when a model makes predictions on new, unseen input data (inference data) and produces predictions as output that are consumed by a user or service.

  
Model inference requires a 

* ML model,
* inference data,
* an inference pipeline,
* and a prediction consumer.

The inference pipeline is  a program that takes the inference data, optionally transforms that data, then makes predictions on the transformed inference data using the model. The prediction consumer is a person or a service that makes use of the model predictions. The prediction consumer could be a database that stores the predictions to allow them to be viewed on a dashboard (e.g., an air quality dashboard for a city) or to be delivered to users of some online service when the user logs on to that service (e.g., show the user the list of songs recommended once per week by Spotify).

‍

‍**Batch Model Inference**

When model inference is performed by a program that runs on a schedule (e.g., once per day/hour), and the predictions are stored in some output sink (e.g., a database), we typically refer to this as batch model inference. Batch model inference programs will typically read the inference data from a feature store as a DataFrame (e.g., new feature data that arrived in the last 24 hours, or the latest feature values for all users in the system), download the model from a model registry, make predictions on the input DataFrame using the model with a user-defined function, and save the output predictions to some stable storage (like a database, data warehouse, file system, or object store).

‍

‍**Online Model Inference**

Model inference can be exposed as request-response network services using model serving infrastructure. The model is typically exposed as a REST or gRPC endpoint, that should support authentication and access control.

A model serving framework, such as [KServe](https://github.com/kserve/kserve), can be used to deploy the model. The model is often deployed by embedding it in a class, so that you can perform setup actions for the model when it is deployed and pre- and post-actions when the model makes predictions. For model serving frameworks like Tensorflow Serving, where you can deploy the model without a prediction class, you can often add a transformer component, written in Python, that performs pre- and post-actions when the model makes predictions. 

Common examples of pre-actions are to retrieve precomputed features from a feature store, compute on-demand features, and build the feature vectors that are the model input for prediction. A common example of a post-action is to take the output of a model prediction and use it as input to another model.

‍

‍**Stream Processing Model Inference**

A model can be downloaded from a Model Registry and embedded in a stream processing application to make predictions on events that are ingested from a message bus (such as Kafka or Kinesis). 

Machine-to-machine AI applications are a popular use case for stream processing model inference. For example, if you have a collection of sensors that publish regular sensor measurements to a Kafka topic, a stream processing model can perform anomaly detection on the sensor readings and alert if a sensor produces anomalous measurements. This type of use case is an example of predictive maintenance.

‍

‍**How do I measure the performance of model inference?**

You typically use throughput and latency, where throughput is the number of requests/second that a model can process, and latency is the time taken to process one or a batch of predictions. 

‍

‍**How do I scale out the performance of batch model inference?**

For batch models, you can often start with Python/Pandas programs, but when the inference data volumes increase to more data than can be processed in-memory on a single server, you switch to PySpark. In both cases, you can keep the DataFrame/model/UDF pattern, although you may switch to Pandas UDFs in PySpark for improved throughput compared to Python UDFs. Some Data Warehouses also support UDFs that can be used for batch inference. If you have a deep learning model, you may need a GPU to improve model inference performance.

‍

‍**How do I scale out the performance of online model inference?**

You typically replicate the model inference servers and load balance input requests across the model inference servers. Frameworks such as K-Serve will load balance the requests transparently to clients and provide support for auto-scaling the number of model serving instances in a load-balancing group (scale up the number of instances when load is higher, and scale down the number of instances when load is lower). If you have a deep learning model, you may need a GPU to improve model inference performance.

‍

‍**How do I scale out the performance of stream processing model inference?**

You can increase the number of workers in your stream processing application, as each worker will typically have its own embedded model and will make predictions locally within the worker. If you are making predictions over changes in windows of data, then predictions are made over data synchronized from multiple workers. In this case, you will need to scale up the workers.


LLM Tags:  #inference, #ml, #modelprediction #kafka 
LLM Tags:  #modelinference #onlinelearning #mlpipeline #prediction
LLM Tags:  #streamprocessing #modelinference
LLM Tags:  #streamprocessing #modelinference #predictiveanalytics #anomaly-detection 
LLM Tags:  #ml #deeplearning #gpu #online-inference
LLM Tags:  #streamprocessing #scalingoutmodelinference #gpudeeplearning