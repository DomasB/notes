The context window of LLMs is the number of tokens the model can take as input when generating responses. For example, in GPT-3 the context window size is 2K (2000) and in GPT-4 it is a larger 32K. There is a trend and demand for increasingly larger context window sizes in LLMs. Larger context windows improve LLM performance and their usefulness across various applications.

‍

**Why is a large context window size important?**

Larger context window sizes increase the ability to perform in-context learning in prompts. That is, you can provide more examples and/or larger examples as prompt inputs, enabling the LLM to give you a better answer. For example, a LLM could take an entire document as input, helping with comprehension of the full scope of an article. This ability enables LLM to produce more contextually relevant responses by leveraging a more comprehensive understanding of the input. 

Another example would be providing the LLM with context information that was not available at the time the LLM was trained - if a user asked GPT-4 “who won the world cup in 2022?”, it doesn’t know the answer (it’s cut-off was before that date). However, a client can use the query to find a relevant document about the 2022 world cup (e.g., using similarity search in a vector database) and add that document to the prompt (e.g., it might be the wikipedia article on the 2022 world cup). The LLM can now answer the query (“Argentina” is the correct answer) as the answer was in the document included in the prompt.

 

**Challenges in increasing the context window size**

The costs increase of larger context windows appear to increase quadratically as the number of tokens is increased, e.g., going from 2K to 4K with GPT-3 to GPT-3.5 was not twice as computationally expensive, but 4x the computationally cost. [Research is ongoing on decreasing the cost](https://hazyresearch.stanford.edu/blog/2023-03-27-long-learning). 

Another challenge is that, based on [Liu et al](https://arxiv.org/abs/2307.03172), it appears that adding relevant context at the beginning or the end of a prompt improves the performance of LLMs, compared to including the relevant context in the middle of the prompt. It is unclear how this observation will affect larger context windows.


#context-window #llm #prompts #comprehension #nlp 