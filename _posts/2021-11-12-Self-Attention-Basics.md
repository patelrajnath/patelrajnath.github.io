---
layout: post
title: Transformer Model - Self Attention - Implementation with In-Depth Details
---

## Implementation
Following is the basic implementation of Self-Attention using Pytorch. 
The main goal of this implementation is to make it easier to understand that how the 
attention score is computed and is used on values to generate the final output. 
The optimized implementation of multiheaded-attention with einsum() will follow in next one.

<script src="https://gist.github.com/makeesyai/e36430f95cabca165a384fa77519d398.js"></script>

Now, we'll try to understand the above code in details and see which part implements what.

## Five steps of implementation
We can split the above implementation into following five steps-
1. *Create Query, Key, and Value using input vectors.*
2. *Compute attention scores using Query and Key (transpose).*
3. *Convert attention scores to probability distribution using SoftMax.*
4. *Compute weighted values by multiplying attention scores to corresponding values.*

<script src="https://gist.github.com/makeesyai/2591c16cb2376b841bf692cf7c3368a2.js"></script>

* *Add-up the weighted values, computed using the scores of a particular query.*

<script src="https://gist.github.com/makeesyai/093cd3af7f653b62d839d2dddb3698b6.js"></script>

## Implementation Details
Imports and Class initialization.

<script src="https://gist.github.com/makeesyai/adc7743ed44b6da5fd222eff151cfbaa.js"></script>

In the above __init__() method, the **emb_dim** is the embedding dimension of the input at 
each position say word-embeddings in a sentence. 
And the **model_dim** is the dimensionality of the query and Key and Value weight matrices. 
To make the output predictable we have updated weights in the Linear layers with predefined 
tensors.

