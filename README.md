# CreditCardFraudDetection_MastersThesis

📘 Overview
This notebook presents the implementation and analysis for my Master’s thesis, which focuses on detecting credit card fraud using machine learning techniques. The project involves feature engineering, preprocessing, and model evaluation on a large, real-world dataset of financial transactions.

The dataset used for this study is an open-source dataset available on Kaggle, containing synthetically generated credit card transactions labeled as fraudulent or legitimate.

📂 Dataset
Source: [Kaggle – Synthetic Financial Dataset For Fraud Detection](https://www.kaggle.com/datasets/kartik2112/fraud-detection/data)

Files Used: fraudTrain.csv and fraudTest.csv

Observations: Contains transaction features such as category, amount, time, location, age, and gender along with a fraud label.

📊 Exploratory Data Analysis (EDA)
The EDA focused on understanding the dataset structure and preparing the data for model building:

Key Steps:
Datetime parsing: Converted trans_date_trans_time and dob to datetime objects.

Age feature creation: Derived the customer's age at the time of transaction.

Time features: Extracted hour, day, and weekday to analyze temporal fraud patterns.

Age binning: Created two categorical age bins (age_group and age_bin_5) to capture demographic patterns.

Missing value handling: Filled NA values in categorical fields with 'missing'.

Observations:
The dataset shows class imbalance with far fewer fraud cases than legitimate transactions.

Time and age features may provide meaningful signals when combined with transaction metadata like category or merchant.

⚙️ Implementation

Preprocessing:
Dropped personally identifiable information (PII) like cc_num, names, address, and unix_time.
Categorical encoding: Converted categorical columns (e.g., merchant, category, gender) to string types and handled missing values.
Class balancing: Used SMOTE (Synthetic Minority Oversampling Technique) to handle class imbalance in the training data.
Feature scaling: Applied StandardScaler to normalize numerical features like transaction amount.
Feature Engineering:
Added columns:age, hour, day, weekday

Binned age into groups using custom intervals for age_group and age_bin_5.

Models Used:
Logistic Regression, Random Forest Classifier, XGBoost Classifier

Each model was trained on the processed training set and evaluated using:

Accuracy

Precision

Recall

F1-score

ROC-AUC Score

Confusion Matrix

Cross-validation using StratifiedKFold

Evaluation focused on Recall and F1-score due to the importance of detecting minority fraud cases.
