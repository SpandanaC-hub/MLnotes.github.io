### Conformal Prediction
It is a statistical technique to derive prediction sets or prediction intervals on the output of ML models such that the model's coverage is always fixed to a desired value.   

Let us take classification as an example application to illustrate the method.
We are given:
- A caliberation set $(X_i,Y_i)_{i=1}^n \backsim P \ iid$, the model has never seen this data
- A model that estimates P(Y=y|X=x)
- A new image $X_{n+1}$  

For the new image or data point, the method will provide us a set $\tau(X_{n+1})$, such that $\tau(X_{n+1})$ is a subset of y (set of all class labels), and this set contains the true class $y_{n+1}$ with high probability. The method uses the caliberation set and the model to compute $\tau(X_{n+!})$ 

Therefore, $P(y_{n+1}\in \tau(X_{n+1})\geq 1-\alpha$, so coverage is high

What properties do the conformal prediction sets need to satisfy?
- The sets need to at the least provide conservative coverage
- The sets should be small sized
- The sets need to be adaptive i.e. small set for easy problems and larger set for difficult problems

Algorithm to create the set $\tau(.)$ (Vovk et. al. - 1998)

1) For each $(X_i,Y_i)$ get the score predicted by the model for the input $X_i$ i.e. get the softmax scores. Now, take the score for the correct class $Y_i$ and denote the score as $E_i$. Repeat for all examples in caliberation set, so we have ${E_1,...,E_n}$
2) Take the 10% quantile over the scores {E_i}_{i=1}^n and call it $\hat{q}$. Therefore, atleast 90% of the scores will be greater than $\hat{q}$
3) For a new data point $X_{n+1}$, the prediction set would be the set of all classes whose scores fall above $\hat{q}$ when $X_{n+1}$ is input. 


