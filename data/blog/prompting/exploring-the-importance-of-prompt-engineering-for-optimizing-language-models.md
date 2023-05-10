---
title: Exploring the Importance of Prompt Engineering for Optimizing Language Models
date: '2023-05-10'
tags: ['chatgpt', 'prompting', 'llm']
draft: false
summary: ' The article explains how to design and optimize prompts for language models, which guide the model and can be used for tasks like product or conversational AI. Rules of thumb are given, and examples are provided for extracting data or generating specific content. Fine-tuning can improve model performance, and being specific and concise in prompts is important.
'
---

## How Prompt Engineering Works

💡 Note: Prompt engineering plays a crucial role in the optimization and design of prompts for language models, which is a key aspect of natural language processing and language generation. The format of prompts serves as a guide for language models and can be utilized for various tasks such as conversational AI or product-related tasks. Although there are dependable prompt formats, it is highly recommended to explore new formats as well.

### 👍 Rules of thumb and Examples

**Rule #1** - Instructions at beginning and `###` or `"""` to separate instructions or context <br/>
❌ Rewrite the text below in more engaging language.

```python
(Your Input Here)
```

✔️ Rewrite the text below in more engaging language.

```python
Text: """
(Your Input Here)
"""
```

**Rule #2** - Be specific and detailed about the desired context, outcome, length, format, and style.<br/>
❌ Write a short story for kids<br/>
✔️ Write a funny soccer story for kids that teaches the kid that persistence is key for success in the style of Rowling.

**Rule #3** - Give examples of desired output format<br/>
❌ Bad Example

```python
   Extract house pricing data from the following text
   Text: """
      (Your text containing pricing data)
   """
```

✔️Good example

```python
   Extract house pricing data from the following text.
      Desired format: """
      House 1| $1,000,000 | 100 sqm
      House 2| $   500,000 |   90 sqm
      ... (and so on)
      """
      Text: """
      (Your text containing pricing data)
      """
```

**Rule #4** - First try without examples, then try giving some examples
❌ Extract brand names from the text below.

```python
   Text: (Your text here)
   Brand names:
```

✔️ Extract brand names from the text below.

```python
   Text 1: Finxter and YouTube are tech companies. Google is too.
   Brand names 2: Finxter, Youtube, Google
   ###

   Text 2: If you like tech, you'll love Finxter!
   Brand names 2: Finxter
   ###

   Text 3: (your text here)
   Brand names 3:
   ###
```

**Rule #5** - Fine-tune if Rule #4 doesn't work<br/>
Fine-tuning improves model performance by training on more examples, resulting in higher quality results, token savings, and lower latency requests.<br/>
ChatGPT can intuitively generate plausible completions from few examples, known as few shot learning
Fine tuning achieve better results on various tasks withour requiring examples in the prompt, saving costs and enabling lower latency requests.

Example Training Data

```python
("prompt": "<input>","completion": "<ideal output>")
("prompt": "<input>","completion": "<ideal output>")
("prompt": "<input>","completion": "<ideal output>")
...
```

**Rule #6** - Be specific. Omit needless words.<br/>
❌ ChatGPT, write a sales page for my company selling sand in
the desert, please write only few sentences, nothing long and complex. <br/>

✔️ Write a 5-sentence sales page, sell sand in the desert.

**Rule #7** - Use leading words to nudge the model toward a pattern <br/>
❌ Write a Python function that plot my net worth over 10 years for
different inputs on the initial investment and a given RoI <br/>

✔️ Good Example

```python
# Python function that plots net worth over 10
# years for different inputs on the initial
# investment and a given RoI

import matplotlib

def plot_net_worth(init, roi):
```

🤖 **Bonus Prompt**: Let ChatGPT design the Optimal Prompt <br/>

```python
You are a robot for creating prompts.
You need to gather information about the user's goals, examples of preferred output and
any other relevant contextual information.
Prompt should contain the necessary information provided to you.
Ask the user more questions until you are sure you can create an optimal prompt.
Your answer should be clearly formatted and optimized for chatGPT interactions.
Be sure to start by asking the user about the goals, desired outcome, and any
additional information you may need
```
