---
title: "PipelineRL: Faster On-policy Reinforcement Learning for Long Sequence Generation"
collection: publications
permalink: /publication/2025-09-23-pipelinerl
date: 2025-09-23
venue: "arXiv preprint arXiv:2509.19128"
paperurl: "https://arxiv.org/abs/2509.19128"
citation: 'Alexandre Piché, Ehsan Kamalloo, Rafael Pardinas, Xiaoyin Chen, Dzmitry Bahdanau. (2025). "PipelineRL: Faster On-policy Reinforcement Learning for Long Sequence Generation." <i>arXiv preprint arXiv:2509.19128</i>.'
---

We present PipelineRL, a fully pipelined on-policy reinforcement learning stack for large language models that keeps accelerators saturated without generating stale, off-policy trajectories. The system overlaps rollout, preference modeling, and policy updates to deliver up to 2× faster convergence on long-context reasoning benchmarks while retaining stability guarantees for PPO-style algorithms.
