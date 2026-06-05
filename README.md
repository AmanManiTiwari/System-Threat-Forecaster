<div align="center">

# 🛡️ System Threat Forecaster

### *Predicting malware infection risk on Windows machines using ensemble machine learning*

<br>

[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![XGBoost](https://img.shields.io/badge/XGBoost-Ensemble-006400?style=for-the-badge)](https://xgboost.readthedocs.io)
[![LightGBM](https://img.shields.io/badge/LightGBM-Ensemble-9ACD32?style=for-the-badge)](https://lightgbm.readthedocs.io)
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)](https://github.com/AmanManiTiwari/System-Threat-Forecaster)

<br>

> **Can we predict whether a Windows machine will be infected by malware - before it happens?**
> This project builds a production-grade ML pipeline to answer exactly that.

</div>

---

## 📌 Overview

**System Threat Forecaster** is an end-to-end machine learning project that predicts the likelihood of a Windows device being compromised by malware. Using real-world telemetry data from Microsoft's systems, it applies a full ML pipeline - from raw data ingestion to hyperparameter-tuned ensemble models - to classify system threat risk with high accuracy.

This project demonstrates the intersection of **cybersecurity intelligence** and **predictive machine learning**, a skillset in high demand across data science, security operations, and threat analytics roles.

---

## 🎯 Problem Statement

| | Details |
|---|---|
| **Task** | Binary Classification - predict malware infection probability |
| **Domain** | Cybersecurity / System Telemetry |
| **Dataset** | Microsoft Malware Prediction (via Kaggle) |
| **Target Variable** | `HasDetections` - whether the device had malware detected |
| **Challenge** | High-dimensional data, class imbalance, mixed feature types |

---

## 🔬 ML Pipeline Architecture

```
┌──────────────────────────────────────────────────────────────┐
│                     RAW TELEMETRY DATA                       │
│              (Windows device system properties)              │
└─────────────────────────┬────────────────────────────────────┘
                          │
                          ▼
┌──────────────────────────────────────────────────────────────┐
│                   DATA PREPROCESSING                         │
│   • Missing value imputation (SimpleImputer)                 │
│   • Categorical encoding (OneHotEncoder)                     │
│   • Feature scaling (StandardScaler)                         │
│   • ColumnTransformer for mixed-type pipeline                │
└─────────────────────────┬────────────────────────────────────┘
                          │
                          ▼
┌──────────────────────────────────────────────────────────────┐
│                  FEATURE ENGINEERING                         │
│   • Dimensionality Reduction via PCA                         │
│   • Statistical Feature Selection via SelectKBest            │
└─────────────────────────┬────────────────────────────────────┘
                          │
                          ▼
┌──────────────────────────────────────────────────────────────┐
│                   MODEL TRAINING                             │
│   ┌─────────────────┐ ┌──────────────┐ ┌─────────────────┐  │
│   │  Random Forest  │ │   XGBoost    │ │    LightGBM     │  │
│   └─────────────────┘ └──────────────┘ └─────────────────┘  │
└─────────────────────────┬────────────────────────────────────┘
                          │
                          ▼
┌──────────────────────────────────────────────────────────────┐
│               HYPERPARAMETER TUNING                          │
│                  GridSearchCV + CV                           │
└─────────────────────────┬────────────────────────────────────┘
                          │
                          ▼
┌──────────────────────────────────────────────────────────────┐
│                   EVALUATION                                 │
│   Confusion Matrix · Classification Report · ROC-AUC · F1   │
└──────────────────────────────────────────────────────────────┘
```

---

## 🤖 Models Compared

| Model | Type | Key Strength |
|-------|------|-------------|
| **Random Forest** | Bagging Ensemble | Robust to noise, interpretable feature importances |
| **XGBoost** | Gradient Boosting | High accuracy, handles sparse/missing data well |
| **LightGBM** | Gradient Boosting | Fastest training on large datasets, memory efficient |

All models are wrapped in a **scikit-learn Pipeline** to prevent data leakage and enable clean cross-validation.

---

## 🛠️ Tech Stack

| Layer | Tools |
|-------|-------|
| **Language** | Python 3.8+ |
| **Notebook** | Jupyter Notebook |
| **Data Handling** | `pandas`, `numpy` |
| **Visualization** | `matplotlib`, `seaborn` |
| **Preprocessing** | `scikit-learn` - `SimpleImputer`, `OneHotEncoder`, `StandardScaler`, `ColumnTransformer` |
| **Feature Selection** | `SelectKBest`, `PCA` |
| **ML Models** | `RandomForestClassifier`, `XGBClassifier`, `LGBMClassifier` |
| **Optimization** | `GridSearchCV`, `Pipeline` |
| **Dataset** | `kagglehub` |

---

## 📁 Repository Structure

```
System-Threat-Forecaster/
│
├── 📓 Notebook.ipynb                      ← Main analysis: full ML pipeline
├── 📓 22f3003055-notebook-t12025.ipynb    ← Extended/competition version
└── 📄 README.md                           ← You are here
```

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/AmanManiTiwari/System-Threat-Forecaster.git
cd System-Threat-Forecaster
```

### 2. Install Dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost lightgbm kagglehub
```

### 3. Set Up Kaggle API (for dataset access)
```bash
# Place your kaggle.json credentials at ~/.kaggle/kaggle.json
# OR set environment variables:
export KAGGLE_USERNAME=your_username
export KAGGLE_KEY=your_api_key
```

### 4. Run the Notebook
```bash
jupyter notebook Notebook.ipynb
```

---

## 📋 Notebook Walkthrough

| Step | Section | What Happens |
|------|---------|-------------|
| 1 | **Package Imports** | Load all libraries and configure settings |
| 2 | **Data Loading** | Pull Microsoft Malware dataset via `kagglehub` |
| 3 | **Data Exploration** | Profile distributions, check class balance, identify nulls |
| 4 | **Data Preprocessing** | Impute, encode, scale - all inside a Pipeline |
| 5 | **Feature Selection** | PCA for dimensionality reduction, SelectKBest for relevance |
| 6 | **Model Training** | Fit Random Forest, XGBoost, LightGBM |
| 7 | **Hyperparameter Tuning** | Optimize with GridSearchCV |
| 8 | **Evaluation** | Confusion matrix, classification report, visual insights |

---

## 📈 Skills Demonstrated

- **End-to-end ML pipeline design** using `sklearn.Pipeline` and `ColumnTransformer`
- **Ensemble methods** - bagging (Random Forest) and boosting (XGBoost, LightGBM)
- **Feature engineering** - dimensionality reduction with PCA and statistical selection
- **Hyperparameter optimization** with `GridSearchCV` and cross-validation
- **Cybersecurity domain knowledge** - understanding system telemetry as ML features
- **Model evaluation** - beyond accuracy: precision, recall, F1, confusion matrix
- **Clean, reproducible code** structured for collaboration and review

---

## 💼 Real-World Relevance

This project mirrors the kind of work done by data scientists at security companies like Microsoft Defender, CrowdStrike, and Palo Alto Networks. The ability to **classify threat risk from system properties** is a core use case in:

- Endpoint Detection & Response (EDR) systems
- Security Operations Centers (SOC)
- Vulnerability management platforms
- Insurance risk scoring for cyber policies

---

## 🙋 About the Author

**Aman Mani Tiwari** - Data Science & ML practitioner building portfolio projects at the intersection of AI and real-world domains.

[![GitHub](https://img.shields.io/badge/GitHub-AmanManiTiwari-181717?style=flat-square&logo=github)](https://github.com/AmanManiTiwari)

---

<div align="center">

*Found this useful? Drop a ⭐ - it helps others discover the project!*

</div>
