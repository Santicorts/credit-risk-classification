# credit-risk-classification


In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis:

    ANS: to build a machine learning model to predict loan risk. Specifically, the models aim to distinguish between healthy loans (0) and high-risk loans (1) to help financial institutions assess the risk associated with each loan application and make informed decisions
* Explain what financial information the data was on, and what you needed to predict.

    ANS: The dataset contains financial information related to borrowers and their loan details. Key features include:
    - interest_rate: The interest rate of the loan.
    - borrower_income: The annual income of the borrower.
    - debt_to_income: The ratio of the borrower’s total monthly debt payments to their monthly gross income.
    - num_of_accounts: The number of credit accounts the borrower has.
    - derogatory_marks: The number of derogatory marks on the borrower’s credit history.
    - total_debt: The total debt of the borrower.
    - loan_size: The size of the loan being applied for.

The target variable we need to predict is loan_status, which indicates whether a loan is a healthy loan (0) or a high-risk loan (1)

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).

    ANS: The variable to predict is loan_status:
    - 0: Healthy loan, where the borrower is likely to repay without issues.
    - 1: High-risk loan, where there is a higher chance of default.
Value Counts of loan_status:

    loan_status
    - 0:    75036 -> MAJORITY
    - 1:     2500 -> MINORITY



* Describe the stages of the machine learning process you went through as part of this analysis.

1. Data Preprocessing:
    - Standardized numerical features to ensure they are on the same scale.
    - Separated the data into features (X) and labels (y).
    - Split the data into training and testing datasets using train_test_split.
2. Model Training:
    - A logistic regression model was instantiated and trained using the training dataset (X_train and y_train).
3. Model Evaluation:   
    - The model’s performance was evaluated using the test dataset (X_test and y_test).
    - Key evaluation metrics such as accuracy, precision, recall, and F1-score were calculated.
    - Confusion matrix and classification report were generated to assess the model’s predictive capabilities.
4. Model Interpretation:
    - Analyzed the confusion matrix and classification report to understand how well the model predicts both healthy and high-risk loans.


* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any other algorithms).

Logistic Regression:

This algorithm was chosen for its simplicity and interpretability, making it a good baseline model for binary classification problems like this one.

## Results

Using bulleted lists, describe the accuracy scores and the precision and recall scores of all machine learning models.
* Machine Learning Model 1: Logistic Regression
    * Accuracy Score:
        - The model achieved an overall accuracy of 99%.
    * Precision and Recall Scores:
        - Healthy Loan (0):
            - Precision: 1.00 (100% of loans predicted as healthy were actually healthy)
            - Recall: 1.00 (100% of actual healthy loans were correctly predicted)
            - F1-Score: 1.00
        - High-Risk Loan (1):
            - Precision: 0.86 (86% of loans predicted as high-risk were actually high-risk)
            - Recall: 0.91 (91% of actual high-risk loans were correctly predicted)
            - F1-Score: 0.88

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:

* Which one seems to perform best? How do you know it performs best?

    ANS: The logistic regression model performed exceptionally well overall, particularly for predicting healthy loans with perfect precision and recall. This suggests it is very reliable in identifying low-risk borrowers.

* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

    ANS: There is a significant class imbalance, with far more healthy loans than high-risk loans. This can lead to inflated accuracy scores and potential underperformance in predicting the minority class (high-risk loans).
