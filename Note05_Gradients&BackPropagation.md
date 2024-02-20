### Gradients
For a 3 layer NN: with input $X_i\in R^{N\times P}$ the output of first, second, and third layer are $a_{1i},a_{2i},a_{3i}$ respectively. If loss over a  mini-batch $X_i, i=1,..,m$ is defined as $L=\sum_i ||y_i-a_{3i}||_2$.
The gradients of the L wrt to each layers' weights i.e. $W1,W2,W3$ would need to be computed for SGD since $W^{t+1} = W^{t}-\eta\frac{\delta {L}}{\delta{W^{t}} }$
to find the optimal set of weights.
Due to chain rule, the deeper the network is, during backpropagation more gradients from deeper layers will be multiplied with the current layers gradients. So if the gradients were small to begin with as the networks gets deeper and deeper the smaller the gradiesnts become for the early layers therefore affecting model convergence since these weights would not be updated properly. This is the vanishing gradient problem. In the alternative case, when gradients are large, this would lead to gradiet explosion.

