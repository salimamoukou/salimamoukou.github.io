# Abstract

Test-time scaling improves large language models’ (LLMs) performance by allocating more compute budget during inference. To achieve this, existing methods often
require intricate modifications to prompting and sampling strategies. In this work,
we introduce representation consistency (RC), a test-time scaling method for aggregating answers drawn from multiple candidate responses of an LLM regardless
of how they were generated, including variations in prompt phrasing and sampling
strategy. RC enhances answer aggregation by not only considering the number of
occurrences of each answer in the candidate response set, but also the consistency
of the model’s internal activations while generating the set of responses leading
to each answer. These activations can be either dense (raw model activations) or
sparse (encoded via pretrained sparse autoencoders). Our rationale is that if the
model’s representations of multiple responses converging on the same answer are
highly variable, this answer is more likely to be the result of incoherent reasoning
and should be down-weighted during aggregation. Importantly, our method only
uses cached activations and lightweight similarity computations and requires no
additional model queries. Through experiments with four open-source LLMs and
four reasoning datasets, we validate the effectiveness of RC for improving task
performance during inference, with consistent accuracy improvements (up to 4%)
over strong test-time scaling baselines. We also show that consistency in the sparse
activation signals aligns well with the common notion of coherent reasoning.

[Open paper](https://arxiv.org/pdf/2506.21590)

