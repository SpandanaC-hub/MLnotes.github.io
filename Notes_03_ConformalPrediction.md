### Conformal Prediction
It is a statistical technique to derive prediction sets or prediction intervals on the output of ML models such that the model's coverage is always fixed to a desired value.\\  

Let us take classification as an example application to illustrate the method.
We are given:
- A caliberation set $(X_i,Y_i)_{i=1}^n \backsim P \ iid$, the model has never seen this data
- A model that estimates P(Y=y|X=x)
- A new image $X_{n+1}$
For the new image or data point, the model should produce a point estimate i.e. the predicted class and also a set $\tau(X_{n+1})$

