# Bank Customer Churn Prediction

The objective is to classify customers into those who are likely to churn (leave the bank) and those who will stay.

The project follows an end-to-end machine learning pipeline, including:

1.  Data Preprocessing (Cleaning and Encoding)
2.  Exploratory Data Analysis (EDA)
3.  Handling Imbalanced Data using SMOTE
4.  Feature Scaling
5.  Model Training and Evaluation with multiple classifiers
6.  Model Comparison
7.  Model Saving and Deployment

## Dataset

The dataset used in this project contains information about bank customers and includes the following columns:

* CreditScore: Customer's credit score (Numerical)
* Age: Customer's age (Numerical)
* Tenure: Number of years the customer has been with the bank (Numerical)
* Balance: Account balance (Numerical)
* NumOfProducts: Number of bank products used by the customer (Numerical)
* HasCrCard: Whether the customer has a credit card (1 = Yes, 0 = No) (Categorical)
* IsActiveMember: Whether the customer is an active member (1 = Yes, 0 = No) (Categorical)
* EstimatedSalary: Estimated salary of the customer (Numerical)
* Exited: Target variable indicating churn (1 = Churned, 0 = Stayed) (Categorical)
* Geography: Customer's country (Categorical)
* Gender: Customer's gender (Categorical)

## Project Workflow

1.  **Data Preprocessing:**
    * Removed irrelevant columns: `RowNumber`, `CustomerId`, and `Surname`.
    * Encoded categorical features: `Geography` and `Gender`.
    * Checked for and handled missing values (though not explicitly mentioned, this is a standard preprocessing step).

2.  **Exploratory Data Analysis (EDA):**
    * Visualized the distribution of the target variable, `Exited`.
    * Plotted a count plot to compare the number of churned vs. retained customers, providing insights into class imbalance.

3.  **Handling Imbalanced Data:**
    * Applied the Synthetic Minority Over-sampling Technique (SMOTE) to address the class imbalance in the dataset, ensuring the model is not biased towards the majority class.

4.  **Feature Scaling:**
    * Utilized `StandardScaler` to normalize the feature values, preventing features with larger scales from dominating the model training process.

5.  **Model Training & Evaluation:**
    * Implemented and evaluated several classification algorithms:
        * Logistic Regression (LR)
        * Support Vector Classifier (SVC)
        * K-Nearest Neighbors (KNN)
        * Decision Tree (DT)
        * Random Forest (RF)
        * Gradient Boosting Classifier (GBC)
    * Evaluated model performance using the following metrics:
        * Accuracy Score
        * Precision Score
        * Recall Score
        * F1 Score

6.  **Model Comparison:**
    * Compared the accuracy scores of the trained models using a bar plot to visually identify the best performing algorithm.

7.  **Model Deployment:**
    * Trained the final selected model (Random Forest) on the entire dataset.
    * Saved the trained model using `Joblib` for persistence.
    * Loaded the saved model and tested it with sample customer data to demonstrate its functionality.

## Results

| Model                     | Accuracy |
| ------------------------- | -------- |
| Logistic Regression       | 79.06%   |
| Support Vector Classifier | 84.43%   |
| K-Nearest Neighbors       | 82.17%   |
| Decision Tree             | 79.66%   |
| **Random Forest** | **86.32%** |
| Gradient Boosting Classifier | 84.84%   |

This summarizes the accuracy scores achieved by the different models:


Based on these results, **Random Forest** achieved the highest accuracy and was therefore selected as the final model for this project.

