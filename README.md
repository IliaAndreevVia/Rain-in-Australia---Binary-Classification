# Rain in Australia - Binary Classification

## Project Overview

This project builds a binary classification model to predict whether it will rain tomorrow in Australia using historical weather observations collected from multiple meteorological stations.

The objective is to develop a robust machine learning pipeline capable of handling missing values, categorical variables, temporal information, and class imbalance while achieving strong predictive performance.

---

## Dataset

The dataset contains historical weather observations from weather stations across Australia.

### Target Variable

**RainTomorrow**

* 1 = Rain tomorrow
* 0 = No rain tomorrow

### Features

The dataset includes:

* Temperature measurements
* Humidity
* Atmospheric pressure
* Wind speed
* Wind direction
* Rainfall
* Cloud cover
* Observation date
* Weather station location

---

## Project Workflow

### 1. Exploratory Data Analysis (EDA)

* Missing value analysis
* Target distribution analysis
* Numerical feature distributions
* Wind direction visualization using wind rose plots
* Correlation analysis

### 2. Feature Engineering

Date decomposition:

* Year
* Month
* Day
* Day of year

Wind direction encoding:

* Sine transformation
* Cosine transformation

### 3. Data Preprocessing

* Median imputation for numerical variables
* Most-frequent imputation for categorical variables
* One-Hot Encoding for categorical features
* Standard scaling where required

All preprocessing steps were implemented using Scikit-Learn Pipelines and ColumnTransformer.

### 4. Model Selection

The following models were evaluated:

* Logistic Regression
* Random Forest
* Gradient Boosting
* HistGradientBoosting
* Support Vector Machine (SVC)
* XGBoost

Hyperparameter optimization was performed using GridSearchCV with Stratified K-Fold Cross Validation.

### 5. Evaluation Metrics

Models were evaluated using:

* ROC-AUC
* F1 Score
* Average Precision
* Accuracy
* Balanced Accuracy

Additional evaluation included:

* ROC Curve
* Precision-Recall Curve
* Confusion Matrix
* Threshold Optimization

---

## Best Model Performance

| Metric            | Value |
| ----------------- | ----- |
| ROC-AUC           | ~0.90 |
| F1 Score          | ~0.68 |
| Average Precision | ~0.75 |

The final model achieved strong predictive performance and maintained a balanced trade-off between precision and recall.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-Learn
* XGBoost
* Matplotlib
* Seaborn
* Windrose

---

## Repository Structure

```text
.
├── data/
├── models/
├── outputs/
├── rain_australia_classification.ipynb
├── requirements.txt
└── README.md
```

---

## Key Findings

* Proper handling of missing values significantly improved model performance.
* Cyclical encoding of wind direction features provided a more meaningful representation of directional data.
* ROC-AUC was selected as the primary metric for model selection.
* XGBoost achieved the best overall predictive performance with ROC-AUC ≈ 0.90.
* Threshold optimization improved the F1-score compared to the default classification threshold.
* Humidity, pressure, rainfall, and wind-related variables were among the most informative predictors.

---

