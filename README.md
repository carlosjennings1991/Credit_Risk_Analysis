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

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/RNS_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/RNS_Classification_Report.png">

## Results 2: SMOTE Oversampling

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/SMOTE_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/SMOTE_Classification_Report.png">

## Results 3: Cluster Centroids Undersampling

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/CCluster_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/CCluster_Classification_Report.png">

## Results 4: SMOTEENN Combo Sampling

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/SMOTEENN_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/SMOTEENN_Classification_Report.png">

## Results 5: Balanced Random Forest Classifier

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/BRFC_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/BRFC_Classification_Report.png">

## Results 6: AdaBooster Classifier

<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/AdBC_Accuracy_Score.png">
<img src="https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/AdBC_Classification_Report.png">

## Summary

### Recommendation
