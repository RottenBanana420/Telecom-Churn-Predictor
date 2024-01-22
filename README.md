
# Telecom Churn Prediction and Analysis

A Python script for predicting and analyzing telecom customer churn. The script covers data preprocessing, exploratory data analysis (EDA), feature engineering, and the implementation of a logistic regression model with Principal Component Analysis (PCA) for dimensionality reduction. The dataset includes information on customer behavior, recharge patterns, and usage metrics. The readme provides an overview of the script, details on each processing step, and insights into model performance metrics. Researchers, data scientists, and telecom industry professionals can utilize this repository for understanding and predicting customer churn patterns.

## Features

The telecom churn prediction and analysis script offer several functionalities, encompassing data preprocessing, exploratory data analysis (EDA), feature engineering, and model training. Here's an overview of the primary functionalities:

### 1. Data Loading and Preprocessing

- The script reads the telecom churn dataset from a CSV file (`telecom_churn_data.csv`).
- Identifies and handles missing values, removing columns with more than 30% missing values.
- Deletes unnecessary date columns and the `circle_id` column.
- Filters high-value customers based on the average recharge amount.

### 2. Handling Missing Values in Rows

- Removes rows with more than 50% missing values, focusing on columns related to MOU (Minutes of Usage) for specific months (June, July, August, September).

### 3. Tagging Churned Customers

- Creates a binary `churn` column based on specific criteria, identifying customers who churned in the last month (September).

### 4. Feature Engineering

- Derives new features related to usage metrics, recharge patterns, ARPU, and VBC.
- Calculates differences and binary indicators to capture changes between different phases (good and action).

### 5. Exploratory Data Analysis (EDA)

- Visualizes churn rates based on various features using bar plots.
- Compares distribution plots for churn and non-churn customers.
- Generates scatter plots to explore relationships between recharge number and amount.

### 6. Train-Test Split and Feature Scaling

- Splits the dataset into training and testing sets.
- Standardizes numeric features using feature scaling.

### 7. Principal Component Analysis (PCA) and Logistic Regression Model

- Applies PCA for dimensionality reduction.
- Performs logistic regression model training using cross-validation with sensitivity as the primary evaluation metric.
- Evaluates model performance on both the training and testing sets.

## Feature Engineering

The script performs feature engineering to derive meaningful features for predicting telecom customer churn. Here are the key features generated:

### Usage Metrics:

- **total_mou_good:** Total Minutes of Usage (MOU) during the good phase (incoming and outgoing).
- **avg_mou_action:** Average MOU during the action phase (months 7 and 8).
- **diff_mou:** Difference between avg_mou_action and total_mou_good.
- **decrease_mou_action:** Binary indicator (1 or 0) for whether MOU decreased in the action phase.

### Recharge Metrics:

- **avg_rech_num_action:** Average recharge numbers during the action phase.
- **diff_rech_num:** Difference between avg_rech_num_action and total_rech_num_6.
- **decrease_rech_num_action:** Binary indicator for whether recharge numbers decreased in the action phase.
- **avg_rech_amt_action:** Average recharge amount during the action phase.
- **diff_rech_amt:** Difference between avg_rech_amt_action and total_rech_amt_6.
- **decrease_rech_amt_action:** Binary indicator for whether recharge amount decreased in the action phase.

### ARPU (Average Revenue Per User) Metrics:

- **avg_arpu_action:** Average ARPU during the action phase.
- **diff_arpu:** Difference between avg_arpu_action and arpu_6.
- **decrease_arpu_action:** Binary indicator for whether ARPU decreased in the action phase.

### VBC (Volume-Based Cost) Metrics:

- **avg_vbc_3g_action:** Average 3G VBC during the action phase.
- **diff_vbc:** Difference between avg_vbc_3g_action and jun_vbc_3g.
- **decrease_vbc_action:** Binary indicator for whether 3G VBC decreased in the action phase.

These features provide insights into customer behavior and usage patterns, helping to identify potential indicators of churn.

## Authors

- [@RottenBanana420](https://github.com/RottenBanana420)

