**What is a streaming feature pipeline?**
-----------------------------------------

**‍**A streaming feature pipeline is a program that continuously processes incoming data in real-time, extracting and computing features and writing those features to a [feature store](https://www.hopsworks.ai/dictionary/feature-store).

‍**When should you use a streaming feature pipeline?**
------------------------------------------------------

**‍**If you need very fresh [precomputed features](http://www.hopsworks.ai/dictionary/precomputed-features) in your feature store, a streaming feature pipeline (written in a per-event stream processing framework, such as Apache Flink) will create features from events in your real-time message bus that are only a few seconds old.


LLM Tags:  #streamingpipeline #realtimestreamprocessing #feature-store