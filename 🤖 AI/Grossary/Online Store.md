**What is an online store?**
----------------------------

**‍**The online store is a row-oriented database or key-value store that provides low-latency lookups for precomputed [feature values](http://www.hopsworks.ai/dictionary/feature-value) using one or more [entity](http://www.hopsworks.ai/dictionary/entity) IDs (or primary keys). The online store enables online inference pipelines (for real-time or near-[real-time machine learning](https://www.hopsworks.ai/dictionary/real-time-machine-learning) systems) to retrieve precomputed features for inference. 

**What are the requirements of an online store?**
-------------------------------------------------

1. **Low latency**: One of the primary requirements of an online store is to provide low-latency lookups for features.
2. **Low latency batch lookups**:  Personalized search/recommendations at scale are commonly based on a [retrieval/ranking architecture](https://www.youtube.com/watch?v=9vBRjGgdyTY) that requires looking up in a single batch the features for 100-250 candidates in parallel. Client SLAs typically have a p99 of 50ms for performing the batch lookup.
3. **High availability**: The online store should be highly available to ensure that [precomputed features](http://www.hopsworks.ai/dictionary/precomputed-features) can be retrieved at any time without interruptions or downtime.
4. **High throughput**: In addition to low latency, the online store should be able to handle a large number of concurrent requests. It must be capable of serving features to many clients simultaneously without compromising client SLAs.
5. **Scalability**: The online store should scale horizontally to handle increasing data volumes and workloads to accommodate the growth of the [feature store](https://www.hopsworks.ai/dictionary/feature-store). This involves being able to add more resources, such as nodes or shards, to the store without downtime or any effects on its performance or availability.
6. **Manageability and monitoring**: An online store should be easy to manage and monitor, offering tools and interfaces that allow administrators to monitor performance, identify issues, and manage resources effectively. This helps ensure that the online store operates smoothly and maintains the desired level of performance and availability.
