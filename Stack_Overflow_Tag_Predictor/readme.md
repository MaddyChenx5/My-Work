Stack Overflow Tag Predict Case Study:

In this case study the data was taken from Kaggle. As Facebook hosted the competetion on the same. The data has ID,Title , Description and respective Tags. The problem statement for us was to predict the tags when a title and description is given. So this was kind of a multilabel classification task/problem.

The main objective as many tags that suits the title and description. There were no high latency demands but predicting the accurate tags was the main concern as that could affect the users.

The metric used for this was Micro Averaged F1 Score. Precision: Out of all the instances predicted + ve by the model , what percentage is actually positive. (TP/(TP+FP)) Recall: Out of all the positives available in the dataset how many are predicted positive. (TP/(TP+FN)) F1 Score= Combintion of Precision and Recall.

If in any probelm we need high precision and recall F1 score is optimal metric. [2((PrecisionRecall)/(Precision+recall))]

Micro Averaged F1 Score : Giving weightage to tags on the basis of their occurence/frequency.

We have used SQLITE for this case study as this is widely used and python has inbuild API for the same.

As a part of EDA we counted for number of rows , checked for duplicates, unique tags with their frequency etc. As a part of data preprocessing I removed HTML tags, seperated code from the body, removed special chracterd from title and decription, removed stopwords, used snowball stemmer to stem the data and converted all the characyers to lowercase.

For featurization we used TFIDF upto 4grams. And test train spilt we choose to be 80:20.

As this is multi label problem and so we used classifier chains to predict the tags. For this problem we used Logistic Regression with One Vs Rest as a classifier because LR is fast and works gread with high dimensional data as its runtime complexity os O(d).

For speeding up the process I used partial coverage that is took only top tags. And for improving performnce I gave Title more weightage(3 times).