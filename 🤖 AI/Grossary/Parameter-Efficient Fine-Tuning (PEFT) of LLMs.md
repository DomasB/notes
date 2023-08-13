Parameter-Efficient Fine-Tuning (PEFT) enables you to fine-tune a small subset of parameters in a pretrained LLM. The main idea is that you freeze the parameters of a pre-trained LLM, add some new parameters, and fine-tune the new parameters on a new (small) training dataset. Typically, the new training data is specialized for the new task you want to fine-tune your LLM for (e.g., for the [clinical domain](https://arxiv.org/abs/2307.03042)).

‍

**What are examples of PEFT techniques?**
-----------------------------------------

[Adapters](https://magazine.sebastianraschka.com/p/finetuning-llms-with-adapters#:~:text=The%20idea%20of%20parameter%2Defficient,the%20pretrained%20LLM%20remain%20frozen.) add tunable layers to the various transformer blocks of an LLM. [Prefix tuning](https://magazine.sebastianraschka.com/p/understanding-parameter-efficient) adds trainable tensors to each transformer block.

‍

**Why is Parameter-Efficient Fine-Tuning important?**
-----------------------------------------------------

Fine-tuning a Large-Language Model (LLMs) has traditionally required retraining its entire set of parameters. However, with even open-source models, such as Llama-2-70b requiring 140GB of GPU memory, this approach is computationally expensive. PEFT enables you to fine-tune a LLM with less resources.

‍

