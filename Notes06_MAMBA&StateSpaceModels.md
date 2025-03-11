## Problem with Transformers
For a given input sequence say $x\in R^{N\times d}$, where N is number of tokens, d is length of token embedding. We transform x into 3 variables - keys ,queries, values eg. $x_k, x_q, x_v \in R^{N\times D}$
Then attention module estimates the relation between a query and all other keys as $softmax(\frac{x_{q} x_k^T}{normalizing\ constant}) x_v$. Here the computation is O(N^2D) so it scales with number of tokens. Inference is slow.
RNNS can do faster inference since they scale linearly with time as they only look at the previous token not all tokens, but they have limited memory so can forget earlier tokens.

### State Space Models
For sequence modeling - represents data as input, output, and state space variables. Minimum number of variables to fully describe the system. 
2 equation describe SSM:
- h'(t) = Ax(t)+Bh(t)
- y(t)= Cx(t)+Dh(t)
h(t) is hidden state representation. Here since input is continuous, SSM is continuous time representation

In text and images the input is discretized tokens or pixels.

So to discretize model use Zero-order hold technique -  hold the value until new value. How long a value is held is decribed by learnable step size $delta$
So the equations for discrete time-steps is
-$h_k = \bar{A}x_{k} + \bar{B}h_{k-1}$
-$ y_k = D h_k$


