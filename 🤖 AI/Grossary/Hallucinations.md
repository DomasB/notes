Hallucinations are responses by LLMs that appear to be correct but are actually false or not based on the input given. Hallucinations can occur when you give a LLM a prompt that is ambiguous or can be interpreted in more than one way or when the LLM has not been trained on enough training data.  
  
**How do I prevent hallucinations?**If you provide more context in your prompts, you limit the possible outcomes, driving the model toward what you are looking for, that is, the LLM will generate more relevant results.

[Zhang et al](https://arxiv.org/pdf/2305.13534.pdf) show how to try to prevent hallucination snowballing, by, as part of a prompt chain, asking the model to first acknowledge a mistake before correcting its output in a subsequent prompt. 

‍

‍**Are hallucinations an inevitable by-product of transformer-based LLMs?**

[Yann LeCun famously claimed](https://twitter.com/ylecun/status/1667218790625468416) that LLMs are auto-regressive models and, as such, hallucinations are an inevitable property of LLMs. Others believe that hallucinations will decrease below human levels as LLMs become larger and are trained on more data.


LLM Tags:  #hallucinationprevention #transformer #promptchain #mistakeacknowledgement
LLM Tags:  #neural-network #hallucination #auto-regression