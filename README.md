# Credit_Risk_Analysis
supervised learning
## Project Overview
### In this project, we have a dataset of loan application.With this much of application information, we want to detect the high risk and low risk application. Considering this is binary question, we decided to use logistic regression to make the prediction model. For the sampling method, we decided to take advantage of Over sampling method,under sampling method, and combine sampling method, because of the imbalanced class in our dataset.  The result of of different sampling method is compared to find the best method

## Detail of each method
### 
### Random Over simpling
* balanced_accurary_score : 0.6603423204808787
* confusion matrix 

CT  | P   | N
-----|-----|------
T    |75   | 26
F    |7216 | 9888
 
 
loan_Status |   pre   |    rec   |    spe    |    f1     |  geo    |   iba  |     sup
------------|---------|----------|-----------|-----------|---------|--------|----------
high_risk   |   0.01  |   0.74   |   0.58    |  0.02     | 0.66    |  0.44  |     101
low_risk    |   1.00  |   0.58   |   0.74    |  0.73     | 0.66    |  0.42  |   17104

### Random Over simpling SMOTE
* balanced_accurary_score : 0.6537310478007576
* confusion matrix 

CT  | P   | N
-----|-----|------
T    |63  | 38
F    |5410 | 11694
 
loan_Status |   pre   |    rec   |    spe    |    f1     |  geo    |   iba  |     sup
------------|---------|----------|-----------|-----------|---------|--------|----------
high_risk   |   0.01  |   0.62   |   0.68    |  0.02     | 0.65    |  0.42  |     101
low_risk    |   1.00  |   0.68   |   0.62    |  0.81     | 0.65    |  0.43  |   17104

### Under simpling ClusterCentroids
* balanced_accurary_score : 0.5440120543859812
* confusion matrix 

CT  | P   | N
-----|-----|------
T    |68  | 33
F    |11010 | 7094
 
loan_Status |   pre   |    rec   |    spe    |    f1     |  geo    |   iba  |     sup
------------|---------|----------|-----------|-----------|---------|--------|----------
high_risk   |   0.01  |   0.67   |   0.41    |  0.01     | 0.53    |  0.29  |     101
low_risk    |   1.00  |   0.41   |   0.67    |  0.59     | 0.53    |  0.27  |   17104        
   
   
### Under simpling ClusterCentroids
* balanced_accurary_score : 0.5440120543859812
* confusion matrix 

CT  | P   | N
-----|-----|------
T    |68  | 33
F    |11010 | 7094
 
loan_Status |   pre   |    rec   |    spe    |    f1     |  geo    |   iba  |     sup
------------|---------|----------|-----------|-----------|---------|--------|----------
high_risk   |   0.01  |   0.67   |   0.41    |  0.01     | 0.53    |  0.29  |     101
low_risk    |   1.00  |   0.41   |   0.67    |  0.59     | 0.53    |  0.27  |   17104   
   
### Combination (Over and Under) Sampling SMOTEENN
* balanced_accurary_score : 0.6365938950069001
* confusion matrix 

CT  | P   | N
-----|-----|------
T    |71  | 30
F    |7351 | 9754
 
loan_Status |   pre   |    rec   |    spe    |    f1     |  geo    |   iba  |     sup
------------|---------|----------|-----------|-----------|---------|--------|----------
high_risk   |   0.01  |   0.70   |   0.57    |  0.02     | 0.63    |  0.41  |     101
low_risk    |   1.00  |   0.57   |   0.70    |  0.73     | 0.63    |  0.40  |   17104   

### Ensemble Balanced Random 
* balanced_accurary_score : 0.7885466545953005
* confusion matrix 

CT  | P   | N
-----|-----|------
T    |71  | 30
F    |2153 | 14951
 
loan_Status |   pre   |    rec   |    spe    |    f1     |  geo    |   iba  |     sup
------------|---------|----------|-----------|-----------|---------|--------|----------
high_risk   |   0.03  |   0.70   |   0.87    |  0.06     | 0.78    |  0.60  |     101
low_risk    |   1.00  |   0.87   |   0.70    |  0.93     | 0.78    |  0.62  |   17104 

### Ensemble Easy Ensembler 
* balanced_accurary_score : 0.9316600714093861
* confusion matrix 

CT  | P   | N
-----|-----|------
T    |93  | 8
F    |983 | 16121
 
loan_Status |   pre   |    rec   |    spe    |    f1     |  geo    |   iba  |     sup
------------|---------|----------|-----------|-----------|---------|--------|----------
high_risk   |   0.09  |   0.92   |   0.94    |  0.16     | 0.93    |  0.87  |     101
low_risk    |   1.00  |   0.94   |   0.92    |  0.97     | 0.93    |  0.97  |   17104 

### In those different sampling method, we use same random_state for consistency purpose.

## Conclusion and Recommendation
### In those method of sample, the result of prediction is different, but in our case, we believe the recall or sensitivity of the model is the most important. we don't want overstate the important of precision, because in that aspect our model would lead us to some false positives. Based on this criterion, our candidate is Easy Ensemble sampling method which has very high accuracy_score, the most important one is the recall of this method is very high that gives us higher precentage of time geting real fraud.
   
