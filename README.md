# Employee Attrition Prediction - Classification Model

[![Python](https://img.shields.io/badge/python-3.11+-blue.svg)](https://www.python.org)
[![XGBoost](https://img.shields.io/badge/XGBoost-Latest-green.svg)](https://xgboost.readthedocs.io/)

## 📝 Overview

Data engineering pipeline for predicting employee attrition. Loads HR employee data, transforms features, and applies XGBoost classification to identify employees likely to leave.

- **Dataset:** 1,470 employees × 35 features
- **Target:** Attrition (Yes/No - Binary)
- **Model Performance:** Accuracy 85.03%
- **Business Impact:** Early identification of at-risk employees

---

## 🎯 Key Features

✅ Load HR employee dataset (CSV)  
✅ Exploratory analysis by attrition status  
✅ Handle class imbalance (84% No, 16% Yes)  
✅ Categorical encoding (one-hot)  
✅ Feature scaling & selection  
✅ XGBoost classification model  
✅ Accuracy & classification metrics  

---

## 🛠️ Tech Stack

- **Python 3.11+** | Pandas | NumPy
- **Visualization:** Matplotlib, Seaborn
- **ML:** Scikit-learn, XGBoost
- **Development:** Jupyter Notebook

---

## 📦 Installation

```bash
# Clone repo
git clone https://github.com/your-username/employee-attrition-pipeline.git
cd employee-attrition-pipeline

# Create virtual environment
python -m venv venv
source venv/bin/activate

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter

# Download data
# Kaggle: IBM HR Analytics Attrition Dataset
# Place Employee.csv in /data/raw/
```

---

## 🚀 Usage

```bash
jupyter notebook RandomF_Employees.ipynb
```

**Pipeline Steps:**
1. Load employee HR data
2. Exploratory analysis (age, income, tenure, satisfaction)
3. Validate data quality
4. One-hot encode categorical variables (department, role, travel)
5. Standardize numerical features
6. Stratified train/test split (preserve class ratio)
7. Train XGBoost classifier with class weight balancing
8. Evaluate with Accuracy, Precision, Recall, F1-Score

---

## 📊 Results

| Metric | Value |
|--------|-------|
| Training Records | 1,029 |
| Test Records | 441 |
| **Accuracy** | 85.03% |
| **Precision** | ~82% |
| **Recall** | ~75% |
| **F1-Score** | 0.78 |

**Interpretation:** Model correctly predicts 85 of 100 employees. Of predicted attrition cases, 82% are correct.

---

## 🔑 Key Features (Predictors)

Top factors influencing attrition:
- Monthly Income (low salary → higher risk)
- Years at Company (newer employees leave more)
- Age (younger employees leave more)
- Work-Life Balance (satisfaction matters)
- Overtime (excessive hours increase attrition)

---

## 📁 Project Structure

```
employee-attrition-pipeline/
├── RandomF_Employees.ipynb   # Main notebook
├── README.md
├── requirements.txt
└── data/
    ├── raw/
    │   └── Employee.csv
```

---

## 🔑 Data Transformations

- **Categorical Encoding:** One-hot encoding for department, role, travel type
- **Feature Scaling:** StandardScaler for numerical features
- **Class Imbalance:** scale_pos_weight=5 to balance 84/16 ratio
- **Train/Test Split:** Stratified 70/30 split

---

## ⚠️ Class Imbalance Challenge

- Raw data: 84% No Attrition, 16% Attrition
- Naive model would predict all "No" (84% accuracy but useless)
- Solution: Stratified split + scale_pos_weight in XGBoost
- Focus on Precision/Recall, not just Accuracy

---

## 📚 Kaggle Dataset

Source: [IBM HR Analytics Attrition Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

---

**Author:** Ramiro Pérez | [GitHub](https://github.com/pfcperez)  
**Status:** ✅ Complete
