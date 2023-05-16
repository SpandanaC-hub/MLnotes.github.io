## Causal Inference
Cause is defined by David Hume as an object followed by another object, where if the first object had not been, the second had never existed.

### Counterfactual claims
The counterfactual theory of causation states that if A causes B, then this implies that if A did not occur then B will not occur. But observed counterfactuals is difficult, eg. we want to assess whether a drug causes improvement in symptoms. A subject cannot receive and not receive drug at the same time.

#### Ways to analysis causality
- Potential Outcomes 
- Structural Equation Models or Structural Causal Models
- Directed Acyclic Graphs

### Causal Learning 
The most important thing to remember when assessing results of statistical or machine learning models is "Correlation does not imply causation".

A model trained to distinguish images of cats and dogs, learns to correlate features corresponditing to each class with the class label. But spurious correlations in the data can lead to poor generalization. Another problem is that correlated features might not always be meaningful in the real world. When using these models for applications such as those related to healthcare, we want features that are biologically relevant and can explain the underlying process behind the outcome, but correlated features cannot directly imply causation.

A model could learn features of a disease in the dataset to predict presence of disease, but the learnt features might not explain the cause of the disease. So using these models to study cause-and-effect is challenging. Hence, models that explicitly capture causal relations can be more useful in application where we are interested in investigating underlying disease mechanisms.

### What is Average Treatment Effect?
Causal effect is the difference between outcomes in the real world and the counterfactual world. In average treatment effect (ATE), we compute difference in expected outcome when treatment is give vs when treatment is not given. In CATE (Conditional average treatment effect), we compute the difference conditioned on some covariate.

