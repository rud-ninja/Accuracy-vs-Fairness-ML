# Title: Research Classification model improvement by optimizing accuracy and reducing bias by hyperparameter tuning and k-fold cross validation.

## Objectives:
1. Preprocess dataset.
2. Explore different hyperparameters of a selected classification model algorithm and test models with different values for the same.
3. Derive hyperparameter values and score for the most accurate and fair models respectively.
4. Perform reweighing of dataset to reduce bias in representation of the critical feature categories.
5. Repeat points 2 & 3 on reweighed dataset.
6. Discuss a strategy to choose the most generalized model


#### Libraries used:
Pandas, NumPy, aif360 (for datasets), sklearn, matplotlib

#### Datasets used:
*Adult income* and *German* from the aif360 library.

#### Classification model:
SVM with radom values of hyperparameters C and gamma. Default kernel 'rbf' used. Equal opportunity difference and disparate impact were chosen as the metrics for bias.