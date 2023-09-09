**What is a streaming inference pipeline?**
-------------------------------------------

**‍**A streaming inference pipeline is a streaming application that makes real-time, non-interactive predictions triggered by the arrival of an event and outputs predictions to some sink (such as the event bus).

![architecture graph](https://assets.website-files.com/618399cd49d125734c8dec95/6436acd2886336d065a3aaa3_5VnvT-MjNbnhofO7bRk4_Dt81nOkKz5L8X1pw-fGsitxqJ-797zfzAD51UCZT3UFs6HyGV-XIA-lBkC5Q2Le_5K-WO8dsP5poobpkqnJHWLrORByYEfdEMD89PiXcg1iFzF6qdBiuzb1QbZsd3fnlg.png)‍**When should I use a streaming inference pipeline?**
------------------------------------------------------

**‍**If you have a non-interactive system that needs to make predictions in near real-time, then a streaming inference pipeline might be the best choice. For example, an IoT device might stream measurements to a Kafka topic, from where a streaming inference pipeline makes continual predictions about the IoT measurements and writes the results to different Kafka topic, from where an alerting component consumes events and takes actions if needed. In contrast, an [online inference pipeline](https://www.hopsworks.ai/dictionary/online-inference-pipeline) is a request/response architecture for interactive systems.


LLM Tags:  #streaming, #inference-pipeline
LLM Tags:  #streaming #inference #IoT #kafka 