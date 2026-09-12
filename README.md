## Breast Cancer Detection using Machine Learning

## Project Overview

This project implements an end-to-end Machine Learning pipeline for breast cancer classification using the Breast Cancer Wisconsin dataset.

The project performs data preprocessing, missing-value handling, feature preparation, train-test splitting, Random Forest model training, evaluation, feature-importance analysis, and model persistence using Joblib.

## Objective

The objective of this project is to build a Machine Learning classification model that predicts whether a breast cancer sample is:

Benign (2)
Malignant (4)

## Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Random Forest
* Joblib
* Matplotlib

## Machine Learning Workflow

Raw Dataset
     ↓
Data Loading
     ↓
Data Cleaning
     ↓
Missing Value Handling
     ↓
Feature Preparation
     ↓
Train-Test Split
     ↓
SimpleImputer
     ↓
Random Forest Classifier
     ↓
Model Prediction
     ↓
Model Evaluation
     ↓
Feature Importance Analysis
     ↓
Save Model using Joblib

## Dataset

The project uses the Breast Cancer Wisconsin dataset.

The input features include:

* Clump Thickness
* Uniformity of Cell Size
* Uniformity of Cell Shape
* Marginal Adhesion
* Single Epithelial Cell Size
* Bare Nuclei
* Bland Chromatin
* Normal Nucleoli
* Mitoses

The target variable is `CancerType`.

The implementation handles `?` values as missing data and converts feature values to numeric format before model training.

## Data Preprocessing

The preprocessing pipeline includes:

1. Reading the dataset using Pandas.
2. Converting missing-value markers (`?`) to `NaN`.
3. Converting feature columns to numeric values.
4. Splitting the dataset into training and testing sets.
5. Using `SimpleImputer` with median strategy for missing values.

## Model

A **Random Forest Classifier** is used for classification.

Model configuration:

n_estimators = 300
random_state = 42
n_jobs = -1

The model is integrated with the missing-value imputation step using a Scikit-learn Pipeline.

## Train-Test Split

The dataset is divided using a **70% training and 30% testing split**.

Stratified splitting is used to maintain the target-class distribution between training and testing datasets.

## Model Evaluation

The trained model is evaluated using:

* Training Accuracy
* Testing Accuracy
* Classification Report
* Confusion Matrix

The project also visualizes:

* Confusion Matrix
* Random Forest Feature Importances

## Model Persistence

The trained Machine Learning pipeline is saved using Joblib:

bc_rf_pipeline.joblib

The saved model can later be loaded and used for prediction without retraining.

Example:

import joblib

model = joblib.load("bc_rf_pipeline.joblib")
prediction = model.predict(sample)

## Feature Importance

Random Forest feature importance is used to identify which input features contribute most to the model's predictions.

This helps provide better interpretation of the trained classification model.

## Project Structure

Breast-Cancer-Detection/
│
├── breast_cancer_detection.py
├── breast-cancer-wisconsin.data
├── breast-cancer-wisconsin.csv
├── bc_rf_pipeline.joblib
├── README.md
│
└── screenshots/
    ├── confusion_matrix.png
    └── feature_importance.png

## Requirements

pandas
numpy
matplotlib
scikit-learn
joblib

## How to Run

Run the Python program:

python breast_cancer_detection.py

The program will:

1. Load the processed dataset.
2. Display basic dataset statistics.
3. Handle missing values.
4. Split the dataset.
5. Train the Random Forest pipeline.
6. Generate predictions.
7. Display evaluation metrics.
8. Display the confusion matrix.
9. Display feature importance.
10. Save the trained pipeline using Joblib.
11. Load the saved model and perform a sample prediction.

## Key Learning Outcomes

Through this project, I gained practical experience in:

* Python programming
* Data preprocessing
* Missing-value handling
* Feature preparation
* Machine Learning classification
* Random Forest
* Model evaluation
* Confusion matrix analysis
* Feature importance
* Scikit-learn Pipelines
* Model persistence using Joblib

## Future Improvements

* Add a user-friendly Streamlit interface.
* Add probability-based predictions.
* Perform hyperparameter tuning.
* Compare Random Forest with other classification algorithms.
* Add cross-validation.
* Improve model interpretability using advanced explainability techniques.

## Disclaimer

This project is developed for educational and Machine Learning practice purposes. It is not intended to provide medical diagnosis or replace professional medical advice.
