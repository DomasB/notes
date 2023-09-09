Prompt engineering involves designing natural language queries (prompts) to produce desired results from a LLM. The prompt is the input text to your LLM, and the response of your LLM is the output. The goal of prompt engineering is to maximize the effectiveness, accuracy, and usefulness of the responses from the LLM. The prompt is often a statement or question that is given in English (or another language) as model input. How a prompt is structured influences the output of the model. For example, a LLM might respond differently to two very similar prompts: "Rewrite the following text to make it half as long" compared to "Summarize the following text, making it half as long".

Prompt engineering has been considered a kind of "programming", where the source code is the natural language prompts.

‍

* **Question answering**
	+ Example prompt: The capital city of Ireland is *\_\_\_\_\_*
* **Fact verification**
	+ Example prompt: Is Dublin the capital city of Ireland? *\_\_\_\_\_*
* **Dialog**
	+ Example prompt: Where should I go to drink the best Guinness? *\_\_\_\_\_*
* **Text summarization**
	+ Example prompt: Please summarize "Love loves to love love" *\_\_\_\_\_*
* **Machine translation**
	+ Example prompt: Translate into Swedish "The sea, the snotgreen sea, the scrotumtightening sea." *\_\_\_\_\_*
* **Source code generation**
	+ Example prompt: Please write a Python program to compute the formula: i² = j² = k² = ijk = -1. *\_\_\_\_\_*
* **Proof generation**
	+ Example prompt: Please provide a proof for the following formula: i² = j² = k² = ijk = -1. *\_\_\_\_\_*
* **Sentiment analysis**
	+ Example prompt: What is the sentiment of this "There is only one thing in the world worse than being talked about, and that is not being talked about"? *\_\_\_\_\_*
* **Reasoning**
	+ Example prompt: What does the author mean by "to live" in this sentence: "To live is the rarest thing in the world. Most people exist, that is all." *\_\_\_\_\_*
* **Data analysis**
	+ Example prompt: Here is a map of Dublin city center [document]. Is there a path to cross Dublin without passing a pub? *\_\_\_\_\_*
* **Instruction models**
	+ Example prompt: Give me directions on how to cross Dublin without passing a pub, starting in Ranelagh triangle and ending at Croke Park. *\_\_\_\_\_*
‍

‍**General Advice for Prompt Engineering**

Prompt engineering can include a wide range of techniques such as:

* rephrase: a reordering or change in the words used can lead to more desirable outputs. For example, "tell me a joke" vs. "make me laugh".
* provide explicit instructions: tell the LLM what to do step by step, to consider the positive and negative aspects of a question, or to adopt a tone before giving an answer.
* specify how the response should be formatted or structured: For example, "give the answer in a single sentence" or "return the answer in JSON format, where the keys are: x, y, z".

‍

**Reduce the need for background knowledge by the LLM**

In [Mishra et al](https://arxiv.org/abs/2109.07830), they show that instead of writing a prompt that requires background knowledge, you should provide patterns that include the expected output. If there are negation statements, change them to instead be assertion statements. 

An example pattern could be as follows:

Raw task*: Follow the instructions to produce output with the given context word. Do <>.  Do <>.  Don’t <>.*   
Input: Context word <>. Expected Output: Long text <> 

Anchoring the model’s behavior: By providing additional context or cues, we can anchor the model's response. For example, a user might anchor the model to act like Shakespeare, or to generate responses as if it were a particular character from a book.

‍

‍**Understand how your LLM performs Tokenization**

When building prompts, you need to consider the tokenizer that should be used for your target LLM. Most LLM tokenizers are not character, sentence, or word-based, but part-of-word based. [For example](https://platform.openai.com/tokenizer), the OpenAI parser parses the string “hello world” as 2 tokens (containing 11 characters), while the string “uryyb jbeyg” is parsed as 6 tokens with 11 characters.

‍

‍**Chain-of-thought Reasoning to Prevent Self-Contradictions**

[Muendler et al](https://arxiv.org/pdf/2305.15852.pdf) show how you can help prevent self-contradictions with chain-of-thought-like prompting (also called self-criticism). This works by identifying self-contradictions in the output and then iteratively make edits to prompts to remove contradictions

‍

‍**Confidence Estimation for Answers**

You can instruct a LLM to refuse to answer unless it is confident in its answer. For example, you can start the prompt: “answer the question as correctly as you can, but if you are not sure of the correct answer, respond with ‘sorry, i do not know the answer to the question.”

‍

‍**Automatic Prompt Generation**

You can enrich the prompt with external knowledge. Retrieval augmented generation techniques (for retrieval-based LLMs) enable you to retrieve relevant information from a feature store or vector database or an external API at inference time and provide that context as part of the prompt. For example, instead of looking up weather information in your browser and pasting it as your prompt in a text window, you could write a program in LangChain that uses a weather api (like OpenMeteo) to retrieve the weather forecast and include it in your prompt.

‍

‍**Front-load or Back-load Prompts - the Middle is just Filler**

In “Lost in the Middle: How Language Models Use Long Contexts”, [Liu et al](https://arxiv.org/abs/2307.03172) find that adding relevant context at the beginning or the end of a prompt improves the performance of LLMs, compared to including the relevant context in the middle of the prompt.

‍

‍**Self-correcting Responses using a 2nd Model**

You could, for example, use GPT-4 to generate some data from some input, followed up by a GPT-3.5 call to verify the output against the input, thus indirectly verifying the content. Sometimes you can feed the GPT-3.5 output straight back into GPT-4 again, enabling the prompts to self-correct the output.

‍

‍**Ensembling Responses**

In the same way as using a 2nd model to validate the output of the 1st model, it is also possible to provide many versions of a prompt, receive many answers, and allow the user to use the wisdom of the crowd to validate the response using the many different answers.

‍

‍**Natural Language versus Structured Text Responses**

LLMs can work better when responding with structured text - such as JSON or a Python program - than outputting natural language, where they are prone to hallucinations. 

‍

‍**Image Prompting**

LLMs are for natural language, but similar foundational models for image classification/segmentation, trained with self-supervision, are appearing, such as Meta's AI [Segment Anything](https://segment-anything.com/). Segment anything provides a prompting-based model for creating masks for objects in images. It can be prompted in several ways, such as selecting a few "positive" and "negative" points, to create a mask that includes all the positive points and excludes all the negative points.


LLM Tags:  #promptengineering, #questionanswering, #factverification
LLM Tags:  #writing, #ml, #web, #hobbies, #maths
LLM Tags:  #promptengineering #instructionmodels #generaladvice
LLM Tags:  #languagemodeltokenization #nlp #nlp
LLM Tags:  #prompts #tokenizer #selfcriticism

LLM Tags:  #context #selfcorrecting #ensembling
LLM Tags:  #image-prompting #llm #nlp