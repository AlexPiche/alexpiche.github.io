---
title: 'Blog Post number 1'
date: 2012-08-14
permalink: /posts/2024/07/mistral-shut-up/
tags:
  - LLMs
  - Factuality
  - RL
---

The model then predicts a probability based on the consistency between sources, which highly correlates with its own certainty for a given claim.

## Synthetic data generation is expensive

Part of the argument for synthetically generating data is that writing them by hand would be tricky. It would require us to know what the model knows and what it does not know, which would then be used to write biographies that only include information that the model knows. Otherwise, we would be training the model to learn specific facts instead of learning the general principle of shutting up when it does not know (see Yoav Goldberg blog post link at the bottom on exactly this). It is also arguably much cheaper in human time and scalable to generate synthetic data than to write them manually. But to the annoyance of my generous and patient colleagues, this project took a scandalous amount of computation (thank you guys!). I am too ashamed to admit how many A100 hours I used, but let's say I would know how to use Zuck's 350,000 H100s.

So why is it so expensive? Basically, instead of generating a single biography for each query, I ended up generating 48 possible ones, breaking each of them into individual sentences, then each sentence into roughly 15 atomic claims which need to be evaluated on how consistent they are with all the other answers. To ensure reliability, every step in this process is packed with in-context examples making the synthetic data generation even more expensive. Long story short, instead of using ~10 tokens of input to get a biography, I ended up using 1.5M tokens.

## Making search wider is so 2017, making search iterative is where it's at

Surprisingly, naively generating more answers in parallel did not help much. And I am not one to let good A100's cycles be wasted on bad computation. On the other hand, what has been working better is to iteratively write biographies. You get the model to write 16 samples, you extract the most likely claims and add them to the prompt for the next generation of 16 biographies. I like to think about this process as self-reflection, where the model learns about its internal knowledge and is able to improve its performance following this reflection.
