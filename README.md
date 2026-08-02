# Diabetes Prediction Using Machine Learning

## Overview

This project focuses on predicting the risk of **Type 2 Diabetes Mellitus (T2DM)** using non-invasive health indicators and demographic information through machine learning techniques.

The research investigates whether machine learning models can assist in early diabetes risk screening without relying on invasive laboratory tests such as fasting blood glucose and HbA1c. Two tree-based classification algorithms were implemented and compared:

- **Decision Tree Classifier**
- **Random Forest Classifier**

The objective is to develop an interpretable and cost-effective screening approach that can support early identification of high-risk individuals, particularly in resource-limited healthcare environments.

---

## Research Abstract

Type 2 Diabetes Mellitus (T2DM) is a rapidly increasing global health concern, especially in developing countries where early diagnosis facilities are limited. This research explores the use of machine learning techniques for predicting T2DM using non-invasive health indicators.

The models were trained using the **Diabetes Health Indicators Dataset**, derived from the **Behavioral Risk Factor Surveillance System (BRFSS) 2015**, containing:

- 70,692 patient records
- 21 predictive health and demographic attributes
- Binary diabetes outcome classification

The optimized models achieved the following results:

| Model | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Decision Tree | 74.18% | 72.59% | 78.04% | 75.22% | 0.819 |
| Random Forest | **75.06%** | **73.28%** | **79.19%** | **76.12%** | **0.827** |

The Random Forest model achieved better generalization and predictive performance compared to the Decision Tree model.

---

# Dataset

## Source

The dataset used in this project was obtained from:
https://data.humdata.org/dataset/38be9db6-c016-4c14-8f0b-95570a5f8593/resource/ccbc3987-e49d-49b0-bb6d-f5b44f40b4a1/download/health_indicators_npl.csv


The dataset contains health indicators and demographic information useful for diabetes risk prediction.

## Features

The dataset contains 21 predictor variables including:

- Body Mass Index (BMI)
- Blood pressure status
- Cholesterol level
- General health condition
- Physical activity
- Age category
- Education level
- Income level
- Smoking status
- Healthcare accessibility
- Lifestyle indicators

Target variable:

- `diabetes target`
  - 0 → Non-diabetic
  - 1 → Diabetic / Prediabetic

---

# Methodology

The project workflow consists of the following stages:
Dataset Collection
|
↓
Data Cleaning & Preprocessing
|
↓
Exploratory Data Analysis
|
↓
Feature Analysis
|
↓
Model Training
|
↓
Hyperparameter Optimization
|
↓
Model Evaluation
|
↓
Performance Comparison


---

# Data Preprocessing

The following preprocessing steps were applied:

- Dataset randomization using a fixed random seed
- Missing value analysis
- Feature scaling using `StandardScaler`
- Train-validation-test split:

Training Set : 65%
Validation Set : 20%
Testing Set : 15%


- Final test set size:


10,605 samples


---

# Machine Learning Models

## 1. Decision Tree Classifier

A Decision Tree classifier was developed as a baseline model due to:

- High interpretability
- Ability to capture nonlinear relationships
- Capability of handling mixed feature types

### Hyperparameter Optimization

Parameters tuned:

| Parameter | Range |
|---|---|
| max_depth | 1 - 15 |
| min_samples_leaf | 1 - 46 |

Final configuration:


max_depth = 8
min_samples_leaf = 21


---

## 2. Random Forest Classifier

Random Forest was selected to improve generalization and reduce overfitting by combining multiple decision trees.

Advantages:

- Ensemble learning capability
- Lower variance compared to single trees
- Feature importance analysis
- Better predictive stability

### Hyperparameter Optimization

Parameters tuned:

| Parameter | Range |
|---|---|
| max_depth | 1 - 15 |
| n_estimators | 1 - 100 |

Final configuration:


max_depth = 8
n_estimators = 40


---

# Exploratory Data Analysis

The project includes analysis of:

- Target class distribution
- Correlation between health indicators
- BMI distribution
- Feature importance analysis

Key observations:

- General health status was the strongest predictor.
- High blood pressure and BMI were major contributing factors.
- Age category and high cholesterol also showed significant importance.

---

# Model Performance

## Decision Tree

Final evaluation results:


Accuracy : 74.18%
Precision : 72.59%
Recall : 78.04%
F1 Score : 75.22%
ROC-AUC : 0.819


---

## Random Forest

Final evaluation results:


Accuracy : 75.06%
Precision : 73.28%
Recall : 79.19%
F1 Score : 76.12%
ROC-AUC : 0.827


Random Forest achieved better performance, especially in recall, which is important for healthcare screening because missing high-risk patients can delay intervention.

---

# Feature Importance

The Random Forest model identified the following important predictors:

| Feature | Importance |
|---|---:|
| General Health | 23.8% |
| High Blood Pressure | 21.1% |
| BMI | 13.4% |
| Age Category | 10.8% |
| High Cholesterol | 10.1% |

---

# Repository Structure


DIABETES_PREDICTION/
│
├── dataset/
│ └── health_indicators_npl.csv
│
├── notebooks/
│ ├── EDA.ipynb
│ ├── DecisionTree.ipynb
│ └── RandomForest.ipynb
│
├── models/
│ ├── decision_tree_model.pkl
│ └── random_forest_model.pkl
│
├── preprocessing/
│ └── scaler.pkl
│
├── requirements.txt
│
├── README.md
│
└── LICENSE


---

# Installation

Clone the repository:

```bash
git clone https://github.com/tikadatta2005/DIABETES_PREDICTION.git

Navigate into the project directory:

cd DIABETES_PREDICTION

Install dependencies:

pip install -r requirements.txt
Requirements

Main libraries used:

Python >= 3.10

numpy
pandas
scikit-learn
matplotlib
seaborn
jupyter
joblib

Install all dependencies:

pip install -r requirements.txt
Running the Project

Run Jupyter Notebook:

jupyter notebook

Execute notebooks in the following order:

Data preprocessing and EDA
Decision Tree training
Random Forest training
Model evaluation
Proposed Intelligent System Architecture

The proposed deployment architecture consists of:

Data Collection Layer
Patient demographic information
Non-invasive health indicators
Preprocessing Layer
Data validation
Feature transformation
Standardization
Machine Learning Layer
Random Forest prediction model
Decision Support Layer
Diabetes risk classification
Prediction probability
Recommended medical follow-up
User Interface Layer
Web/mobile application
Healthcare worker interface
Feedback and Retraining Layer
Continuous monitoring
Model improvement using new clinical data
Limitations
Dataset is derived from BRFSS 2015 and may not fully represent the Nepalese population.
Clinical measurements such as glucose level and HbA1c were unavailable.
Only Decision Tree and Random Forest models were evaluated.
External validation using Nepal-specific hospital data is required.
Explainable AI techniques such as SHAP and LIME were not implemented.
Future Work

Future improvements include:

Training with Nepal healthcare datasets.
Adding clinical features such as HbA1c and blood glucose.
Comparing advanced models:
XGBoost
LightGBM
Support Vector Machines
Deep Learning approaches
Implementing Explainable AI techniques.
Deploying the model as a healthcare screening application.
Ethical Considerations

This system is intended as a screening support tool, not a replacement for professional medical diagnosis.

Important considerations:

Patient data privacy and security
Algorithmic bias due to dataset differences
Proper interpretation of predictions
Validation with real clinical data before deployment
Authors

Tika Datta Gautam

Machine Learning Research Project
Diabetes Risk Prediction Using Non-Invasive Health Indicators

GitHub:
https://github.com/tikadatta2005/DIABETES_PREDICTION

License

This project is intended for academic and research purposes.