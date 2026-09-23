# Customer Churn Prediction

A machine learning project that predicts whether a telecom customer is likely to churn using Logistic Regression and Random Forest.

## Project Overview

Customer churn prediction is a binary classification problem where the model predicts whether a customer will leave a service.

This project uses the IBM Telco Customer Churn dataset and follows a complete machine learning workflow:

1. Load and inspect the dataset
2. Clean the data
3. Analyze customer churn
4. Encode categorical features
5. Split data into training and testing sets
6. Train Logistic Regression
7. Train Random Forest
8. Evaluate both models
9. Analyze feature importance
10. Visualize model results

## Dataset

The project uses the Telco Customer Churn dataset containing customer demographic, service, contract, billing, and churn information.

After cleaning, the dataset contains **7,032 customer records** and **21 original columns**.

The target variable is:

- **Churn = No** → customer stayed
- **Churn = Yes** → customer left

## Data Preparation

- Removed `customerID` because it is an identifier rather than a predictive feature.
- Converted `TotalCharges` from text to numeric.
- Removed 11 rows with missing `TotalCharges` after conversion.
- Converted categorical variables into numerical dummy variables.
- Used an 80/20 train-test split with stratification.

Final split:

- Training: **5,625 records**
- Testing: **1,407 records**
- Model input features after encoding: **30**

## Models

### Logistic Regression

Results from the test set:

| Metric | Score |
|---|---:|
| Accuracy | 80.45% |
| Precision | 64.86% |
| Recall | 57.75% |
| F1 Score | 61.10% |

### Random Forest

Results from the test set:

| Metric | Score |
|---|---:|
| Accuracy | 78.96% |
| Precision | 62.58% |
| Recall | 51.87% |
| F1 Score | 56.73% |

These values are the results obtained from the notebook's test-set evaluation.

## Feature Importance

The Random Forest model's top features by importance were:

1. TotalCharges
2. tenure
3. MonthlyCharges
4. InternetService_Fiber optic
5. PaymentMethod_Electronic check
6. Contract_Two year
7. gender_Male
8. OnlineSecurity_Yes
9. PaperlessBilling_Yes
10. TechSupport_Yes

Feature importance indicates how the trained Random Forest model used the features for prediction; it does not by itself establish causation.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab
- GitHub

## Project Workflow

```text
Telco Customer Data
        ↓
Data Cleaning
        ↓
Categorical Encoding
        ↓
Train/Test Split
        ↓
 ┌───────────────────────┐
 │                       │
Logistic Regression   Random Forest
 │                       │
 └───────────┬───────────┘
             ↓
     Model Evaluation
             ↓
 Accuracy / Precision
 Recall / F1 Score
             ↓
   Feature Importance
```

## Project File

- `Customer_Churn_Prediction.ipynb` — complete Google Colab notebook containing data preparation, analysis, model training, evaluation, and visualizations.

## Future Improvements

- Hyperparameter tuning
- Cross-validation
- Class imbalance handling
- ROC-AUC analysis
- Model deployment using Flask or FastAPI
- Interactive churn prediction dashboard

## Author

**Purnitha Kalluri**

B.Tech Artificial Intelligence and Machine Learning  
Saveetha School of Engineering

LinkedIn: https://www.linkedin.com/in/purnithakalluri
