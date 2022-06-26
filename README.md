# Credit_Risk_Analysis

## Overview
THe purpose of this exercise was to utilize different supervised machine learning models and determine which best predicted credit risk by classifying a potentional borrower as "high risk" or "low risk".  Determining success of each model will rest on the results of the balanced accuracy, precision, and recall scores.

## Results
As a standard, I used the test_train_split function in the same way for each model to ensure each model was tested on the same sample parameters.

### Naive Random Oversampling
The first model, Naive Random Oversampling, gave us a balanced accuracy score of 0.6547.  The precision varies wildly between the two groups (with high risk at 0.01 and low risk at 1.00), and the recall sees a drop in the low_risk group, as can be seen below:

<img width="678" alt="naive_random_oversampling_report" src="https://user-images.githubusercontent.com/99457275/175836917-9f8780bf-d516-48c2-8515-4c7c4fb96b60.png">

### SMOTE
The second model, SMOTE oversampling, saw a similar issue with precision.  However, the recall was closer beetween the two groups, with low-risk having slightly better recall at 0.69 vs 0.63 bfor the high risk group.   The balanced accuracy score was 0.662.

<img width="679" alt="smote_report" src="https://user-images.githubusercontent.com/99457275/175836996-0d86dcc1-8c21-4327-98f5-f8b6604644c2.png">

### Cluster Centroids
The third model was ClusterCentroids.  The balanced accuracy score was lower, at 0.5447.  The precision was the same as the previous models.  The recall was lower, with high risk at 0.69, but low risk at 0.40.

<img width="676" alt="cluster_centroids_report" src="https://user-images.githubusercontent.com/99457275/175837200-d8196799-d437-4394-b17e-9bdee5cfe81b.png">

### SMOTEENN
Our fourth method, SMOTEENN had a balanced accuracy score of 0.6473, which is neither the lowest or highest accuracy score.  The precision score was identical to all previous model.  The recall was 0.72 for high risk and 0.57 for low risk.

<img width="636" alt="smoteenn_report" src="https://user-images.githubusercontent.com/99457275/175837301-b007cf68-49de-4edb-ab8f-76fb03dbf158.png">

### Balanced Random Forest Classifier
This model showed improvement in the balanced accuracy score at 0.7885.  Precision was still an issue, but the high risk group was up to 0.03, while the low-risk group stayed at 1.00.  Recall was overall higher, with high risk at 0.70 and low risk at 0.87.

<img width="629" alt="balanced_random_forest_report" src="https://user-images.githubusercontent.com/99457275/175837444-949a4701-79fb-46c6-8173-acafd9545b06.png">

This model also came with ranked features.  The three most important features were 'Total Received Principal'[0.0788], 'Total Payment'[0.0588], and 'total_pymnt_inv'[0.0563].  Below is a list of the top 10 features:

<img width="373" alt="top_10_features" src="https://user-images.githubusercontent.com/99457275/175837638-91cb6398-7dd9-4d12-b4f4-81e9fbe855bc.png">

### Easy Ensemble AdaBoost Classifier
The last model was Easy Ensemble AdaBoost Classifier.  The balanced accuracy score was the strongest at 0.9317.  The precision also was the highest, as the high risk group was up to 0.09, while the low risk group was steady at 1.00.  The recall was also the best of any model.  High risk came in at 0.92, while low risk was 0.94.  

<img width="628" alt="easy_ensemble_report" src="https://user-images.githubusercontent.com/99457275/175837757-bf060577-f39b-4b7b-b6c4-a8f2b2b6626a.png">

## Summary
Overall, the Easy Ensemble AdaBoost model was the strongest, with the best numbers across the board.  This suggests that the Easy Ensemble method was the best option, with very strong scores, and is my recommendation for this data.  With regards to important features, it would be prudent not to give out extremely large loans, as principal and payment were the most important factors from an otherwise-solid Balanced Random Forest model.
