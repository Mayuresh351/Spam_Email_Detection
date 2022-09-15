# Spam EMail Detection

With the ever increasing connectivity in this growing world, the problem of spamming due to marketing and phishing activities are becoming a major concern. In order to tackle this, the modern Email service providers provide a feature of spam detection which filters out potentially harmful emails without affecting our main inbox. This project is an attempt to imitate the same feature by implementing the machine learning algorithm. 

## Table of Contents
* [Description](#description)
* [Important Code Snippets with Explanation](#important-code-snippets-with-explanation)
* [Final Results](#final-results)
* [Future Developments](#future-developments)

## Description
This Project will use **Support Vector Machine** Algorithm for the classification of the dataset. The dataset could be found in this [Kaggle Link](https://www.kaggle.com/datasets/studymart/spam-email-detection-dataset). 

### Support Vector Machines
It is a popular Supervised Machine Algorithm used for Classification as well as Regression Problems. There are two types of SVM:
1. Linear SVM
2. Non-Linear SVM

As our dataset has to be classified into two classifications, i.e., spam or nor spam, we use Linear SVM for this problem.

### TfIDFVectorizer
It is a Sklearn Feature_Extraction functionto convert the data into matrix of TF IDF.

## Important Code Snippets with Explanation
```
data_withoutNull = initial_data.fillna('')
```
The above code removes the null data from the data set.


```
(X_train, X_test, Y_train, Y_test) = train_test_split(X, Y, test_size = 0.15, random_state = 2)
```
This line of code splits the data into training and test data set. 15% data is converted into test data set and the rest is converted into training data set.

```
feature_extraction = TfidfVectorizer(min_df = 1, stop_words='english', lowercase='true')
```
Converts the data into tf idf features.

```
X_train_features = feature_extraction.fit_transform(X_train)
X_test_features = feature_extraction.transform(X_test)
```
Converts the data into a form that could fit in the SVM Model.

## Final Results
At the end, the test accuracy for the SVM model was achieved greater than 93%.

## Future Developments
The above accuracy could be improved by altering the test train data set ratio and by using various other algorithm. 
Further this ML model could be deployed on a chrome extension which could give live result whether the mail is spam or no.