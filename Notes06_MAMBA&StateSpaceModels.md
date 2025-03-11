## Problem with Transformers
For a given input sequence say $x\in R^{N\times d}$, where N is number of tokens, d is length of token embedding. We transform x into 3 variables - keys ,queries, values eg. $x_k, x_q, x_v \in R^{N\times D}$
Then attention module estimates the relation between a query and all other keys as $softmax\frac{x_{q} x_k.T}{normalizing\ constant} x_v$. Here the computation is O(N^2D)
### State Space Models
For sequence modeling - represents data as input, output, and state space variables.
