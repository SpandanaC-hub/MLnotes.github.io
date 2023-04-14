The most important thing to remember when assessing results of statistical or machine learning models is "Correlation does not imply causation".

A model trained to distinguish images of cats and dogs, learns to correlate features corresponditing to each class with the class label. But spurious correlations in the data can lead to poor generalization. Another problem is that correlated features might not always be meaningful in the real world. When using these models for application in healthcare, we want features that are biologically relevant and can explain the underlying process behind the outcome, but correlated features cannot directly imply causation.

A model could learn features of a disease in the dataset to predict presence of disease, but the learnt features might not be the cause of the disease. So using these models to study cause-and-effect is challenging. Hence, models that explicitly capture causal relations can be more useful in application where we are interested in investigating underlying disease mechanisms.

