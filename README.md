# Title: Accuracy and fairness tradeoff in imbalanced binary classification
This is a simple research on the changes in accuracy and fairness metrics for varying model hyperparameters. The work aims to find different combinations of hyperparameters that (i) prioritise prediction accuracy and (ii) prioritises bias mitigation in predictions for a binary classification task with imbalanced class representation.

The dataset used for the task is the German credit data. More information about the dataset can be found [here](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/new/german.doc)

## Objectives fulfilled:
1. Visualised the imbalance.
2. Selected 2 best performing prediction algorithms.
3. Performed hyperparameter tuning with 5 fold cross validation and appropriate scoring metrics to derive most accurate and fair models of the chosen algorithms.
4. Performed reweighing of dataset to modify instance weights and reduce bias according to the class representation of the protected features i.e age and sex.
5. Verified performance of models derived in point 3. on the reweighed dataset.


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


**Fig 1: Histogram of features displaying the imbalance in representation of the protected classes 'Age' and 'Sex' and labels. Histogram of features in blue and that of labels in Orange.**

The protected attribute chosen in this case to test bias is 'Age'.




![](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/new/plot.png)


**Fig 2: Choice of prediction algorithm based on accuracy and the ratio of F-scores between the unprivileged and privileged class. These predictions are made by the base models with the default hyperparameter values. Values closer to 1 are fairer in predictions than those much lesser and represent bias towards the positive class. The algorithms SVC and logistic regression have been chosen as they give the best results.**




![](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/new/svc.jpg)


**Fig 3: Results of Support vector classifier. (Blue confusion matrix for accuracy, green for fairness)**

In the above figure, we can see that the accuracy models tend to maximise accuracy of predictions. Given that positive classifications are high in number (as seen from the earlier histograms), a bias towards positive prediction may be helpful in increasing accuracy score. The fairer model often has lower accuracy value as it tends to lower misclassification of the negative labels in its predictions. For example, the accuracy model for the original samples misclassifies 54 bad credit labels (labeled '2') as good credit (label '1'). The fair model lowers this number by a lot to 24 and improves the true positive rate of bad credit classifications. As a drawback, the fair model now misclassifies a higher number of good credit classifications (1) as bad credit (2). Practically, it is considered to be a good output if lesser number of bad credits are misclassified than good credit. Reweighing helps to balance the classes as we add appropriate sample weights while training the model. We can see that in the confusion matrix for the reweighed samples fairness model. Misclassification of bad credits are reduced greatly than that of the accuracy model along with improving the F-score from 0.38 to 0.65 for the unprivileged class.


![](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/new/logreg.jpg)


**Fig 4: Results of Logistic regression.  (Blue confusion matrix for accuracy, green for fairness)**

We can see that SVC clearly performs better than Logistic regression in this case.

For more detailed discussion on accuracy and fairness, please click [here](https://github.com/rud-ninja/ML_hyperparameter_tuning/blob/main/ml_hyperparameter_tuning_report.pdf).
