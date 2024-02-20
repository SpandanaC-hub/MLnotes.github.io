### Gradients
For a 3 layer NN: with input $X_i\in R^{Nxp}$ the output of first, second, and third layer are $a_{1i},a_{2i},a_{3i}$ respectively. If loss over a  mini-batch $X_i, i=1,..,m$ is defined as L=\sum_i ||y_i-a_{3i}||_2\\
the gradients wrt to each layers weights i.e. $W1,W2,W3$ would need to be computed for SGD since $W^{t+1} = W^{t}-\eta\frac{\delta {L}}{\delta{W^{t}} }$\\\\

