# 💳 Credit Card Fraud Detection using Machine Learning

![Python](https://img.shields.io/badge/Python-3.11-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange)
![XGBoost](https://img.shields.io/badge/XGBoost-Classifier-green)
![License](https://img.shields.io/badge/License-MIT-brightgreen)

## 📌 Project Overview

This project focuses on detecting fraudulent credit card transactions using Machine Learning.

Since fraud datasets are highly imbalanced, different imbalance handling techniques were applied before training multiple classification models.

The project compares Logistic Regression, Random Forest, and XGBoost using Precision, Recall, F1-Score and PR-AUC. Threshold optimization and business cost-benefit analysis are also performed to deploy the best fraud detection model.

---

# 🎯 Objectives

- Detect fraudulent transactions
- Handle extreme class imbalance
- Compare multiple ML algorithms
- Optimize decision threshold
- Perform business cost-benefit analysis
- Build a deployment-ready pipeline

---

# 📂 Dataset Information

- Dataset: Credit Card Fraud Detection
- Total Transactions: 50,000
- Fraud Class: Highly Imbalanced
- Target Variable:
  - 0 → Legitimate
  - 1 → Fraud

---

# 🚀 Project Workflow

## ✅ Step 1 – Problem Framing & Theory

- Why Accuracy is misleading
- Precision vs Recall
- PR-AUC
- Class imbalance
- Business impact

📷 Screenshot

![Step1](images/step1.png)

---

## ✅ Step 2 – Dataset Loading & EDA

- Load Dataset
- Dataset Information
- Missing Values
- Duplicate Values
- Class Distribution
- Feature Analysis

📷 Screenshot

![EDA](images/eda.png)

---

## ✅ Step 3 – Data Preprocessing

Performed:

- Log Transformation
- Feature Engineering
- Standard Scaling
- Train-Test Split
- SMOTE
- Random Undersampling
- Class Weight

📷 Screenshot

![Preprocessing](images/preprocessing.png)

---

## ✅ Step 4 – Logistic Regression

Three Logistic Regression models were compared:

- Original Dataset
- Class Weight Balanced
- SMOTE Dataset

Evaluation Metrics

- Precision
- Recall
- F1 Score
- PR-AUC

📷 Screenshot

![LR](images/logistic.png)

---

## ✅ Step 5 – Random Forest

Random Forest was trained using the best imbalance strategy.

Model Parameters

- n_estimators = 100
- class_weight = balanced
- random_state = 42

Evaluation

- Precision
- Recall
- F1 Score
- PR-AUC

Feature Importance was also plotted.

📷 Screenshot

![RF](images/randomforest.png)

---

## ✅ Step 6 – XGBoost

### Baseline Model

Parameters

- n_estimators = 200
- learning_rate = 0.1
- max_depth = 4

### Hyperparameter Tuning

RandomizedSearchCV

Optimized

- n_estimators
- max_depth
- learning_rate
- subsample
- colsample_bytree

Threshold Optimization

- Default Threshold
- Best F1 Threshold
- Recall ≥ 0.90 Threshold

📷 Screenshot

![XGB](images/xgboost.png)

---

## ✅ Step 7 – Model Comparison

Compared

- Logistic Regression
- Random Forest
- XGBoost Baseline
- Tuned XGBoost

Metrics

- Precision
- Recall
- F1 Score
- PR-AUC

📷 Screenshot

![Comparison](images/comparison.png)

---

## ✅ Step 8 – Business Analysis

Business Metrics

- Money Saved
- Investigation Cost
- Money Lost
- Net Benefit

Threshold Sensitivity Analysis

Business Recommendation

📷 Screenshot

![Business](images/business.png)

---

# 📈 Results

| Model | Precision | Recall | F1 | PR-AUC |
|--------|-----------|--------|----|--------|
| Logistic Regression | Your Result | Your Result | Your Result | Your Result |
| Random Forest | Your Result | Your Result | Your Result | Your Result |
| XGBoost Baseline | Your Result | Your Result | Your Result | Your Result |
| Tuned XGBoost | Your Result | Your Result | Your Result | Your Result |

---

# 🏆 Best Model

✅ Tuned XGBoost

Reasons

- Highest PR-AUC
- Better Precision-Recall Balance
- Best Business Benefit
- Threshold Optimized

---

# 💼 Business Impact

Business analysis shows that using the optimized threshold reduces financial loss while maintaining a high fraud detection rate.

The final threshold was selected based on both ML performance and business benefit.

---

# 📦 Deployment

The final model was saved using

```
joblib.dump(pipeline,"fraud_detection_model.pkl")
```

The saved pipeline can be loaded using

```python
import joblib

model = joblib.load("fraud_detection_model.pkl")
```

---

# 📁 Repository Structure

```
credit-fraud-detection-supervised-learning/

│── FraudDetection_SupervisedLearning.ipynb
│── fraud_detection_model.pkl
│── README.md
│── requirements.txt
│── summary_report.md
│── images/
│     ├── step1.png
│     ├── eda.png
│     ├── preprocessing.png
│     ├── logistic.png
│     ├── randomforest.png
│     ├── xgboost.png
│     ├── comparison.png
│     └── business.png
```

---

# ⚙️ Installation

```bash
pip install -r requirements.txt
```

---

# ▶️ Run Project

```bash
jupyter notebook
```

Open

```
FraudDetection_SupervisedLearning.ipynb
```

Run all cells.

---

# 🛠️ Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Scikit-Learn
- Imbalanced-Learn
- XGBoost
- Joblib
- Jupyter Notebook

---

# 👨‍💻 Author

**Abhiraj Medhat**

Machine Learning Practical Project

Red & White Skill Education

---

⭐ If you like this project, don't forget to star the repository.
