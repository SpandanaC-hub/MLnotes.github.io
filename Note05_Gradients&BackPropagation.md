### Gradients
For a 3 layer NN: with input $X_i\in R^{N\times P}$ the output of first, second, and third layer are $a_{1i},a_{2i},a_{3i}$ respectively. If loss over a  mini-batch $X_i, i=1,..,m$ is defined as $L=\sum_i ||y_i-a_{3i}||_2$.
The gradients of the L wrt to each layers' weights i.e. $W1,W2,W3$ would need to be computed for SGD since $W^{t+1} = W^{t}-\eta\frac{\delta {L}}{\delta{W^{t}} }$
to find the optimal set of weights.
Due to chain rule, the deeper the network is, during backpropagation more gradients from deeper layers will be multiplied with the current layers gradients. So if the gradients were small to begin with as the networks gets deeper and deeper the smaller the gradiesnts become for the early layers therefore affecting model convergence since these weights would not be updated properly. This is the vanishing gradient problem. In the alternative case, when gradients are large, this would lead to gradient explosion. Vanishing gradients imply that weights if the network are not being updated, while exploding gradient imply that the weights are changing by large values based on the learning rate selected and hence the model learning can be unpredictable.


#### Why this happens?
When activation functions like sigmoid or tanh are used their value is saturated at the extrema, this implies that if the output of a layer is too small or too large then the gradients for that layer will be small. So ReLU activation was suggested as an alternative. But ReLU is prone to explodng gradients, since its gradient is always 1 for outputs greater than 0, so if we have input to relu as $in = Wx$ and output as  $out = relu(in)$, then derivative of output wrt weight W is $\frac{\delta out}{\delta W} = \frac{\delta out}{\delta in} \times \frac{\delta in}{\delta W}$, here $\frac{\delta out}{\delta in}=1$ if in in >0 else its 0.
So $\frac{\delta out}{\delta W} = (1/0) \times x $,we can note how ehis means gradients can be pretty large when relu is used.
To circumvent this problem, 

