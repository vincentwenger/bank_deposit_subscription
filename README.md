# Will the client subscribe a term deposit?

**Assignment notebook:** https://github.com/vincentwenger/bank_deposit_subscription/blob/main/prompt_III.ipynb

## What is the problem?
The goal is to predict if a client will subscribe a term deposit at the bank, which is a classification task.
The target variable is the column "y" of the original dataset : "has the client subscribed a term deposit?(binary: 'yes','no')". The input variables are all the other columns of the original dataset.
Since the target variable is binary (yes/no), this will be a binary classification problem.

## What is the data?
The data is a dataset related to the marketing of bank products over the telephone. It comes from the UC Irvine Machine Learning Repository.
The data is from a Portuguese banking institution and is a collection of the results of multiple marketing campaigns. 
The dataset collected is related to 17 campaigns that occurred between May 2008 and November 2010, corresponding to a total of 79354 contacts.
It contains 41188 rows and 21 columns.

## What are the findings?

The findings are that :
- After checking how imbalanced is the Output variable, we could see that about 11% of the desired target class is yes so the class is imbalanced
- In the data, for original fields default, housing, loan, y, we could consider changing the datatype of the columns to boolean since those are binary columns. We would need to default value "unknow" to "no"
- For original fields month and day_of_week we could consider changing the datatype to integer after converting the values to integer
- We were able to create a baseline model using a DummyClassifier which has strategy "most frequent". Therefore all its predictions were "no". It had a test accuracy around 88%, and a test recall and test F1 of 0%
- We were able to create 4 other models using K nearest Neighbors (KNN), Logistic Regression, Decision trees and Support Vector Machine (SVM), using the default settings for each of the models. When we compare the 4 models, we can see that KNN, Logistic Regression and Decision Tree are all fast in term of train time. SVC is a bit slower. Regarding train accuracy, the Decision Tree model has the best performance with a train accuracy of 100%. The other 3 models are quite similar with a train accuracy around 91 or 92%. Regarding test accuracy, the Logistic Regression model and SVC model seem to have the best performance with a test accuracy close to 91%. 2nd is KNN model with test accuracy of 89.7% and last is the decision tree with test accuracy of 88.9% If I had to pick one model, I would probably pick the logistic regression because it is fast to train and has one of the best test accuracy. Also we noticed that all those models beat our baseline model performance.
- We were able to improve all above 4 models, using hyperparameter tuning and grid search. We also adjusted the performance metric. We used for GridsearchCV a scoring "accuracy" and then a scoring "f1". Since the class is imbalanced, we try to use the performance metric F1 because it is more informative than simple accuracy
- Regarding the 4 improved models, we noticed that all those improved models beat our baseline model performance. In term of test accuracy, the best improved model is the Decision Tree model with performance metric : accuracy. In term of test recall, the best improved model is the Logistic Regression model with performance metric : f1. In term of test F1, the best improved model is the Decision Tree model with performance metric : f1. In term of train time, the best improved model is the Decision Tree model which is the fastest. The models with SVM are the slowest to train

## What do I recommend?

- Since we saw earlier that the output class is imbalanced, it could be better to use the performance metric F1 as it is more informative than simple accuracy in that case
- I would recommend to choose the Decision Tree improved model with performance metric : f1. It is also one of the fasted model to train. The train time is about 6 seconds. The hyperparameters are : criterion = gini and max_depth = 3. The train accuracy is 90.86%, the test accuracy is 90.89%, the test recall is 59.14% and the test F1 is 59.59%
