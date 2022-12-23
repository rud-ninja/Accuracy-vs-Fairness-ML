# Title: Accuracy and fairness tradeoff in imbalanced binary classification
This is a simple research on the changes in accuracy and fairness metrics for varying model hyperparameters. The work aims to find different combinations of hyperparameters that (i) prioritise prediction accuracy and (ii) prioritises bias mitigation in predictions for a binary classification task with imbalanced class representation.

The dataset used for the task is the German credit data. More information about the dataset can be found [here](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/new/german.doc)

## Objectives:
1. Visualising the imbalance.
2. Select the prediction algorithm to be used.
3. Perform hyperparameter tuning with 5 fold cross validation and appropriate scoring metrics to derive most accurate and fair models respectively.
4. Perform reweighing of dataset to add weights and reduce bias according to the class representation of the critical features.
5. Check performance of models derived in point 3. on the reweighed dataset.


#### Libraries used:
Pandas, NumPy, aif360 (for datasets), sklearn, matplotlib

#### Datasets used:
*German* from the aif360 library.
Older version included *Adult income* as well. Python notebook [here](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/ML_hyperparameter_tuning/ml_hyperparameter_tuning_code.ipynb)

#### Classification models:
Logistic regression and Support vector classifier

#### Performance metrics considered:
For accuracy: 'Accuracy' or Correct predictions / Total predictions
For fairness: 'F-score' or (2 * Precision * Recall) / (precision + recall)



## Figures and tables

![](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/new/hist.png)


Fig 1: Histogram of features displaying the imbalance in representation of the protected classes 'Age' and 'Sex' and labels. Histogram of features in blue and that of labels in Orange.

The protected attribute chosen in this case to test bias is 'Age'.




![](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/new/plot.png)


Fig 2: Choice of prediction algorithm based on accuracy and the ratio of F-scores between the unprivileged and privileged class. These predictions are made by the base models with the default hyperparameter values. Values closer to 1 are fairer in predictions than those much lesser and represent bias towards the positive class. The algorithms SVC and logistic regression have been chosen as they give the best results.




![](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/new/svc.jpg)


Fig 3: Results of Support vector classifier. (Blue confusion matrix for accuracy, green for fairness)

In the above figure, we can see that the accuracy models tend to maximise accuracy of predictions. Given that positive classifications are high in number (as seen from the earlier histograms), a bias towards positive prediction may be helpful in increasing accuracy score. The fairer model often has lower accuracy value as it tends to lower misclassification of the negative labels in its predictions. For example, the accurate model for the original samples misclassifies 54 bad credit labels as good credit. The fair model lowers this number by a lot to 24. Reweighing helps to balance the classes and lower bias as we add appropriate sample weights while training the model.


![](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/new/logreg.jpg)


Fig 4: Results of Logistic regression.  (Blue confusion matrix for accuracy, green for fairness)

We can see that SVC clearly performs better than Logistic regression in this case.

For more detailed discussion on accuracy and fairness, please click [here](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/ml_hyperparameter_tuning_report.pdf).
