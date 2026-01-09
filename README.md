# Heart Disease Prediction Analysis

**Tech Stack:** Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn

## Overview
This project explores whether heart disease can be predicted using clinical and demographic health data. Using a combination of exploratory data analysis, logistic regression, and unsupervised clustering, the analysis examines which factors are most strongly associated with heart disease and whether patients can be grouped into meaningful risk categories.

The project emphasizes interpretability and practical decision-making, particularly in a medical context where false negatives are costly.

## Data
The dataset was sourced from **Kaggle** and combines five previously published heart disease datasets into a single, unified dataset with common features.

- **Observations:** 918 patients  
- **Features:** 11 clinical and demographic variables  
- **Target:** Presence of heart disease (binary)

Source: Heart Failure Prediction Dataset (Kaggle) https://tinyurl.com/ye2ay9d8

## Data Cleaning
Several data quality issues were addressed:

- Resting blood pressure and cholesterol contained impossible zero values
- Mean imputation was used for resting blood pressure
- Median imputation was used for cholesterol due to skewness
- Negative values in the `Oldpeak` variable were treated as measurement error and set to zero
- Duplicate observations were removed prior to analysis

Approximately **80% of the data required no modification**, reflecting overall strong data quality.

## Exploratory Data Analysis (EDA)
Key exploratory findings include:

- Individuals with heart disease tend to be older on average
- Men exhibit significantly higher rates of heart disease than women
- Asymptomatic chest pain is common among patients with heart disease
- Higher `Oldpeak` values are associated with increased heart disease risk
- No single feature alone explains heart disease, suggesting a multivariate relationship

## Logistic Regression
A logistic regression model was trained using an 80/20 train-test split.

### Preprocessing
- Numerical features were standardized
- Categorical features were one-hot encoded
- Multicollinearity was avoided by dropping baseline categories

### Results
- **Accuracy:** ~86%
- **Sensitivity (Recall):** ~84%

The strongest predictors of heart disease included:
- Male sex
- Flat ST slope
- High fasting blood sugar
- Exercise-induced angina
- Elevated Oldpeak values

Given the medical context, model evaluation focused heavily on sensitivity to reduce missed diagnoses.

## K-Means Clustering
Unsupervised learning was used to explore whether patients could be grouped into risk categories.

- Numerical features were scaled
- The elbow method suggested **k = 3**
- PCA was used to visualize cluster separation

### Identified Groups
- **High risk:** ~84% heart disease prevalence
- **Medium risk:** ~65% heart disease prevalence
- **Low risk:** ~28% heart disease prevalence

While clusters overlap, they align with intuitive risk groupings and complement the supervised model.

## Conclusions
- Heart disease risk is best understood as a combination of factors rather than a single indicator
- Logistic regression provides interpretable predictors useful for screening
- Clustering reveals natural groupings that can support risk stratification
- In medical settings, prioritizing sensitivity over overall accuracy is critical

This project highlights both the potential and limitations of predictive modeling in healthcare contexts.
