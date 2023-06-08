# Prompt enginnering
In this tutorial, we will study prompt engineering techniques. Inspired by recent progresses on foundation models, there is emerging a new interactive approach named prompt between large language models (LLM) and users. With it, we can just tell our needs (questions and examples) to LLMs and wait their answers. 

To learn this technique, we start to explain its concept from HCI's perspective. Second, we will summary common tips for "how to use prompt". Third, we pay more attention to "how to learn prompt". In the end, we will dive into details of visual prompts (a new interesting interactive approach to vision models).  

_Although prompt enginnering is a very hot topic for LLM, most of them seem like tricks for me because the rationale behind them is not clear._

## Content
- [Prompt enginnering](#prompt-enginnering)
  - [Content](#content)
  - [What is prompt](#what-is-prompt)
  - [How to use prompt](#how-to-use-prompt)
  - [How to learn prompt](#how-to-learn-prompt)
  - [Visual prompt](#visual-prompt)
  - [Augmented Language Models](#augmented-language-models)
  - [References](#references)

## What is prompt
Prompt is a new interactive approach between LLM and users. It targets to improve answers of conversation-based AI via providing clear task instructions, more and similar examples.
```markdown
# example:

## Task instruction: 
Please analysis the sentiment of the following sentences.

## Example:
Text: (lawrence bounces) all over the stage, dancing, running, sweating, mopping his face and generally displaying the wacky talent that brought him fame in the first place.
Sentiment: positive.

Text: despite all evidence to the contrary, this clunker has somehow managed to pose as an actual feature movie, the kind that charges full admission and gets hyped on tv and purports to amuse small children and ostensible adults.
Sentiment: negative.

Text: for the first time in years, de niro digs deep emotionally, perhaps because he's been stirred by the powerful work of his co-stars.
Sentiment: postive.

## Question:
Text: i'll bet the video game is a lot more fun than the film.
Sentiment: 
```   
## How to use prompt
In sum, there are 5 rules for prompt usage: 
1. Few-shot prompts are likely better. More context are provided, better results are returned.
   ```markdown
   ## zero-shot prompt
   It doesn't work!:
   _Answer_: I understand that you are frustrated, but without additional information about what specific product or service you are referring to and what issues you are experiencing, it is difficult for me to provide meaningful assistance. If you could please provide more details about the problem, I would be happy to try and help you find a solution.
   ## few-shot prompt
   Great product, 10/10: positive
   Didn't work very well: negative
   Super helpful, worth it: positive
   It doesnt work!:
   _Answer_: negative
   ```
2. Give your model a certain role and audience.
   ```bash
   # Prompt
   You are the best computer scientist of the world. Please explain "primitive" to new graduates.
   #Anwer from GPT-4:
   Thank you for your kind words! In computer science, a primitive is a fundamental data type that cannot be broken down into a more simple data type1. For example, an integer is a primitive data type, while an array, which can store multiple data types, is not1. Some programming languages support more data types than others and not all languages implement data types the same way1. I hope this helps. Is there anything else I can help you with?
   ```
3. Chain-of-thought (CoT) for reasoning tasks. 
   ```markdown
   # Prompt for CoT
   Instruction: Please answer the following math problem.
   Question: 10*23-34=?
   Let's think step-by-step.
   ```
   _Note: CoT only yields performance gains when used with models of ~100B parameters._
4. Clear and specific prompts (use specific symbols, formatted outputs, add conditions).
   ```bash
   # Prompt for specific symbols
   Please proofread the following sentence "In this tutorial, we will study prompt engineering techniques. Inspired by recent progresses on foundation models, there is emerging a new interactive approach named prompt between large language models (LLM) and users. With it, we can just tell our needs (questions and examples) to LLMs and wait their answers."
   # Prompt for formatted outputs
   Please summary recent efforts on efficient vision transformers and return results in a table-like structure.
   # Prompt for adding conditions
   Do you know Jason Lu? Say "I don't know" if you do not know the answer.
   ``` 
5. Know the model temperature (t=0 for determined tasks and t>0 for generation tasks). 


## How to learn prompt
1. AutoPrompt, EMNLP'20
   1. Paper: https://aclanthology.org/2020.emnlp-main.346/
   2. Summary: To reduce mannual efforts on prompt design, authors proposed a new approach to generate prompts for an given input text ($x_{inp}$) automatically. Thus, they call it autoprompt. Specificially, autoprompt will first construct prompt templates ($\lambda$) for all tasks and then search the optimal trigger tokens ($x_{trig}$) to complete the prompt.
   3. Question: 
      - How to construct templates for all tasks? large manual efforts? Can we use it for new tasks?
      - How to search trigger token efficiently?  
2. Prefix-Tuning
3. P-tuning
4. Prompt-Tuning
## Visual prompt
Visual prompt is like a click on the visual data and is not intuitive as same as text prompt. The wide-used visual prompts are points, bounding boxes and area. Recent works show that prompt tuning is also works on visual domains. xxx
## Augmented Language Models
1. Retrieval
2. Programming Language
3. Extenal API

## References
1. [大模型时代的科研基础之：Prompt Engineering (MSRA)](https://www.bilibili.com/video/BV13P41197c6/?spm_id_from=333.337.search-card.all.click)
2. [Lilian Weng's blog on prompt engineering (OpenAI)](https://lilianweng.github.io/posts/2023-03-15-prompt-engineering/)
3. [Pre-train, Prompt, and Predict: A Systematic Survey of Prompting Methods in Natural Language Processing (CMU)](https://arxiv.org/abs/2107.13586)
4. [Andrew Ng and OpenAI's prompt course (focus on how to use prompt)](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/)
5. https://learnprompting.org/docs/intro
6. https://zhuanlan.zhihu.com/p/366771566
7. [OpenAI Cookbook](https://github.com/openai/openai-cookbook) 
   1. [Guide: How to work with large language models?](https://github.com/openai/openai-cookbook/blob/main/how_to_work_with_large_language_models.md)
   2. [Guide: Technique to improve reliability (chain-of-thought for complex problems)](https://github.com/openai/openai-cookbook/blob/main/techniques_to_improve_reliability.md)
8. [OpenAI Examples (including typical prompts for many popular tasks, the best reference for me)](https://platform.openai.com/examples)
9. [awesome chatgpt prompts (different roles for LLM)](https://github.com/f/awesome-chatgpt-prompts#prompts)