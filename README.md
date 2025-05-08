# 🧠 Machine Learning Pipeline Notebook

This Jupyter Notebook demonstrates a complete pipeline for building and optimizing machine learning models. It walks through essential steps like data preprocessing, feature engineering, model training, and evaluation using popular Python libraries.

## 📁 Notebook Structure

1. **Importing Necessary Packages**
2. **Data Loading**
3. **Data Exploration**
4. **Data Preprocessing**
5. **Feature Selection & Dimensionality Reduction**
6. **Model Training**
   - Random Forest
   - XGBoost
   - LightGBM
7. **Hyperparameter Tuning**
8. **Model Evaluation & Visualization**

---

## 🗂️ Project Overview

The notebook guides you through:

- 📊 **Data Exploration** – Understanding and profiling the dataset
- 🧹 **Data Cleaning** – Handling missing values and inconsistencies
- 🧬 **Feature Engineering** – Encoding, scaling, and transforming variables
- 📉 **Dimensionality Reduction** – Applying PCA and SelectKBest
- 🤖 **Model Training** – Using Random Forest, XGBoost, and LightGBM
- 🔍 **Hyperparameter Tuning** – GridSearchCV optimization
- 📈 **Evaluation** – Confusion matrix, classification report, and visual insights

---

## 📦 Tech Stack

| Category         | Libraries Used |
|------------------|----------------|
| Data Handling    | `pandas`, `numpy` |
| Visualization    | `matplotlib`, `seaborn` |
| Preprocessing    | `scikit-learn`, `SimpleImputer`, `OneHotEncoder`, `StandardScaler` |
| Feature Selection| `SelectKBest`, `PCA` |
| ML Algorithms    | `RandomForestClassifier`, `XGBClassifier`, `LGBMClassifier` |
| Tuning & Workflow| `Pipeline`, `ColumnTransformer`, `GridSearchCV` |
| Dataset Access   | `kagglehub` |

---

## 📦 Dependencies

Make sure to install the following Python libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost lightgbm kagglehub
