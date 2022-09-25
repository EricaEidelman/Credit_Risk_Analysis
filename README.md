# Supervised Machine Learning and Credit Risk

## Project Overview
The purpose of the project is to evaluate a set of machine learning models used to predict credit risk. Four of the models use resampling techniques - RandomOverSampler, SMOTE, ClusterCentroids, and SMOTEENN - and the other two - BalancedRandomForestClassifier and EasyEnsembleClassifier - are meant to improve the performance of individual weak learners by combining their learnings.

## Resources
Data Source: LoanStats_2019Q1.csv

Software: Python 3.7.6

## Results
For all six models, balanced accuracy, precision, and recall scores were found. Because the size of the classes in the data was unbalanced to start with - there were more low-risk than high-isk loans - the balanced accuracy score was found, which takes the average of the accuracy in identifying members of either class. The precision score shows how well the model identifies actual positives out of all the items it classifies as positive. The recall score shows how well the model identifies actual positives out of all the actual positives that exist. The results are summarized below.

- The RandomOverSampler had a balanced accuracy score of 0.6610, a precision of 0.01 for high-risk loans and 1.00 for low-risk loans, and a recall of 0.71 for high-risk loans and 0.61 for low-risk loans. This means that out of all the loans classified as high-risk 1% actually were high-risk, and also that the model correctly identified 71% of all the high-risk loans actually in the test data. Likewise, out of all the loans classified as low-risk almost all actually were, and also the model correctly idenytified 61% of all the low-risk loans in the test data. The image below summarizes the results for the RandomOverSampler.

![This is an image](https://github.com/EricaEidelman/Credit_Risk_Analysis/blob/main/Random_Oversampling.png)

- The SMOTE had a balanced accuracy score of 0.6549, a precision of 0.01 for high-risk loans and 1.00 for low-risk loans, and a recall of 0.63 for high-risk loans and 0.68 for low-risk loans. This means that out of all the loans classified as high-risk 1% actually were high-risk, and also that the model correctly identified 63% of all the high-risk loans actually in the test data. Likewise, out of all the loans classified as low-risk almost all actually were, and also the model correctly idenytified 68% of all the low-risk loans in the test data. The image below summarizes the results for the SMOTE.

![This is an image](https://github.com/EricaEidelman/Credit_Risk_Analysis/blob/main/SMOTE.png)

- The ClusterCentroids had a balanced accuracy score of 0.5301, a precision of 0.01 for high-risk loans and 1.00 for low-risk loans, and a recall of 0.67 for high-risk loans and 0.39 for low-risk loans. This means that out of all the loans classified as high-risk 1% actually were high-risk, and also that the model correctly identified 67% of all the high-risk loans actually in the test data. Likewise, out of all the loans classified as low-risk almost all actually were, and also the model correctly idenytified 39% of all the low-risk loans in the test data. The image below summarizes the results for the ClusterCentroids.

![This is an image](https://github.com/EricaEidelman/Credit_Risk_Analysis/blob/main/Undersampling.png)

- The SMOTEENN had a balanced accuracy score of 0.6565, a precision of 0.01 for high-risk loans and 1.00 for low-risk loans, and a recall of 0.74 for high-risk loans and 0.57 for low-risk loans. This means that out of all the loans classified as high-risk 1% actually were high-risk, and also that the model correctly identified 74% of all the high-risk loans actually in the test data. Likewise, out of all the loans classified as low-risk almost all actually were, and also the model correctly idenytified 57% of all the low-risk loans in the test data. The image below summarizes the results for the SMOTEENN.

![This is an image](https://github.com/EricaEidelman/Credit_Risk_Analysis/blob/main/Combination.png)

- The BalancedRandomForestClassifier had a balanced accuracy score of 1.0, a precision of 1.00 for high-risk loans and 1.00 for low-risk loans, and a recall of 1.00 for high-risk loans and 1.00 for low-risk loans. This means that the model correctly predicted the status of every single loan in the test data set. The image below summarizes the results for the BalancedRandomForestClassifier.

![This is an image](https://github.com/EricaEidelman/Credit_Risk_Analysis/blob/main/Balanced_Random_Forest.png)

- The EasyEnsembleClassifier had a balanced accuracy score of 1.0, a precision of 1.00 for high-risk loans and 1.00 for low-risk loans, and a recall of 1.00 for high-risk loans and 1.00 for low-risk loans. This means that the model correctly predicted the status of every single loan in the test data set. The image below summarizes the results for the EasyEnembleClassifier.

![This is an image](https://github.com/EricaEidelman/Credit_Risk_Analysis/blob/main/Ensemble_ADA_Forest.png)

## Summary
In summary, the two ensemble machine learning models showed a 100% accuracy on the test data set. The ClusterCentroids had the worst balanced accuracy score at about 53%, and the remaining three models all had about 65-66% balanced accuracy. All four resampling models had nearly 100% success in precision for low-risk loans, but that was mainly due to the extreme imbalance in classes (101 high-risk loans compared to 17,104 low-risk loans in the test data). All four models also had a precision of 0.01 for high-risk loans, which indicates a lot of low-risk loans being flagged as high-risk. The recall for high-risk loans was the best for SMOTEENN at 0.74, followed by RandomOverSampler (0.71), ClusterCentroids (0.67), and SMOTE (0.63). For low-risk loans, recall was the best for SMOTE at 0.68, followed by RandomOverSampler (0.61), SMOTEENN (0.57), and ClusterCentroids (0.39).

While the two ensemble learning models had 100% accuracy and it might seem tempting to select either of them to use, the 100% accuracy can be thought of as somewhat suspicious. The models may be overfitting, and it would be worthwile to test them again removing some of the features used to train the models before deciding to use them. The two models best to use would be SMOTEENN and RandomOverSampler. Not only did these two models have the highest balanced accuracy scores of all the resampling models, but they also had the highest recall for high-risk loans. For a lender, it's much more important to be able to flag as many high-risk loans as possible than low-risk, which is why these two models are recommended.
