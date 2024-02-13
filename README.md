# Breast Cancer Classification Project

## Problem Statement

The goal of this project is to classify breast cancer using various machine learning techniques, including supervised, semi-supervised, and unsupervised learning. The Breast Cancer Wisconsin (Diagnostic) Data Set is utilized for this classification task.

## Dataset

- Download the dataset from [Breast Cancer Wisconsin (Diagnostic) Data Set](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+ %28Diagnostic%29).
- Direct link to the data: [wdbc.data](https://archive.ics.uci.edu/ml/machine-learning-databases/breast-cancer-wisconsin/wdbc.data).
- The dataset contains IDs, classes (Benign=B, Malignant=M), and 30 attributes.

## Monte-Carlo Simulation

### (a) Data Splitting

- Repeat the following procedures for supervised, unsupervised, and semi-supervised learning M = 30 times.
- Use randomly selected train and test data, ensuring 20% of both positive and negative classes are included in the test set.

### (b) Supervised Learning (L1-penalized SVM)

#### i. Train an L1-penalized SVM

- Use 5-fold cross-validation to choose the penalty parameter.
- Use normalized data.

#### ii. Evaluation Metrics

- Average accuracy, precision, recall, F1-score, and AUC for both training and test sets over M runs.

#### iii. Visualizations

- Plot the ROC curve and report the confusion matrix for training and testing in one of the runs.

### (c) Semi-Supervised Learning/Self-training (L1-penalized SVM)

#### i. Select Labeled Data

- Select 50% of the positive class and 50% of the negative class as labeled data.

#### ii. Train the SVM

- Train an L1-penalized SVM to classify the labeled data using normalized data.

#### iii. Self-Training Loop

- Find the unlabeled data point farthest to the decision boundary.
- Label it (ignore its true label) and add it to the labeled data.
- Retrain the SVM and repeat until all unlabeled data are used.

#### iv. Evaluation Metrics

- Average accuracy, precision, recall, F1-score, and AUC for both training and test sets over M runs.

#### v. Visualizations

- Plot the ROC curve and report the confusion matrix for training and testing in one of the runs.

### (d) Unsupervised Learning (K-Means Algorithm)

#### i. Run K-Means

- Run k-means algorithm on the whole training set (k = 2).

#### ii. Centers and Labels

- Compute the centers of the two clusters.
- Find the closest 30 data points to each center and take a majority poll for labeling.

#### iii. Evaluation Metrics

- Average accuracy, precision, recall, F1-score, and AUC for training data over M runs.
- Classify test data based on proximity to the centers and report metrics.

#### iv. Visualizations

- Plot the ROC curve and report the confusion matrix for training and testing in one of the runs.

### (e) Spectral Clustering

#### i. Run Spectral Clustering

- Utilize spectral clustering with RBF kernel (gamma=1 or find appropriate gamma).
- Use the fit-predict method.

### (f) Comparison of Results

- Compare the results obtained by supervised, semi-supervised, and unsupervised learning methods.

## Conclusion

- Summarize and interpret the results obtained from different learning techniques.
