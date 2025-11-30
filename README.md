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

## What do I recommend?

- It is better to buy white cars
- We recommend to install a car dealership un Utah as we will be able to make more money selling cars
- It is better to buy more full size pick-ups with 4wd drive, with as many cylinders as possible
- It is recommended to buy new car working with diesel 
