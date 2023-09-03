Retrieval-augmented generation (RAG) for large language models (LLMs) aims to improve prediction quality by using an external datastore at inference time to build a richer prompt that includes some combination of input context, history, and recent/relevant knowledge. [RAG LLMs can outperform LLMs without retrieval by a large margin with much fewer parameters](https://acl2023-retrieval-lm.github.io/), and they can update their knowledge by replacing their retrieval corpora, and provide citations for users to easily verify and evaluate the predictions.

The most common systems used to provide external data for retrieval-augmented generationLLMs are [vector databases](https://python.langchain.com/docs/modules/chains/additional/vector_db_text_generation) and [feature stores](https://blog.langchain.dev/feature-stores-and-llms/). 

RAG for LLMs works because of the ability of LLMs to perform [in-context learning](https://www.hopsworks.ai/dictionary/in-context-learning-icl).

‍**Why is there a need for RAG LLMs?**‍
---------------------------------------

Pre-trained LLMs (foundation models) do not learn over time, often hallucinate, and may leak private data from the training corpus. To overcome these limitations, there has been growing interest in retrieval-augmented generation which incorporate a vector database and/or feature store with their LLM to provide context to prompts.

‍

What data systems are used for RAG LLMs?
----------------------------------------

Popular serverless vector databases and feature stores are Pinecone and [Hopsworks](https://app.hopsworks.ai) that provide time-unlimited free tiers. Chroma is often used as an embedded vector database. 


LLM Tags:  #llm, #retrievalaugmentedgeneration, #llm
LLM Tags:  #RAGLLMs, #context, #vector-database