## Causal Inference
Cause is defined by David Hume as an object followed by another object, where if the first object had not been, the second had never existed. [Simpson's paradox](https://en.wikipedia.org/wiki/Simpson%27s_paradox)  is a motivating example for causal inference. 

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

#### Correlation = Causation is a cognitive bias
Availability heuristic and motivated reasoning are both cognitive biases which result in concluding that correlation equals causation. If we read a paper that states that social media causes anxiety, we migth associate our anxiety to use of social media since taht is the most recent thing we read. On another hand, if we do not like socializing, we might associate socializing to anxiety as that gives us a reason to not socialize. This is an example of motivated reasoning.

### Potential Outcomes
T = {0,1} denotes whether subject received treatment i.e. observed treatment.  Y denotes the observed outcome. Then for a subject i, $Y_i(T=0)$ represents  outcome when treatment was not given and $Y_i(T=1)$ represents outcome when treatment was given. The causal effect of treatment on subject i's outcome is therefore equal to $Y_i(T=1)-Y_i(T=0) = ITE$ (ITE refers to individual treatment effect). And herein lies the fundamental problem with causal inference which we previously described which is that we cannot observe the counterfactual of subject i not receiving treatment when subject i already received treatment. Hence, we need to look at the average treatment effect.

#### What is Average Treatment Effect?
Causal effect is the difference between outcomes in the real world and the counterfactual world. In average treatment effect (ATE), we compute difference in expected outcome when treatment is give vs when treatment is not given. ATE = E[Y(T=1)]-E[Y(T=0)]. The difference in these potential outcomes i.e. causal effect is usually not equal to the difference in conditional expectations i.e. ATE = E[Y(T=1)]-E[Y(T=0)] $\ne$ E[Y|T=1]-E[Y|T=0]. This is due to the presence of confounding. This is because the difference in conditional expectation is not a causal quantity, it is a mixture of causal and confounding assocition. To prevent confounding, people use randomized control trials where the treatment and no treatment groups are randomly assigned thereby removing confounding associations.
Assumptions where E[Y(1)]-E[Y(0)] = E[Y|T=1]-E[Y|T=0] are:
1) Ignorability: If potential outcome was independent of treatment group assignment, then E[Y(1)]-E[Y(0)] = E[Y(1)|T=1]-E[Y(0)|T=1] = E[Y|T=1]-E[Y|T=0]
2) Exchangeability: The Expected outcome conditioned on treatment vs no treatment is the same if the groups were reversed.

### Observational Studies
Since randomizing subjects to different groups is not always feasible, observation studies usually have confounding association that cannot be ignored. Hence, measuring causal effects in observation studies requires us to explicitly control for confounders.

#### CATE (Conditional average treatment effect)
Since we cannot always use RCT study design, that means potential outcomes are not independent of treatment group assignment. Here, we use conditional exchangeability where we additionally condition of the confounder to get ACTE.

In CATE (Conditional average treatment effect), we compute the difference conditioned on some covariate. ie E[Y(T=1)-Y(T=0)|X] = E[Y(T=1)|X]-E[Y(T=0)|X] = E[Y(T=1)|T=1,X]-E[Y(T=0)|T=0,X]=E[Y|T=1,X]-E[Y|T=0,X]

