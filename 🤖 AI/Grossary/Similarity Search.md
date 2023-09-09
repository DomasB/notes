**What is similarity search for vector embeddings?**
----------------------------------------------------

[[Embedding|Vector embeddings]] (or embeddings or vectors) are compressed representations of data such as text, images, and audio. Vector similarity search (or similarity search for embeddings) finds the “top K” most similar vectors to a query vector in a [[Vector Database|vector database]]. In order to be able to search for items in a vector database, you need to first insert vector embeddings for items, then the items will be indexed by the vector database.

**What is similarity search used for?**
---------------------------------------

Similarity search is used to build:

* **single modality similarity search** where a user supplies an Image/video/audio that is run through an embedding model to create a vector with whicha similarity search is performed on the vector database to find similar images/video/audio. Here the similarity search is for the same modality (e.g., use an image to find images);
* **Two-modality similarity search** where a user enters a search string (a query) or the last video they watched, and we augment that with the user’s history and preferences and context information like what’s trending and with all that data, we use an embedding model to create a vector. We then look up items (a different modality from the user search) in a vector database. Two-modality similarity search is enabled by training models using the two-tower model, where you have samples where a user query (and its embedding) is linked to an item the user clicked on (or negatively - the user didn’t click on it).
* **Prompt engineering for generative AI tools (LLMs)** where you take a user’s query and retrieve similar text passages stored in a vector database, and add those text passages as “prompts” to your query. This will better instruct the [[LLMs - Large Language Models|LLM]] how to generate a more relevant, informed response. For example, if you retrieve recent information from your vector database (not available when the LLM aws trained), the LLM can give you a correct answer, even though it didn’t know that data at the time of training;
* **Anomaly detection** where you supply a vector and search for outliers in the vector database (outliers are very different from all other vectors in the vector DB);
* **Deduplication and record matching** where similarity search can find very similar (but maybe not 100% identical) items. This can be useful for detecting plagiarism, for example.

**What indexing algorithms are used for similarity search?**
------------------------------------------------------------

[Approximate k-nearest neighbors](https://ignite.apache.org/docs/latest/machine-learning/binary-classification/ann#:~:text=An%20approximate%20nearest%20neighbor%20search,good%20as%20the%20exact%20one.) (ANN) is commonly used to return the k nearest vectors - exact matching is too computationally expensive. Approximate approaches find good enough matches without exhaustively checking all the possible matches. Your ANN algorithms should be configurable to enable you to tradeoff recall (percentage of results with true top-k nearest neighbors), latency, throughput, and vector insertion time.

Popular approximate approaches include:

* **HNSW** ([Hierarchical Navigable Small Worlds](https://www.pinecone.io/learn/hnsw/#:~:text=Hierarchical%20Navigable%20Small%20World%20(HNSW,search%20speeds%20and%20fantastic%20recall.)) is a proximity graph indexing and retrieval algorithm. Upper layers contain only "long connections," while lower layers have only "short connections" between vectors in the database. HNSW searches through the graph starting from the uppermost layer moving to the lowest layer, greedily traversing the graph with the longest inter-vector connections for the vector closest to our query vector - until at algorithm termination, you are left with the closest neighbors;
* **FAISS** ([Facebook AI Similarity Search](https://github.com/facebookresearch/faiss)) enables vectors to be compared with L2 (Euclidean) distances or dot products and uses quantization and binary indexes to reduce search latency at the cost of recall. Compared to HNSW, it does not build a complex indexing structure, enabling it to be optimized for memory usage and speed;
* ‍**SCANN** ([Scalable Approximate Nearest Neighbors](https://github.com/google-research/google-research/tree/master/scann)) uses search space pruning and quantization for Maximum Inner Product Search and also supports other distance functions such as Euclidean distance.

#embedding #data-base  #similarity-search #modality #vectormodel
LLM Tags: #anomaly-detection #deduplication
LLM Tags:  #ml 
LLM Tags:  #graph #proximitygraphs #hierarchicalnetworks #neighborsearch
LLM Tags:  #ml, #faiss, #l2distance