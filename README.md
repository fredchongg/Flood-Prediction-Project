# 🌊 Flood Risk Prediction Project

A data mining school project to analyze environmental factors and predict flood risk using machine learning. This repository contains a complete Jupyter Notebook with data cleaning, exploratory data analysis (EDA), and model comparison.

## 🎯 Project Overview

Floods are a major environmental hazard, and being able to predict them is crucial for public safety. The goal of this project was to:
1.  Analyze a dataset of 200 locations to identify the key factors contributing to floods.
2.  Build and evaluate three different classification models:
    * **Logistic Regression**
    * **Decision Tree**
    * **Neural Network (MLP Classifier)**
3.  Determine the best-performing model for predicting flood risk based on these features.

## 📊 The Dataset

* **Source:** `Flood_Prediction_Dataset.xlsx`
* **Size:** 200 records, 8 features.
* **Target Variable:** `Flood` (Yes/No)
* **Key Features:**
    * `Rainfall` (continuous)
    * `RiverLevel` (continuous)
    * `DrainageQuality` (categorical: Poor, Moderate, Good)
    * `SoilSaturation` (continuous)
    * `LandType` (categorical: Urban, Suburban, Rural)

## 🛠️ Methodology

The project followed a standard data science workflow:

1.  **Data Preprocessing:**
    * Loaded the dataset using `pandas`.
    * Handled missing values using median (for numerical) and mode (for categorical) imputation.
    * Performed feature encoding:
        * **Label Encoding (Mapping):** Used for ordinal data (`DrainageQuality`) and binary data (`Flood`, `NearbyWaterBody`).
        * **One-Hot Encoding (`get_dummies`):** Used for nominal data (`LandType`) while dropping the first column to prevent multicollinearity.

2.  **Exploratory Data Analysis (EDA):**
    * Analyzed the distribution of the target variable (`Flood`) and found it was imbalanced.
    * Created histograms and count plots to visualize the relationship between features (like `Rainfall` and `DrainageQuality`) and the flood outcome.
    * Generated a correlation heatmap to identify the strongest predictive features.

3.  **Model Preparation & Training:**
    * Split the data into training (70%) and testing (30%) sets using `train_test_split`.
    * Scaled numerical features (`Rainfall`, `RiverLevel`, etc.) using `StandardScaler` to prepare them for Logistic Regression and Neural Networks.
    * Handled the imbalanced dataset by using the `class_weight='balanced'` parameter in the models.

4.  **Model Evaluation:**
    * Trained all three models on the same scaled training data.
    * Evaluated them on the unseen test data.
    * Compared their performance using **Accuracy**, **Precision**, **Recall**, and **F1-Score**.

## 📈 Results: Model Comparison

After training and evaluation, the models performed as follows. The Neural Network achieved the highest overall performance

| Model | Accuracy | F1-Score (for "Flood") |
| :--- | :--- | :--- |
| Neural Network | 0.8333 | 0.64 |
| Decision Tree | 0.7833 | 0.65 |
| Logistic Regression | 0.7667 | 0.61 |


## 💻 Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn (Sklearn)
* Jupyter Notebook
* Git & GitHub