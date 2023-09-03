In-context learning (ICL) is a specific method of prompt engineering where demonstrations of the task are provided to the model as part of the prompt (in natural language). With ICL, you can use off-the-shelf Large language models (LLMs) without any need for [fine-tuning](https://www.hopsworks.ai/dictionary/fine-tuning-llms).

In-context learning (ICL) learns a new task from a small set of examples presented within the context (the prompt) at inference time. LLMs trained on sufficient data exhibit ICL, even though they are trained only with the objective of next token prediction.  Much of the interest in LLMs is due to the prompting with examples as it enables applications on novel tasks without the need for fine-tuning the LLM.

**How to Engineer Prompts for In-Context Learning**
---------------------------------------------------

Imagine a recipe generation service where you enter what ingredients you have available, and ask the service to generate a recipe for you. One way to implement this service would be with prompts prefixed with example recipes before your text with your available ingredients is finally added to the prompt. For this, you may have thousands of recipes indexed in a [[Vector Database|VectorDB]]. When the query arrives, you use the ingredients to look up the most relevant recipes in the VectorDB, then paste them in at the start of the prompt, and then write the list of available ingredients, and finally, ask your LLM to generate a prompt. This is an example of [retrieval-augmented generation for LLMs](https://www.hopsworks.ai/dictionary/retrieval-augmented-llm).

The above service follows one piece of advice on prompt engineering - **add the most relevant context at the beginning or the end of a prompt to improve the performance of LLMs**. [Researchers have shown](https://arxiv.org/abs/2307.03172) that adding relevant context (i.e., the question of what recipe to generate) in the middle of the prompt leads to worse performance. ^408512

How many example recipes can you add to your prompt? That depends on the context window size for your model. GPT-4 can include ~50 pages of input text (32KB of data), and inference time slows down with larger input prompts.

**Model Size and Context Window Size for ICL**
----------------------------------------------

In-context learning benefits from larger context window sizes, as it makes it easier for ICL with prompts. Similarly, ICL can benefit from LLMs with more parameters. For example, in GPT-4, with a large 32K context window size, [Kosinski](https://arxiv.org/abs/2302.02083) showed that GPT-4 could solve 95% of a set of  40 classic false-belief tasks widely used to test Theory-of-Mind (ToM) in humans. In contrast, GPT-3 has a smaller model (up to 1000 times smaller than GPT-4) with a context window size of 2K, and it could only solve 40% of the false-belief tasks. Similarly, [Levenstein et al in LLaMA 30b](https://arxiv.org/abs/2307.00175), a LLM with only 10s of billions of parameters and a smaller context window size, could not show ability to solve ToM problems. 

**Is In-Context Learning Real?**
--------------------------------

Yes, in [this paper](https://arxiv.org/abs/2306.15063) by Raventós et al, where they study ICL for linear regression and each task corresponds to a different latent regression vector, as pre-training task diversity increases beyond a threshold, transformer models outperform Bayesian estimators on unseen tasks. The implication is that ICL is an emergent phenomenon, as their transformer model moves beyond memorization of the pretraining tasks when there is sufficient diversity and scale in pre-training data. With ICL, transformers can solve new tasks not seen during pre-training.

‍**Why does ICL work?**
-----------------------

Informally, Charles Fyre declares, prompting is mostly subtractive, we delete potential words with each input. ICL is more about [defining the task than about [learning] it](https://twitter.com/full_stack_dl/status/1658497436862791681). However, other researchers disagree and believe the LLMs can learn in a single shot.

[Dileep et al](https://arxiv.org/pdf/2307.01201.pdf) speculate that schema learning and rebinding are key mechanisms - they believe that ICL can be explained as schema learning, and simultaneously inferring the slot-filling and latent template from the prompt. 

As Dileep explains “fast rebinding is a special case of expectation maximization, where the updates are local to surprising tokens found during inference. Most of the content of the latent circuit remains ‘anchored’ to prior training, while some ‘slots’ are filled on the fly with rebinding”. In contrast, [Xie et al](https://arxiv.org/pdf/2111.02080.pdf) speculate that implicit Bayesian inference is the main mechanism at work, although Dileep et al show that this is not enough to solve the “dax test” like novel word usage.

**Zero-Shot vs Few Shot Learning**
----------------------------------

[Reynolds and McDonell](https://arxiv.org/pdf/2102.07350.pdf) describe fews-shot prompts as where a small number of examples of solved tasks are provided as part of the input to the trained LLM. The goal is to make predictions for new classes based on just a few examples of labeled data. 

In zero-shot learning, there is no labeled data available for new classes. Zero-shot learning is when a machine is taught how to learn from data without ever needing to access the data itself.  In zero-shot learning, a LLM is given training data and asked to learn from it.

In general, in current LLMs, a well constructed zero-shot prompt can probably match the performance of providing many examples (for few-shot learning), so zero-shot prompts are typically preferred. Zero-shot learning could be more effective than few-shot learning because it may allow machines to learn from data without being explicitly told how to do so, leading to better generalization from examples. 

‍


#fine-tuning #in-context-learning #vector-database   #context-window #promptengineering #llm #recipes #in-context-learning #llm #transformer #pre-training #diversity #few-shot #zero-shot