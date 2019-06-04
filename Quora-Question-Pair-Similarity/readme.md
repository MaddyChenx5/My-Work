Quora Question Pair Similarity Case Study:

In this case study we have taken dataset from Kaggle. The problem is to predict where given questions are similar or not.

Some Constrains and objectives:

-> Cost of mis clssification is very high. -> Need prbability of duplicacy/similarity of questions. -> No strict low latency requirement. -> Interpretability is partially important.

Performance Metric:

We will be using log-loss and binary confusion matrix in thic case.

Train and test Split is random i.e. not in any chronological order.(70:30 ratio)

** As a part of EDA:

Checking for nulls.
Class comparison
Duplicate check.
As it is a text dataset so needs some preprocessing:

-> Removal of HTML tags. -> Removal of puntuations. -> Stemming -> Removal of stopwrds. -> Expansion of contractions i.e (% to percent, 've to have etc.)

** Some feature extractions:

Common word count,stop word count, token count, last/first word equality, length difference. Used TFIDF W2v to vectorize the data. Some advance features: Fuzzy ratio, Fuzzy partial ratio, Token Sort ratio, Token Set Ratio, edit distance, Longest substring ratio.

Also performed feature analysis using TSNE.

First build a random model and computed the log loss so as to know the worst performance.

We are using Logistic Regression as we need probability in this case and medium dimensions are there. And as there is log loss calibration is required.

We also trained Linear SVM and XGboost model for the above problem.