# Model Caliberation for Machine Learning
## Problem: An uncaliberated model can give predictions that are overconfident or underconfident 

Given a multi-class prediction task, an ML model is trained to predict class labels y given input X.
  - $P(y_j = class \ i| X_j) \forall$ i = 1,...,10 classes  
If the model is uncaliberated, the probability of class i predicted by the model (eg. using a softmax layer) cannot be interepreted as true probability. For instance, a true probability would imply that when a model predicts that a given input has 0.5 probability of belonging to class i, then out of all samples 50%  of the sample actually belong to class i. So in a  well caliberated model, a probability of 0.5 would imply that the model is correct 50% of the time. Another example is binary classification fo diseas vs no disease. If for each of the 100 inputs the model predicts disease with a probability of 0.7, in a well caliberated model this would suggest that your prediction is correct 70% of the time. So, 70 of the 100 subjects have disease.

## Solution: Model Caliberation
A well caliberated model allows us to evaluate performance of differnet models and also build models that produce reliable and interpretable outputs.


## How to assess model caliberation:
1) Reliability curves, plot model prediction on X-axis and ground truth on Y-axis.
2) Cross-entropy or log-loss : penalises models that are overconfident. A well-caliberated mdoel should have low log-loss.
3) Expected Caliberation Error 
 
## Techniques for caliberation
Train-test-val split of data followed by model caliberation using Platt Scaling, isotonic regression, Spline Caliberation, etc.

