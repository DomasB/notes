**What is an online inference pipeline?**
-----------------------------------------

An online inference pipeline is a program that runs in a [[Feature|model deployment](https://www.hopsworks.ai/dictionary/model-deployment) and returns predictions to a client using a model, downloaded and cached from a [model registry](https://www.hopsworks.ai/dictionary/model-registry), and [features]] that are either on-demand or precomputed and retrieved from the [feature store](https://www.hopsworks.ai/dictionary/feature-store).

**What are the key steps in an online inference pipeline?**
-----------------------------------------------------------

An online application sends a prediction request to the model deployment that contains an [inference pipeline](https://www.hopsworks.ai/dictionary/inference-pipeline) that processes the input request, computes any [on-demand features](https://www.hopsworks.ai/dictionary/on-demand-features), retrieves any precomputed features from a feature store, applies any model-dependent transformations to the on-demand and [precomputed features](http://www.hopsworks.ai/dictionary/precomputed-features) and builds a [feature vector](https://www.hopsworks.ai/dictionary/feature-vector) from them, before making a prediction on the model with that feature vector, and finally post-processes the prediction before it sends the results back to the client application.

![architecture graph](https://assets.website-files.com/618399cd49d125734c8dec95/6436a6a3eec4f7e18b8815e4_Z_f7JmXO7IkqoA7J3I8R-RTeiGE33RYmXFzhxe2Se3N10IA0hm2VN0Xc8EzTTTAUojNlnJJZK0Khv2KnryJuDX3QQUvg-5vIjgvnJOykDkDa5jCYm4HaACcDYI4Gu6shCCKs0f9mpGpPV-Oz8MwA_Q.png)
LLM Tags:  #on-lineinference, #modeldeployment, #registry, #feature, #ondemand, #precomputed
LLM Tags:  #inferencepipeline #on-demand-features #precomputedfeatures #feature-store #transformation #predictionrequest
LLM Tags:  #architecture, #graph