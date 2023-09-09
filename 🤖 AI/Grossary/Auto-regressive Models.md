---
tags:
  - "#time-series #auto-regression #linearregression #languagemodeling #neural-network #ml #reinforcement-learning"
---
An autoregressive (AR) model forecasts future behavior based on past behavior data.

AR models are useful for time-series predictions and for language modeling. In both cases, there is a correlation between the preceding and succeeding values in a time-series.

In many time-series datasets, past values influence the current values. This is true for both stock market prices to words in a sentence or a longer piece of text. Autoregressive modeling uses only past data to predict future behavior. Linear regression is carried out on the data from the current series based on one or more past values of the same series.

AR models are linear regression models where the outcome variable (Y) at some point of time is directly related to the predictor variable (X). In AR models, Y depends on X and previous values for Y, which is different from simple linear regression.

## Are [[LLMs - Large Language Models|LLMs]] Autoregressive models?
![[Pasted image 20230903213537.png]]
Yann LeCun famously claimed that LLMs are auto-regressive models and, as such, [[hallucinations]] are an inevitable property of LLMs. AR models are a way to parametrize probability distributions over multidimensional vectors (or sequences of tokens, as in LLMs). However, LLMs are also fine-tuned with Reinforcement Learning from Human Feedback (RLHF) - they are not trained solely for auto-regressive performance. And it is [believed by some](https://arxiv.org/abs/2304.11490) that RLHF trains LLMs to track truth (leading to the emergence of mental states). 

