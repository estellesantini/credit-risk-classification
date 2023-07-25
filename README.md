# credit-risk-classification.

## Overview of Analysis
In this supervised learning challenge a model is trained to evaluate if a loan is a healthy or high risk loan. By using test data and assessing the balance of each class, the target variable can be predicted. With this prediction, the model's can evaluate the accuracy and how well the model performs. 

To build this model, I took the following steps:
1. Split the Data into Training and Testing Sets
2. Create a Logistic Regression Model with the Original Data's Training Data
3. Evaluate the Model's Performance
4. Create a Logistic Regression with Resampled Training Data
While 
5. Re-evaluate the Model's Performance

To have a good representation of the samples and have unbiased predictions, the dataset must be balanced meaning have around the same number of occurences. There are multiple other components assessed in the performance of a model including precision, recall, f-1 score, and overall metrics. The purpose of this analysis is to determine if the model had a good performance in predicting the risk of a loan.

## Results
<!-- The results: Using a bulleted list, describe the accuracy score, the precision score, and recall score of the machine learning model -->
<b> Original Dataset </b>
<br>
The results of the model using the original dataset can be summarized by the following:
- Balance accuracy 0.9924164259182832
- Confusion matrix [[18679    80]
 [   67   558]]
 - Classification Report

|            | precision | recall | f1-score | support |
|------------|-----------|--------|----------|---------|
| 0 (healthy)|   1.00    | 1.00   |   1.00   |  18759  |
| 1 (high-risk) |   0.87    | 0.89   |   0.88   |   625 |
| accuracy   |           |        |   0.99   |  19384  |
| macro avg  |   0.94    | 0.94   |   0.94   |  19384  |
| weighted avg |   0.99    | 0.99   |   0.99   |  19384  |
<br/>

The classification report demonstrates that this model performs very well for class 0 (healthy loans) with nearly 100% precision and recall. The model also performs very strongly for identifying high-risk loans, with a lower yet still high precision, recall, and F1-score. Precision is the proportion of true positive predictions to the total number of predictions in that class, recall measures the true positive predictions to the number of predictions in the class, and f1-score encompasses the predictions and recall.

To break these statistics down further, the high-risk loan's precision of 0.87 indicates that the model correctly predicts that a loan is a high-risk about 87% of the time, whereas 100% of healthy loan predictions are healthy loans. The recall of a high-risk loan shows 89% of the time the model can determine actual samples, while healthy loans can 100% of the time. Both loans have a good balance between precision and recall although the high-risk F1-score is 0.12 lower. 

Although this looks favorable, in this analysis it is important to note that there is a wide class imbalance. The support shows that the number of occurences of healthy loans was over 30 times more than the frequency of high-risk loans. This shows that the dataset was not balanced, which should be considered in analyzing these statistics. 

The overall performance and accuracy shows that 99% of the samples in the test data are predicted accurately using this model, the macro average for each class is 94% in precision, recall, and F1-scoring.

<b> Resampled Dataset </b>
<br>
The previous results can be compared to the model with the resampled data:
- Balance accuracy 0.9959744975744975
- Confusion matrix [[18668    91]
 [    2   623]]
 - Classification Report

|            | precision | recall | f1-score | support |
|------------|-----------|--------|----------|---------|
| 0 (healthy)|   1.00    | 1.00   |   1.00   |  18759  |
| 1 (high-risk) |   0.87    | 1.00   |   0.93   |   625 |
| accuracy   |           |        |   1.00   |  19384  |
| macro avg  |   0.94    | 1.00   |   0.96   |  19384  |
| weighted avg |   1.00    | 1.00   |   1.00   |  19384  |

 In addressing the class imbalance by oversampling the data and creating more samples for the minority high-risk loan class we can see that the model performed even better. While the statistics of the healthy loan stayed the same at about 100% precision, recall, and f1 scoring, the high-risk loan identification improved recall and it's f1 score. In other word the model nearly 100% of the time made fewer false positive predictions and can identify the positive instances in the model. The recall improved by 0.11 and the f1 score rose .06. The overall metrics improved as well reaching higher accuracy, macro avg, and weighted average. Overall the oversampled data classification report showed significant improvement in predicting high-risk loans with a higher recall and f1-score.
</br>
## Summary

Overall, I would recommend this machine learning model if you are trying to determine if a loan is healthy or high risk. As we saw, the original dataset showed that for a healthy loan the model had 100% precision, 100% recall, and an f1 of 100%. The high risk loan also had high numbers with a precision of 87%, recall of 89% and an f1-score of 88%. The overall accuracy of the model performed excellent with a 99% accuracy. Despite having an imbalanced dataset, once the data was resampled the model continued to perform well in predicting how many positive prediction are correct and the true positive rate. The model's statistics with the oversampling allowed the healthy loan to have 100% precision, recall, and f1-scoring. While the high-risk loanhad 87%, 100%, and 93% respectively, increasing it's recall and f1- score. The overall model accuracy also increased to 100%, meaning the model is nearly almost correct. 