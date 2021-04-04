# Credit Risk Analysis

In this analysis, we review the likelihood of a borrower defaultingo on a loan. Using several variables as inputs, we test several sampling and classification techniques to find the best predictor. For each method, we rely on three key metrics. 

**Precision**
<br>
**Sensitivity (aka 'Recall')**
<br>
**Accuracy**

These metrics bear some explanation, especially since precision and accuracy are nearly interchangeable in everyday speech.

```Precision``` is the likelihood of the test correctly predicting binary outcomes i.e default vs non-default. 
**Formula: (True Positive / (True Positive + False Positive))**

```Sensitivity``` is the likelihood of test correctly identifying *each outcome correctly*. 
**Formula: (True Positive / (True Positive + False Negative)**

```Accuracy``` is the likelihood of the test correctly predicting both outcomes. 
**Formula: (True Postive + True Negative / (True Positive + False Positive + False Negative + True Negative))**

#

We have to keep in mind the subject matter, credit risk. It's much, much riskier for a bank to approve a loan to someone who will default than to deny a loan to someone who will not default. Think of the possible outcomes like this. 


```True Positive:``` Correctly predict that the person is high risk and deny loan.

```False Negative:``` Incorrectly predict that the person is low risk and approve the loan. (very dangerous)

```False Positive:``` Incorrectly predict that the person is high risk and deny the loan. 

```True Negative:``` Correctly predict that the person is low risk and approve the loan. 


For a bank, the loss of income on a loan default vastly outweighs the revenue lost by not approving those who would repay the loan. For this reason the recall metric i.e 'sensitivity' is more important that precision and when we evaluate each method of prediction, we pay closer attention to the recall. 

#

[Sampling Results Here](https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/credit_risk_resampling.ipynb)
<br>
[Classification Results Here](https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/credit_risk_ensemble.ipynb)
#

### Tools Used
- [x] Python (Pandas)

#

## Results 1: Naive Random Oversampling

In this method, we simply oversample members of the minority class until they reach parity with the majority class. The accuracy, nearly 64% is the better than the three other samplers, but still not great. As for it's recall of high risk loan applicants, it's only 0.59, meaning 41% of high risk applicants are receiving a loan. That's not good. 

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/RNS_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/RNS_Classification_Report.png">

## Results 2: SMOTE Oversampling

Using the Synthetic Minority Oversampling Technique (SMOTE) we oversample members of the minority class, but instead of merely selecting minority-class data points multiple times until the two class reach parity, we interpolate new data points of the minority data class. With this method we achieve similar results, 62% accuracy and low recall of the false negatives. 41% of the high risk applicants are receiving a loan in this model as well. 

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/SMOTE_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/SMOTE_Classification_Report.png">

## Results 3: Cluster Centroids Undersampling

In this method we undersample the majority class, but not randomly. The data points that we do pick from the majority class are from clusters within the majority class. However, this technique fares very poorly. It's accuracy is barely above random chance at a dismal 51%. Not only is its recall of high risk applicants low (0.59), it's recall of low risk applicants is even lower at 0.44. That means this model rejects more than half of the people who actually would pay back the loan. 

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/CCluster_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/CCluster_Classification_Report.png">

## Results 4: SMOTEENN Combo Sampling

This technique is a combination of oversampling and undersampling. The oversampling comes from the SMOTE technique, as described earlier, the undersampling comes from a technique known as 'Edited Nearest Neighbors' or EEN. With EEN, if a data point's two nearest neighors belong to the opposite class, the data point is dropped. This works to sharpen the distinctions between the two classes. Using SMOTEENN we have an accuracy score of 63.1 and a recall of high_risk applicants of 0.70, meaning 30% of high risk applicants are approved. While this is better than the other resampling techniques, this is hardly spectacular.

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/SMOTEENN_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/SMOTEENN_Classification_Report.png">

## Results 5: Balanced Random Forest Classifier

With this technique we don't resample at all. Whereas the previous four techniques all resample the data and run a logistic regression classifier, this technique doen't resample but used a Balanced Random Forest Classifier. This technique replaces the standard decision tree used in a simple logistic regression, with a series of smaller decision trees. While the mechanics of this are a little complicated, this technique proves to be resilient against overfitting, runs efficiently on large data sets and handles outliers easily. Not surprisingly, it's accuracy is much higher than previous examples at 79%. However, its recall for high risk loan applicants is still uncomfortably low at 67% meaning, 33% of high risk loan applicants are still receiving a loan which they will ultimately default on. 

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/BRFC_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/BRFC_Classification_Report.png">

## Results 6: AdaBooster Classifier

In this technique, we run an Adaptive Boosting technique, which is a bit complicated, but essentially runs a series of predictions in sequence and each prediction learns from the previous one, i.e gives extra weight to the errors. While each learning model (i.e prediction) may be individually weak, when run together in this way they prove to be quite powerful. Unsurprisingly the accuracy score is much higher, at 93% and its recall for high risk loan applicants is higher as well, at 92%, meaning only 8% of high risk applicants are receiving a loan. 

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/AdBC_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/AdBC_Classification_Report.png">

## Summary

### Recommendation
