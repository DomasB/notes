1. **Definition of LLMs:** LLMs (Large Language Models) are machine learning models trained on extensive text data to understand and generate human language. Notably, OpenAI's GPT-3, with 175 billion parameters, is an example of such a model.

2. **GPU Requirements:** LLMs require GPUs for both training and inference to avoid sluggish performance.

3. **Prompts and In-Context Learning:** LLMs respond to queries (prompts) in natural language. The quality of responses can be enhanced through prompt engineering, where prompts are carefully designed. In-context learning involves providing examples for the LLM to learn from.

4. **Fine Tuning:** Pre-trained LLMs can be downloaded and fine-tuned on private data for specific tasks, yielding improved performance for specialized queries.

5. **Size of LLMs (Parameters):** LLM size is measured by parameters. Larger models, like GPT-4 with 1,700 billion parameters, exhibit unique capabilities. The number of parameters also affects memory usage; for instance, Llama-2-70b with 16-bit precision requires 140 GB memory.

6. **Proprietary LLMs:** Proprietary LLMs, like OpenAI's ChatGPT and GPT-4, are accessed via UI or APIs. They can't be downloaded, and customization is limited. Legal and privacy concerns might restrict their use.

7. **Open-Source LLMs:** Numerous open-source LLMs exist. Llama-2, the most powerful, has 70 billion parameters. They can be fine-tuned for specific tasks using proprietary data. This type of LLM offers control over deployment in data centers or clouds, ensuring data privacy. However, their performance is still somewhat inferior to proprietary LLMs for general language tasks due to their smaller size.