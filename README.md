# Credit Risk Analysis

In this analysis, we review the likelihood of a borrower defaultingo on a loan. Using several variables as inputs, we test several sampling and classification techniques to find the best predictor. For each method, we rely on three key metrics. 

**Precision**
<br>
**Sensitivity (aka 'Recall')**
<br>
**Accuracy**

These metrics bear some explanation, especially since precision and accuracy are nearly interchangeable in everyday speech.

```Precision``` is the likelihood of the test correctly predicting binary outcomes i.e default vs non-default. 
Formula: (True Positive / (True Positive + False Positive))

```Sensitivity``` is the likelihood of test correctly identifying *each outcome correctly*. 
Formula: (True Positive / (True Positive + False Negative)

```Accuracy``` is the likelihood of the test correctly predicting both outcomes. 
Formula: (True Postive + True Negative / (True Positive + False Positive + False Negative + True Negative))

#

[Sampling Results Here](https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/credit_risk_resampling.ipynb)
<br>
[Classification Results Here](https://github.com/carlosjennings1991/Credit_Risk_Analysis/blob/main/credit_risk_ensemble.ipynb)
#

### Tools Used
- [x] Python (Pandas)

#

## Results 1: Naive Random Oversampling

## Results 2: SMOTE Oversampling

## Results 3: Cluster Centroids Undersampling

