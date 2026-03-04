## Project Overview

This project analyzes the Red Wine Quality dataset and builds machine learning models to classify whether a wine is high quality or not. The workflow includes data cleaning, exploratory data analysis (EDA), feature engineering, model training, and evaluation.

## Dataset Information

* **Dataset:** `Red_wine.csv`
* **Total Samples:** 1,599
* **Features:** 11 numerical physicochemical attributes (acidity, sugar, chlorides, pH, sulphates, alcohol, etc.)
* **Target Variable:** `quality`

## Problem Formulation

* The original `quality` column is a score (typically 3–8).

* To simplify the task, the problem is converted into **binary classification** by creating a new target:

* **best_quality = 1** → quality > 5

* **best_quality = 0** → quality ≤ 5

* This allows the models to focus on predicting whether a wine is considered “good” quality or not.

## Data Preprocessing

* Checked dataset structure and summary statistics to understand feature ranges.
* Handled missing values using **mean imputation** for columns with null values.
* Dropped the `total sulfur dioxide` feature to reduce redundancy.
* Split the dataset into:

  * **80% training**
  * **20% testing**
* Applied **MinMax Scaling** to normalize features (helps models like SVM and Logistic Regression).

## Exploratory Data Analysis (EDA)

* Visualized feature distributions using histograms to understand spread and skewness.
* Compared alcohol levels across different quality scores to study patterns.
* Used a correlation heatmap to identify relationships between features.

### Key Observations

* Alcohol content increases with wine quality.
* Many chemical features show moderate correlation with each other.
* The dataset has more mid-quality wines than extreme low/high quality wines.

## Models Implemented

* Logistic Regression

* XGBoost Classifier

* Support Vector Classifier (RBF Kernel)

* Models were evaluated using ROC-AUC and classification metrics.
## Evaluation Summary

* Compared training vs validation ROC-AUC to understand generalization.
* XGBoost achieved the strongest validation performance among the tested models.
* Final evaluation includes accuracy, precision, recall, and F1-score for the best model.

## Tools & Technologies

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn
* XGBoost

## Key Insights

* Feature scaling improves model stability for distance-based and margin-based models.
* Tree-based models (XGBoost) perform strongly on structured tabular datasets.
* Alcohol and sulphates are among the more informative features for predicting quality.

## Future Improvements

* Hyperparameter tuning (GridSearchCV / RandomizedSearchCV)
* K-Fold cross-validation for more reliable evaluation
* Feature importance plots (especially for XGBoost)
* Try handling class imbalance (SMOTE, class weights)
* Experiment with ensemble methods

## Conclusion
This project applies a complete machine learning workflow to a structured classification problem. After evaluating multiple models, XGBoost achieved the strongest validation performance. The results demonstrate the impact of preprocessing, feature scaling, and model selection on predictive accuracy. Overall, the project provides practical insight into building and evaluating ML models on tabular datasets.
