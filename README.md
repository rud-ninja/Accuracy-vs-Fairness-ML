<html>

<head>
<meta http-equiv=Content-Type content="text/html; charset=utf-8">
<meta name=Generator content="Microsoft Word 15 (filtered)">
<style>
<!--
 /* Font Definitions */
 @font-face
	{font-family:Wingdings;
	panose-1:5 0 0 0 0 0 0 0 0 0;}
@font-face
	{font-family:"Cambria Math";
	panose-1:2 4 5 3 5 4 6 3 2 4;}
@font-face
	{font-family:DengXian;
	panose-1:2 1 6 0 3 1 1 1 1 1;}
@font-face
	{font-family:Calibri;
	panose-1:2 15 5 2 2 2 4 3 2 4;}
@font-face
	{font-family:"\@DengXian";
	panose-1:2 1 6 0 3 1 1 1 1 1;}
 /* Style Definitions */
 p.MsoNormal, li.MsoNormal, div.MsoNormal
	{margin-top:0in;
	margin-right:0in;
	margin-bottom:8.0pt;
	margin-left:0in;
	line-height:107%;
	font-size:11.0pt;
	font-family:"Calibri",sans-serif;}
p.MsoListParagraph, li.MsoListParagraph, div.MsoListParagraph
	{margin-top:0in;
	margin-right:0in;
	margin-bottom:8.0pt;
	margin-left:.5in;
	line-height:107%;
	font-size:11.0pt;
	font-family:"Calibri",sans-serif;}
p.MsoListParagraphCxSpFirst, li.MsoListParagraphCxSpFirst, div.MsoListParagraphCxSpFirst
	{margin-top:0in;
	margin-right:0in;
	margin-bottom:0in;
	margin-left:.5in;
	line-height:107%;
	font-size:11.0pt;
	font-family:"Calibri",sans-serif;}
p.MsoListParagraphCxSpMiddle, li.MsoListParagraphCxSpMiddle, div.MsoListParagraphCxSpMiddle
	{margin-top:0in;
	margin-right:0in;
	margin-bottom:0in;
	margin-left:.5in;
	line-height:107%;
	font-size:11.0pt;
	font-family:"Calibri",sans-serif;}
p.MsoListParagraphCxSpLast, li.MsoListParagraphCxSpLast, div.MsoListParagraphCxSpLast
	{margin-top:0in;
	margin-right:0in;
	margin-bottom:8.0pt;
	margin-left:.5in;
	line-height:107%;
	font-size:11.0pt;
	font-family:"Calibri",sans-serif;}
.MsoChpDefault
	{font-family:"Calibri",sans-serif;}
.MsoPapDefault
	{margin-bottom:8.0pt;
	line-height:107%;}
@page WordSection1
	{size:841.9pt 595.3pt;
	margin:.5in .5in .5in .5in;}
div.WordSection1
	{page:WordSection1;}
 /* List Definitions */
 ol
	{margin-bottom:0in;}
ul
	{margin-bottom:0in;}
-->
</style>

</head>

<body lang=EN-US style='word-wrap:break-word'>

<div class=WordSection1>

<p class=MsoNormal align=center style='text-align:center;line-height:150%'><b><span
lang=EN-IN style='font-size:22.0pt;line-height:150%'>Visualising Accuracy vs.
Fairness in ML models</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN style='font-size:18.0pt;line-height:150%'>Introduction</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><img width=357
height=238 src="readme_doc%20-%20Copy_files/image001.jpg" align=left hspace=12><span
lang=EN-IN>In the pursuit of building highly accurate machine learning models,
it's often easy to overlook the potential biases hidden within these
mathematical constructs. Our primary focus becomes achieving the best
predictive performance, sometimes at the cost of introducing unfair or
discriminatory outcomes. AI Fairness 360 is a pioneering initiative dedicated
to unearthing and addressing these biases. It conducts rigorous research and
offers powerful methods to mitigate disparities in machine learning models.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>But wait, how can a mathematical model be biased against humans?
Well, the reasons are as follows:</span></p>

<ol style='margin-top:0in' start=1 type=1>
 <li class=MsoNormal style='text-align:justify;line-height:150%'><b><span
     lang=EN-IN>Biased Training Data</span></b><span lang=EN-IN>: Machine
     learning models learn from historical data, and if this data contains
     biases or discrimination, the model is likely to inherit those biases. For
     example, if historical hiring data favours certain demographic groups over
     others, a model trained on this data may perpetuate hiring biases.</span></li>
 <li class=MsoNormal style='text-align:justify;line-height:150%'><b><span
     lang=EN-IN>Data Collection Methods</span></b><span lang=EN-IN>: Bias can
     be introduced during data collection. For example, if data collection
     processes favour certain groups or areas over others, the resulting data
     will reflect these biases.</span></li>
 <li class=MsoNormal style='text-align:justify;line-height:150%'><b><span
     lang=EN-IN>Historical Inequities</span></b><span lang=EN-IN>: Biases may
     also stem from systemic inequalities that have existed in society for a
     long time. These inequities can be reflected in the data used to train
     models, leading to biased outcomes.</span></li>
 <li class=MsoNormal style='text-align:justify;line-height:150%'><b><span
     lang=EN-IN>Labelling Bias</span></b><span lang=EN-IN>: Biases can arise
     from the way data is labelled. Human annotators or data labellers may
     inadvertently introduce their own biases when labelling data.</span></li>
 <li class=MsoNormal style='text-align:justify;line-height:150%'><b><span
     lang=EN-IN>Sample Size</span></b><span lang=EN-IN>: If certain groups are
     underrepresented in the training data, the model may not learn to make
     accurate predictions for those groups, leading to bias against them.</span></li>
 <li class=MsoNormal style='text-align:justify;line-height:150%'><b><span
     lang=EN-IN>Feature Engineering</span></b><span lang=EN-IN>: The selection
     of features or variables used in the model can introduce bias if certain
     features are chosen based on subjective criteria or if they carry
     underlying biases.</span></li>
</ol>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>In this exploration, we delve into one of AI Fairness 360's
datasets, known as the &quot;Adult Income&quot; dataset. Our aim is to
visualize and understand modelling bias concerning an individual's sex,
shedding light on the importance of fairness and equity in the world of
artificial intelligence.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN style='font-size:18.0pt;line-height:150%'>About the dataset</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><img width=296
height=168 src="readme_doc%20-%20Copy_files/image002.png" align=left hspace=12><span
lang=EN-IN>The AI Fairness 360 (AIF360) toolkit provides a collection of
datasets for use in fairness, bias, and discrimination research in machine
learning. One of the datasets included in AIF360 is the &quot;Adult
Income&quot; dataset. This dataset is used for income prediction, typically for
tasks like income classification. </span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN>Task:</span></b><span lang=EN-IN> The primary task associated with
the Adult Income dataset is income prediction. The goal is to predict whether
an individual's income exceeds $50,000 per year based on various demographic
and employment-related features.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN>Features:</span></b><span lang=EN-IN> The dataset contains a set of
features that describe individuals, including age, education, occupation,
marital status, race, gender, hours worked per week, etc. </span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN>Label:</span></b><span lang=EN-IN> The target variable or label is a
binary variable that indicates whether an individual's income exceeds $50,000
per year (1 for income &gt; $50K, 0 for income &lt;= $50K).</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN>Protected class:</span></b><span lang=EN-IN> There are two protected
classes in the dataset, namely race and sex. For this analysis, we have chosen
to focus on sex as a factor that may introduce bias. In this context, the
privileged class is &quot;Male&quot; (labelled as 1), while the unprivileged
class is &quot;Female&quot; (labelled as 0).</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN style='font-size:18.0pt;line-height:150%'>Python specifications</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Environment – Jupyter</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Classifier – Random Forest</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Key modules – AIF360 (similar to sklearn but for fairness analysis)</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN style='font-size:18.0pt;line-height:150%'>Bias-variance</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Before delving into assessing the fairness of a predictive model,
it's crucial to grasp the trade-off between bias and variance. These two
concepts are fundamental in the context of model performance and have a
significant impact on a model's ability to make accurate predictions.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Bias in a machine learning model represents the error that occurs
when the model simplifies complex real-world data and fails to capture the
underlying patterns and trends. High bias leads to underfitting, where the
model is overly simplistic and performs poorly on both the data it was trained
on (the training data) and unseen data (the testing data). To mitigate bias,
one can explore strategies such as using more complex models, increasing the
model's capacity, or incorporating more informative features.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><img width=376
height=252 src="readme_doc%20-%20Copy_files/image003.jpg" align=left hspace=12><span
lang=EN-IN>Variance, on the other hand, describes how sensitive a model is to
small fluctuations or noise in the training data. High variance results in
overfitting, a scenario where the model fits the training data extremely
closely but struggles to generalize to new, unseen data. To reduce variance,
it's advisable to simplify the model, apply regularization techniques, increase
the amount of training data, or carefully select relevant features.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>The bias-variance trade-off is a central concept in machine
learning. Striking the right balance between bias and variance is essential for
a model to generalize effectively to new, unseen data. Techniques like
cross-validation, hyperparameter tuning, and feature engineering play a pivotal
role in finding this equilibrium and constructing models that excel in making
predictions on previously unobserved data.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>In cases of highly imbalanced datasets, the importance of proper
data handling becomes evident. Unlike balanced datasets where accuracy is a
commonly chosen evaluation metric, imbalanced datasets like this one benefit
from metrics like the F-score or log loss for more precise model assessment.
These metrics account for the imbalance and provide a more accurate measure of
a model's performance, particularly in situations where minority classes are of
significant importance.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN><img width=1024 height=273 id="Picture 4"
src="readme_doc%20-%20Copy_files/image004.png"></span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>The provided figure illustrates a common scenario where a model's
performance diverges at a certain point, indicating a shift from better
performance on the training data to less favourable results on the test data.
Ideally, the chosen model should strike a balance between these two data sets,
delivering optimal results within acceptable error margins. The three graphs,
from left to right, portray the progression from underfitting to overfitting,
with the desired model residing somewhere in between.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Apart from the techniques mentioned for addressing overfitting,
model selection plays a pivotal role. Ensemble algorithms like Random Forest
offer a robust solution to overfitting because they consider results from
multiple trees with varying performance levels. This diversity often results in
a more balanced and reliable model that generalizes well to new, unseen data.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Having discussed bias and variance in predictions, let's delve into
the core of our analysis. The analysis is structured into two main sections:</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>In the first section, we conducted hyperparameter tuning for a
Random Forest model, resulting in two models with distinct focuses. One model
prioritizes accurate predictions, while the other emphasizes fairness in the
selection process, particularly for privileged and unprivileged classes. In
this section, all samples are assigned uniform weight.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>In the second section, we repeated the same steps, but this time we
introduced sample weights that consider not only the label class but also the
protected class. This approach categorizes samples into four distinct groups:
positive-privileged, positive-unprivileged, negative-privileged, and
negative-unprivileged.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Before proceeding, a mild overview of two of the fairness metrics
used:</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN>Equal opportunity difference</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>EOD measures the disparity in the model's true positive rates
(sensitivity or recall) between the privileged and unprivileged groups in a
protected attribute (e.g., gender or race). It quantifies the difference in the
probability that a true positive prediction is made for each group, indicating
whether one group has an advantage in terms of positive predictions. EOD
assesses whether the model provides equal opportunities for positive outcomes
across different groups. A value of 0 indicates fairness, while a positive
value suggests a favourable bias towards the privileged group, and a negative
value indicates bias towards the unprivileged group.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN>Disparate Impact</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Disparate Impact, also known as Adverse Impact, focuses on the
impact of a model's decisions on different protected groups, often with respect
to adverse or unfavourable outcomes such as being denied a loan or job. It is
typically measured as the ratio of the predicted positive outcomes for the
privileged group to the predicted positive outcomes for the unprivileged group.
Disparate Impact analysis aims to identify and rectify situations where one
group is disproportionately affected or favoured by the model's decisions. A
value of 1 indicates no disparate impact, while values significantly above or
below 1 suggest potential discrimination.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN style='font-size:18.0pt;line-height:150%'>Accuracy and fairness with
uniform weight</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN>Accurate model:</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>The selection criteria used for the accuracy focused model was
log-loss or cross-entropy loss whose formula is  </span><span
lang=EN-GB style='font-size:11.0pt;line-height:107%;font-family:"Calibri",sans-serif;
position:relative;top:6.0pt'><img width=262 height=26
src="readme_doc%20-%20Copy_files/image005.png"></span><span lang=EN-IN> </span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>The metric used for evaluating model fairness was disparate impact.
The function to calculate DI is available from the aif360 library.</span></p>

<table class=MsoTableGrid border=1 cellspacing=0 cellpadding=0
 style='border-collapse:collapse;border:none'>
 <tr>
  <td width=513 style='width:384.7pt;border:solid windowtext 1.0pt;padding:
  0in 5.4pt 0in 5.4pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:115%'><b><span lang=EN-IN style='font-size:18.0pt;line-height:
  115%'>Accurate model</span></b></p>
  </td>
  <td width=513 style='width:384.7pt;border:solid windowtext 1.0pt;border-left:
  none;padding:0in 5.4pt 0in 5.4pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:115%'><b><span lang=EN-IN style='font-size:18.0pt;line-height:
  115%'>Fair model</span></b></p>
  </td>
 </tr>
 <tr style='height:49.5pt'>
  <td width=513 style='width:384.7pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:49.5pt'>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>precision   
  recall  f1-score   support</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>&nbsp;</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>0.0       0.91     
  0.70      0.80     11132</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>1.0       0.46     
  0.79      0.58      3521</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>&nbsp;</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>accuracy                          
  0.73     14653</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>macro avg      
  0.69      0.75      0.69     14653</span></p>
  <p class=MsoNormal align=right style='margin-bottom:8.0pt;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>weighted avg      
  0.81      0.73      0.74     14653</span></p>
  </td>
  <td width=513 style='width:384.7pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:49.5pt'>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>precision   
  recall  f1-score   support</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>&nbsp;</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>0.0       0.84     
  0.83      0.83     11132</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>1.0       0.48     
  0.51      0.50      3521</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>&nbsp;</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>accuracy                          
  0.75     14653</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>macro avg       0.66     
  0.67      0.66     14653</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>weighted avg      
  0.76      0.75      0.75     14653</span></p>
  </td>
 </tr>
 <tr style='height:311.0pt'>
  <td width=513 style='width:384.7pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:311.0pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:150%'><span lang=EN-IN><img width=494 height=374
  id="Picture 1451981202" src="readme_doc%20-%20Copy_files/image006.png"></span></p>
  </td>
  <td width=513 style='width:384.7pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:311.0pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:150%'><span lang=EN-IN><img width=462 height=374
  id="Picture 1197105560" src="readme_doc%20-%20Copy_files/image007.png"></span></p>
  </td>
 </tr>
 <tr style='height:55.35pt'>
  <td width=513 style='width:384.7pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:55.35pt'>
  <p class=MsoNormal style='margin-bottom:0in;text-align:justify;line-height:
  115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:
  "Courier New";color:#212121;background:white'>Fairness metrics of accurate
  model on unweighted samples: -</span></p>
  <p class=MsoNormal style='margin-bottom:0in;text-align:justify;line-height:
  115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:
  "Courier New";color:#212121;background:white'>Equal opportunity difference: 
  -0.3934</span></p>
  <p class=MsoNormal style='margin-bottom:0in;text-align:justify;line-height:
  115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:
  "Courier New";color:#212121;background:white'>Disparate Impact:  0.2722</span></p>
  </td>
  <td width=513 style='width:384.7pt;border-top:none;border-left:none;
  border-bottom:solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;
  padding:0in 5.4pt 0in 5.4pt;height:55.35pt'>
  <p class=MsoNormal style='margin-bottom:0in;text-align:justify;line-height:
  115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:
  "Courier New";color:#212121;background:white'>Fairness metrics of fair model
  on unweighted samples: -</span></p>
  <p class=MsoNormal style='margin-bottom:0in;text-align:justify;line-height:
  115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:
  "Courier New";color:#212121;background:white'>Equal opportunity difference: 
  0.0155</span></p>
  <p class=MsoNormal style='margin-bottom:0in;text-align:justify;line-height:
  115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:
  "Courier New";color:#212121;background:white'>Disparate Impact:  0.8343</span></p>
  </td>
 </tr>
</table>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN>&nbsp;</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN>Discussion:</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Upon initial observation, it appears that the fair model outperforms
the accurate model in classification, boasting a higher accuracy of 75%
compared to the accurate model's 73%. However, it's important to consider the
dataset's high imbalance, primarily favoring one label class (0). Consequently,
accuracy alone is an inadequate metric for model evaluation.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>A closer examination of recall and F1-score reveals that the
accurate model excels as a classifier when compared to the fair model. This is
further bolstered by the confusion matrix where we can clearly see which model
was better able to accommodate for the class label imbalance and predict the
minority class better. It's worth noting that this improvement in predicting
the minority class often comes at the cost of misclassifying some of the
majority class labels. However, this trade-off is an essential aspect of
achieving a more generalized model that accommodates both class extremes.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>In the third row, the fair model lives up to its name, delivering
values that approach absolute fairness for the evaluation metrics, as seen in
the Equal Opportunity Difference (EOD) close to 0 and Disparate Impact (DI)
close to 1. The accompanying bar plots provide further evidence that the
fairness model narrows the gap in predicting true positives between privileged
and unprivileged classes, while the accurate model predominantly favours the
privileged class in this regard.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN><img width=1027 height=476 id="Picture 11"
src="readme_doc%20-%20Copy_files/image008.png"></span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>But, can we enhance fairness while preserving optimal classification
performance? AI Fairness 360 offers a practical solution for this challenge:
assigning weights to samples through a technique known as
&quot;Reweighing.&quot;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Reweighing is a technique designed to mitigate bias and promote
fairness in machine learning models. It can be found as a preprocessing
algorithm in the aif360 library. The technique works by adjusting the weights
of the samples in the dataset. It aims to give different weights to different
samples, particularly focusing on the privileged and unprivileged groups
defined by a protected attribute (in this case sex). The goal is to create a
balanced dataset, where the model's training process is less influenced by the
privileged group.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Here's how reweighing works:</span></p>

<p class=MsoListParagraphCxSpFirst style='text-align:justify;text-indent:-.25in;
line-height:150%'><span lang=EN-IN style='font-family:Symbol'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-IN>Calculate Initial Weights: Initially, the
dataset is assigned uniform weights for all samples. This means that each
sample has the same weight in the training process.</span></p>

<p class=MsoListParagraphCxSpMiddle style='text-align:justify;text-indent:-.25in;
line-height:150%'><span lang=EN-IN style='font-family:Symbol'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-IN>Identify Protected Groups: The protected
attribute is used to categorize the dataset into privileged and unprivileged
groups. For example, in gender fairness, male and female groups may be
identified.</span></p>

<p class=MsoListParagraphCxSpMiddle style='text-align:justify;text-indent:-.25in;
line-height:150%'><span lang=EN-IN style='font-family:Symbol'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-IN>Compute Disparities: The disparities in
prediction outcomes between the privileged and unprivileged groups are
measured. These disparities include metrics like false positive rates, false
negative rates, or other relevant fairness metrics.</span></p>

<p class=MsoListParagraphCxSpMiddle style='text-align:justify;text-indent:-.25in;
line-height:150%'><span lang=EN-IN style='font-family:Symbol'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-IN>Adjust Sample Weights: The sample weights are
then adjusted based on the disparities identified. The goal is to assign more
weight to underprivileged or disadvantaged groups and reduce the weight of
privileged groups. This helps to balance the influence of these groups during
model training.</span></p>

<p class=MsoListParagraphCxSpLast style='text-align:justify;text-indent:-.25in;
line-height:150%'><span lang=EN-IN style='font-family:Symbol'>·<span
style='font:7.0pt "Times New Roman"'>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</span></span><span lang=EN-IN>Iterative Process: The reweighing process is
often iterative. The sample weights are recalculated, disparities are
reevaluated, and the weights are adjusted again. This cycle continues until the
model's predictions become fairer and more unbiased.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>By reweighing the dataset, it ensures that the model's training
process considers the needs and characteristics of both privileged and
unprivileged groups more equally. It's a valuable tool in promoting fairness
and reducing bias in machine learning models, particularly when dealing with
imbalanced datasets or scenarios where fairness concerns are paramount, for
example while developing a loan approval system or student admission systems.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN style='font-size:18.0pt;line-height:150%'>Accuracy and fairness with
reweighed samples</span></b></p>

<table class=MsoTableGrid border=1 cellspacing=0 cellpadding=0
 style='border-collapse:collapse;border:none'>
 <tr>
  <td width=527 style='width:395.0pt;border:solid windowtext 1.0pt;padding:
  0in 5.4pt 0in 5.4pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:115%'><b><span lang=EN-IN style='font-size:18.0pt;line-height:
  115%'>Accurate model</span></b></p>
  </td>
  <td width=499 style='width:5.2in;border:solid windowtext 1.0pt;border-left:
  none;padding:0in 5.4pt 0in 5.4pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:115%'><b><span lang=EN-IN style='font-size:18.0pt;line-height:
  115%'>Fair model</span></b></p>
  </td>
 </tr>
 <tr style='height:120.0pt'>
  <td width=527 style='width:395.0pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:120.0pt'>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>             
  precision    recall  f1-score   support</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>&nbsp;</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>         0.0      
  0.89      0.71      0.79     11132</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>         1.0      
  0.44      0.72      0.55      3521</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>&nbsp;</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>   
  accuracy                           0.71     14653</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>   macro avg      
  0.67      0.72      0.67     14653</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>weighted avg      
  0.78      0.71      0.73     14653</span></p>
  </td>
  <td width=499 style='width:5.2in;border-top:none;border-left:none;border-bottom:
  solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;padding:0in 5.4pt 0in 5.4pt;
  height:120.0pt'>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>             
  precision    recall  f1-score   support</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>&nbsp;</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>         0.0      
  0.89      0.72      0.79     11132</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>         1.0      
  0.44      0.71      0.55      3521</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>&nbsp;</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>   
  accuracy                           0.72     14653</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>   macro avg      
  0.67      0.71      0.67     14653</span></p>
  <p class=MsoNormal align=right style='margin-bottom:0in;text-align:right;
  line-height:115%'><span lang=EN-IN style='font-size:10.5pt;line-height:115%;
  font-family:"Courier New";color:#212121;background:white'>weighted avg      
  0.78      0.72      0.73     14653</span></p>
  </td>
 </tr>
 <tr style='height:297.55pt'>
  <td width=527 style='width:395.0pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:297.55pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:150%'><b><span lang=EN-IN style='font-size:18.0pt;line-height:
  150%'><img width=513 height=374 id="Picture 9"
  src="readme_doc%20-%20Copy_files/image009.png"></span></b></p>
  </td>
  <td width=499 style='width:5.2in;border-top:none;border-left:none;border-bottom:
  solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;padding:0in 5.4pt 0in 5.4pt;
  height:297.55pt'>
  <p class=MsoNormal align=center style='margin-bottom:0in;text-align:center;
  line-height:150%'><b><span lang=EN-IN style='font-size:18.0pt;line-height:
  150%'><img width=476 height=374 id="Picture 10"
  src="readme_doc%20-%20Copy_files/image010.png"></span></b></p>
  </td>
 </tr>
 <tr style='height:55.85pt'>
  <td width=527 style='width:395.0pt;border:solid windowtext 1.0pt;border-top:
  none;padding:0in 5.4pt 0in 5.4pt;height:55.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:115%'><span
  lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:"Courier New";
  color:#212121;background:white'>Fairness metrics of accurate model on
  reweighed samples:-</span></p>
  <p class=MsoNormal style='margin-bottom:0in;line-height:115%'><span
  lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:"Courier New";
  color:#212121;background:white'>Equal opportunity difference:  0.0329</span></p>
  <p class=MsoNormal style='margin-bottom:0in;line-height:115%'><span
  lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:"Courier New";
  color:#212121;background:white'>Disparate Impact:  0.9351</span></p>
  </td>
  <td width=499 style='width:5.2in;border-top:none;border-left:none;border-bottom:
  solid windowtext 1.0pt;border-right:solid windowtext 1.0pt;padding:0in 5.4pt 0in 5.4pt;
  height:55.85pt'>
  <p class=MsoNormal style='margin-bottom:0in;line-height:115%'><span
  lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:"Courier New";
  color:#212121;background:white'>Fairness metrics of fair model on reweighed
  samples:-</span></p>
  <p class=MsoNormal style='margin-bottom:0in;line-height:115%'><span
  lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:"Courier New";
  color:#212121;background:white'>Equal opportunity difference:  0.0461</span></p>
  <p class=MsoNormal style='margin-bottom:0in;line-height:115%'><span
  lang=EN-IN style='font-size:10.5pt;line-height:115%;font-family:"Courier New";
  color:#212121;background:white'>Disparate Impact:  0.961</span></p>
  </td>
 </tr>
</table>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN>Discussion:</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>Following the application of sample reweighing, the accuracy-focused
and fairness-focused models yield more balanced results, with similar outputs.
These models not only excel in classification performance but also strike a
balance between privileged and unprivileged classes.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN style='font-size:18.0pt;line-height:150%'><img width=1027
height=476 id="Picture 12" src="readme_doc%20-%20Copy_files/image011.png"></span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>&nbsp;</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><b><span
lang=EN-IN style='font-size:18.0pt;line-height:150%'>Conclusion</span></b></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>In this task, we analysed the effects of bias and the requirements
of fairness in machine learning models trough a simple classification problem.
We began by discussing about the bias-variance trade-off in machine learning
that almost always takes the front seat obscuring the effects of unfairness and
bias towards specific classes. To demonstrate this, we obtained two similar
models fine-tuned to produce i) the most accurate results and ii) the fairest
result. After observing their differences and understanding the impact, a
method called reweighing was discussed which aims to mitigate the effects of
bias while training a machine learning model. At the end, we visualised the effects
of reweighing and confirmed the minimization of bias in the training process.</span></p>

<p class=MsoNormal style='text-align:justify;line-height:150%'><span
lang=EN-IN>The complete code in python can be found here.</span></p>

</div>

</body>

</html>
