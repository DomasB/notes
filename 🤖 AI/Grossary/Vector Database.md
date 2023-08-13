**What is a vector database in ML?**
------------------------------------

A vector database for machine learning is a database that stores, manages, and provides semantic query support for embeddings (high-dimensional vectors). The semantic queries supported are typically [similarity search](http://www.hopsworks.ai/dictionary/similarity-search), nearest neighbor search, and clustering. Vector databases are available as the following: standalone servers, as a library to embed in an application, or as a feature in an existing database.

‍

**When do I need a vector database?**
-------------------------------------

The most popular applications of vector databases are in AI, where you may want to quickly find similar items (e.g., a matching fashion item in an ecommerce store, or a matching piece of text for use as a prompt input to a large language model). Similarity search can also be used to bridge two modalities. For example, you can take a user’s history and search query (first modality) and match it to the most similar item (product/video/song/etc) in a catalog (second modality). This [two-tower similarity search method](https://www.youtube.com/watch?v=tz6Tg-NCFLU&vl=en) is used for personalized search and recommendation systems.

‍

**Why can I not use my existing database?**
-------------------------------------------

Some databases have added support for both the storage of vectors and vector similarity search. In relational databases, Postgres has added vector database support with [pgvector](https://github.com/pgvector/pgvector). In document databases, [OpenSearch](https://opensearch.org/platform/search/vector-database.html) has had vector database support since 2021 with the kNN plugin, and [ElasticSearch](https://www.elastic.co/what-is/vector-search) added vector database support recently. 

There is a tradeoff to make between using an existing database and a standalone vector database. There are higher operational costs in managing a new system, but  standalone vector databases tend to have wider support for more ANN algorithms than databases that support vector storage and similarity search.

**What are the most popular ANN algorithms used by Vector Databases?**
----------------------------------------------------------------------

When you query a vector database, you enter a vector (array of integers) and you ask to return the N, e.g., N=100, most similar vectors. K-nearest neighbor algorithms are accurate (they find the nearest neighbors) but are too slow to be used in practical systems. Hence, approximate nearest neighbor (ANN) algorithms are used to find the closest neighbors (most similar vectors) to an input vector. Typically they use distance measures to compare vectors, such as L2 (Euclidean) distances or dot products.

Most of the ANN algorithms used in existing vector databases have been written in the last 5 years (it is a fast moving space), and they generally are designed to favor either accuracy (recall) or performance (throughput). The three most popular algorithms are: 

* hierarchical navigable small worlds network (hnsw),
* faiss-ivf,
* scann.

For an open-source benchmark with more details, we refer you to [ANN Benchmarks](https://ann-benchmarks.com/).

‍

**What are the most popular open-source libraries that existing vector databases build on?**
--------------------------------------------------------------------------------------------

[FAISS](https://github.com/facebookresearch/faiss) (Facebook AI Similarity Search) FAISS is an open-source library for efficient similarity search and clustering of dense vectors. [SCANN](https://github.com/google-research/google-research/tree/master/scann) (Scalable Compressed Approximate Nearest Neighbors), developed by Google, is an open-source library for efficient similarity search and approximate nearest neighbor search in high-dimensional vector spaces.  [HNSW library](https://github.com/nmslib/hnswlib) is a fast approximate nearest neighbor search library that is incorporated in many existing vector databases. Some companies have also built their own proprietary libraries, such as [Weaviate](https://ann-benchmarks.com/weaviate.html). 

‍

**How do I evaluate the performance of a vector database?**
-----------------------------------------------------------

You can perform benchmarks on different vector databases and ANN algorithms by using one or more appropriate datasets and distance measures. A good place to start is [ANN Benchmarks](https://ann-benchmarks.com/) that includes a github repository with benchmarks for many vector databases and libraries. The most common benchmarks are:

* write throughput (measured in inserts per second)
* read throughput (measured in queries per second)
* accuracy (measured as a *Recall percentage*)

‍

### **Recall vs Throughput Tradeoffs**

A useful property to evaluate for your requirements in benchmarks is accuracy vs performance for Vector Database, dataset, and ANN algorithm That is, 

* *Recall* (the fraction of true nearest neighbors found, on average over all queries)  
vs
* *Throughput* (the number of queries per second)

Depending on your requirements, you typically need to make a choice to favor an algorithm that has higher Recall or higher throughput. Different ANN algorithms make different tradeoffs in favoring throughput or Recall.

‍

