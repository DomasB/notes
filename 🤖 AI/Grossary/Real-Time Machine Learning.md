**What is real-time machine learning?**
---------------------------------------

**‍**Real-time ML reference to [[ML]] systems where decisions or predictions must be produced with minimal, predictable latency. Real-time ML systems may need very [fresh features](https://www.hopsworks.ai/dictionary/feature-freshness), which can be [on-demand features](https://www.hopsworks.ai/dictionary/on-demand-features) or [precomputed features](http://www.hopsworks.ai/dictionary/precomputed-features) created by a [streaming feature pipeline](https://www.hopsworks.ai/dictionary/streaming-feature-pipeline). Batch features may be used if the model is not sensitive to stale [feature values](http://www.hopsworks.ai/dictionary/feature-value). Real-time ML systems have either:

* [**online inference pipelines**](https://www.hopsworks.ai/dictionary/online-inference-pipeline), where an interactive application expects a prediction response to its request within some bounded time period, e.g., a 50ms SLA, or
* **streaming inference pipelines**, where a non-interactive system sends prediction requests to an event bus and gets responses created by a streaming inference pipeline, e.g., running in Apache Flink or Spark Streaming.

LLM Tags:  #real-timeml, #minimallatency, #freshfeatures, #on-demand-features, #precomputedfeatures, #streamingpipeline, #feature 
LLM Tags:  #inference #pipeline #online #streaming