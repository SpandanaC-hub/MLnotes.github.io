### Conformal Prediction
It is a statistical technique to derive prediction sets or prediction intervals on the output of ML models such that the model's coverage is always fixed to a desired value.\\  

Let us take classification as an example application to illustrate the method.
We are given:
- A caliberation set $(X_i,Y_i)_{i=1}^n \backsim P \ iid$, the model has never seen this data
- A model that estimates P(Y=y|X=x)
- A new image $X_{n+1}$ \\

For the new image or data point, the method will provide us a set $\tau(X_{n+1})$, such that $\tau(X_{n+1})$ is a subset of y (set of all class labels), and this set contains the true class $y_{n+1}$ with high probability. The method uses the caliberation set and the model to compute $\tau(X_{n+!})$ \\

Therefore, $P(y_{n+1}\in \tau(X_{n+1})\geq 1-\alpha$, so coverage is high


