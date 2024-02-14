# credit-risk-classification
## Supervised Learning Module 20 Challenge
This script contains code that trains and evaluates a model based on loan risk.

### Split the Data into Training and Testing Sets
The code first reads a CSV file containing loan data from the Resources folder and transfers it to a Pandas DataFrame. It then separates the labels and features from the “loan_status” column, using the labels for the y variable (the loan_status column) and the features for the X variable (the rest of the dataframe minus the column). This column only contains 0 and 1 values, using 0 to label a healthy loan and 1 for a high-risk loan.

It then counts the values of the labels, totaling 75,036 '0' values to only 2,500 '1' values. Split the data into training and testing datasets by using train_test_split. A train_test learn module is then imported, and the data is split into training and testing datasets using the train_test_split function, and a random state of 1.

### Create a Logistic Regression Model with the Original Data
The code then creates a logistic regression model and fits it to the training data. It then makes predictions using the testing data.
The model's performance is then evaluated by calculating the accuracy score of the model, generating a confusion matrix, and printing the classification report. From the classification report we are able to see how well does the logistic regression model predicts both the 0 (healthy loan) and 1 (high-risk loan) labels (100% precision for 0 compared to 89% for 1).

### Predict a Logistic Regression Model with Resampled Training Data
Next the code resamples the training data using a RandomOverSampler model and initializes the model with a random state of 1. The old training data is then fitted to the new model. When the values of the labels are counted from the new model, there is now 56,271 values  for 0 and 56,271 for 1, an even count.

Another logistic regression model is then made, using the resampled training data, and new predictions are made. Once again, the accuracy score is calculated, a confusion matrix is made, and the classification report is printed, this time for the new model. This report shows a much more even predictions, with a precision, recall, and F1-score of 99% for both 0 and 1 values. By comparing the two reports, we can see that the model created with the oversampled data predicted the labels better.
