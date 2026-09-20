# Customer Churn Prediction

A machine learning project for predicting customer churn using the Telco Customer Churn dataset.  
The goal of this project is to analyze customer behavior, identify factors associated with churn, and build classification models to predict customers who are likely to leave the service.

---

## Project Overview

Customer churn prediction is an important problem for subscription-based businesses because retaining existing customers is often more cost-effective than acquiring new ones.

This project follows a complete machine learning workflow:

- Data loading and exploration
- Data cleaning and preprocessing
- Exploratory data analysis (EDA)
- Feature engineering
- Model training
- Model comparison
- Feature importance analysis
- Saving trained models and evaluation reports

---

## Dataset

The project uses the **Telco Customer Churn Dataset** containing information about 7,043 customers.

The dataset includes:

- Customer demographics
- Account information
- Service subscriptions
- Payment methods
- Monthly and total charges
- Customer churn status

Target variable:

```
Churn
```

where:

- `No` → Customer stayed
- `Yes` → Customer left the service

---

## Data Preprocessing

The following preprocessing steps were applied:

- Removed missing values caused by empty `TotalCharges` entries
- Converted `TotalCharges` from object to numeric format
- Encoded categorical variables using one-hot encoding
- Removed `customerID` because it does not provide predictive information
- Split data into training and testing sets

Final processed dataset:

- Samples: 7,032
- Features after encoding: 30

Train-test split:

- Training set: 5,625 samples
- Test set: 1,407 samples

---

## Exploratory Data Analysis

Key observations from the analysis:

- Overall churn rate:

  - No churn: 73.46%
  - Churn: 26.54%

- Customers with shorter tenure showed higher churn rates.
- Month-to-month contracts had a higher churn proportion compared with longer contracts.
- Fiber optic internet customers showed higher churn compared with other internet service categories.
- Customers with lower total tenure and higher monthly charges were more likely to churn.

---

## Machine Learning Models

Four classification models were trained and evaluated:

1. Logistic Regression
2. Logistic Regression with class balancing
3. Random Forest
4. Gradient Boosting

Evaluation metrics:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

---

## Model Results

| Model | Accuracy | Churn Recall | Churn F1-score |
|---|---:|---:|---:|
| Logistic Regression | 0.8038 | 0.5722 | 0.6080 |
| Logistic Regression Balanced | 0.7264 | 0.7968 | 0.6075 |
| Random Forest | 0.7719 | 0.6604 | 0.6061 |
| Gradient Boosting | 0.7960 | 0.5294 | 0.5798 |

The models show different trade-offs between overall accuracy and detecting churn cases.  
For churn prediction problems, recall is an important metric because identifying potential churn customers can help businesses take preventive actions.

---

## Feature Importance

The most influential features identified by the Gradient Boosting model were:

| Feature | Importance |
|---|---:|
| TotalCharges | 0.1759 |
| tenure | 0.1648 |
| MonthlyCharges | 0.1524 |
| Contract (Two year) | 0.0617 |
| InternetService (Fiber optic) | 0.0392 |
| PaymentMethod (Electronic check) | 0.0377 |

These results indicate that customer loyalty duration, billing information, and contract type play important roles in churn prediction.

---

## Project Structure

```
customer-churn-prediction/

├── data/
│   ├── raw/
│   └── processed/

├── models/
│   └── gradient_boosting_churn_model.pkl

├── notebooks/
│   ├── 03_data_exploration_new.ipynb
│   └── 04_model_training_new.ipynb

├── reports/
│   ├── model_comparison.csv
│   └── feature_importance.csv

├── src/
├── tests/
├── docs/
└── README.md
```

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook
- Git & GitHub

---

## Future Improvements

Possible future improvements include:

- Hyperparameter optimization
- Cross-validation
- Additional ensemble models
- Model explainability using SHAP
- Deployment as a prediction API

---

## Author

Anahita Alhouei

Machine Learning / Artificial Intelligence Project