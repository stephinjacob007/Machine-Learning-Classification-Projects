# 📱 Teen Smartphone Usage and Addiction Classification

## Overview

This project focuses on predicting smartphone addiction levels among teenagers using machine learning techniques. The continuous addiction score was transformed into three categories representing **Low**, **Medium**, and **High** addiction levels, and multiple classification models were developed and compared.

The project includes extensive exploratory data analysis, feature engineering, preprocessing pipelines, class imbalance handling using SMOTE, hyperparameter tuning, model comparison, feature importance analysis, and confusion matrix visualization.

---

## Dataset

* Dataset Size: **3,000 records**
* Features: **25 attributes**
* Target Variable:

  * Low Addiction
  * Medium Addiction
  * High Addiction

### Feature Categories

#### Demographic Features

* Age
* Gender
* Location
* School Grade

#### Usage Features

* Daily Usage Hours
* Weekend Usage Hours
* Phone Checks Per Day
* Apps Used Daily
* Screen Time Before Bed

#### Activity Features

* Time on Social Media
* Time on Gaming
* Time on Education

#### Lifestyle and Mental Health Features

* Sleep Hours
* Exercise Hours
* Anxiety Level
* Depression Level
* Self-Esteem
* Family Communication
* Academic Performance
* Social Interactions
* Parental Control

---

## Exploratory Data Analysis

The project includes:

* Dataset inspection
* Missing value analysis
* Descriptive statistics
* Distribution analysis
* Correlation analysis
* Mutual information analysis
* Visualization of feature relationships
* Analysis of behavioral patterns across addiction categories

---

## Data Preprocessing

### Feature Selection

Unnecessary columns were removed:

* ID
* Name

### Missing Value Handling

* Numerical features → Median imputation
* Categorical features → Most frequent imputation

### Encoding

Categorical variables were encoded using:

* OneHotEncoder

### Scaling

For models sensitive to feature magnitude:

* StandardScaler

Tree-based models were trained without scaling.

---

## Handling Class Imbalance

The target classes were highly imbalanced.

SMOTE (Synthetic Minority Oversampling Technique) was applied within the training pipeline to generate synthetic samples for minority classes and improve classification performance.

---

## Models Evaluated

1. Logistic Regression
2. Support Vector Machine (SVM)
3. K-Nearest Neighbors (KNN)
4. Decision Tree
5. Random Forest
6. XGBoost

---

## Hyperparameter Tuning

GridSearchCV was used for model optimization.

### Evaluation Metric

Because of class imbalance, **Macro F1-score** was used as the tuning metric to ensure equal importance for all classes.

---

## Model Performance

| Model               | Accuracy | Macro F1 |
| ------------------- | -------: | -------: |
| SVM                 |   98.67% |   0.9447 |
| Logistic Regression |   97.50% |   0.9291 |
| XGBoost             |   93.83% |   0.8421 |
| Random Forest       |   91.83% |   0.7682 |
| Decision Tree       |   86.17% |   0.6515 |
| KNN                 |   76.33% |   0.5182 |

---

## Best Model: Support Vector Machine

### Best Parameters

```python
C = 10.0
Kernel = Linear
```

### Performance

* Accuracy: **98.67%**
* Macro F1-score: **0.9447**

### Why SVM Performed the Best

After applying SMOTE, the classes became more balanced, allowing SVM to learn clear decision boundaries. Feature scaling and the linear kernel enabled efficient learning in the high-dimensional feature space produced by one-hot encoding. SVM generalized well across all classes and achieved the best overall performance.

---

## Important Features

Feature importance analysis showed that the following variables had the highest influence on addiction prediction:

1. Daily Usage Hours
2. Apps Used Daily
3. Time on Gaming
4. Time on Social Media
5. Phone Checks Per Day
6. Sleep Hours
7. Academic Performance
8. Family Communication
9. Exercise Hours
10. Weekend Usage Hours

---

## Libraries Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Imbalanced-learn
* XGBoost
* SciPy

---

## Project Workflow

```
Data Collection
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
Feature Engineering
        ↓
Preprocessing Pipelines
        ↓
SMOTE for Class Balancing
        ↓
Model Training
        ↓
GridSearchCV Hyperparameter Tuning
        ↓
Performance Comparison
        ↓
Feature Importance Analysis
        ↓
Confusion Matrix Visualization
```

---

## Results

Support Vector Machine emerged as the best-performing model with an accuracy of **98.67%** and a macro F1-score of **0.9447**, demonstrating strong predictive capability across all addiction categories.

---

## Future Improvements

* Stratified K-Fold cross-validation
* Explainability using SHAP
* Ensemble learning approaches
* Deep learning models
* Deployment using Streamlit
* Real-time prediction system
