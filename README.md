# 📊 Customer Support Ticket Analysis & Satisfaction Prediction

> End-to-end data analysis + machine learning project to analyze support performance and predict customer satisfaction.

---

## 📌 Project Overview

This project analyzes customer support tickets to uncover:

- Customer complaint patterns  
- Support efficiency (response & resolution time)  
- Product-related issues  
- Channel performance  

It also builds a **machine learning model to predict customer satisfaction ratings**.

---

## 🎯 Objectives

- Identify key business problems in support system  
- Analyze response & resolution delays  
- Understand customer behavior  
- Improve service quality using data  
- Build ML model to predict satisfaction  

---

## 🛠️ Tech Stack

- **Python**
- **pandas, numpy** → data handling  
- **matplotlib, seaborn** → visualization  
- **scikit-learn** → machine learning  

---

## 📂 Dataset

- Source: Customer support tickets dataset  
- Contains:
  - Customer details (age, gender)  
  - Ticket info (type, priority, channel, status)  
  - Product purchased  
  - Response & resolution times  
  - Customer satisfaction rating  

---

## 🧹 Data Preprocessing

- Handled missing values:
  - `customer_satisfaction_rating` → filled with `0`
- Converted categorical variables:
  - Gender encoded manually (Male=0, Female=1, Other=2)
- Feature engineering:
  - Mean encoding:
    - `product_purchased`
    - `ticket_subject`
- Dropped irrelevant columns:
  - IDs, names, emails, text-heavy columns
- Train-test split:
  - 80% training / 20% testing  

---

## ⚙️ Feature Engineering

### 🔹 Mean Encoding
- Product-based satisfaction mean
- Ticket subject-based satisfaction mean

### 🔹 Column Transformation
- **Numerical features** → StandardScaler  
- **Categorical features** → OneHotEncoder  

---

## 🤖 Machine Learning Models Used

Multiple models were trained and compared:

- Logistic Regression  
- Decision Tree Classifier  
- Random Forest Classifier  
- Gradient Boosting Classifier  
- AdaBoost Classifier  
- K-Nearest Neighbors  

---

## 📊 Model Evaluation

Metrics used:

- Accuracy  
- Precision  
- Recall  
- F1 Score  

---

## 🔍 Hyperparameter Tuning

- Used **RandomizedSearchCV**
- Applied on:
  - Gradient Boosting  
  - Logistic Regression  

### Final Selected Model:
**GradientBoostingClassifier**

---

## 🏆 Final Model Configuration

```python
GradientBoostingClassifier(
    n_estimators=200,
    learning_rate=0.1,
    max_depth=8,
    min_samples_split=3,
    min_samples_leaf=5,
    loss='log_loss'
)
```

## 📁 Project Structure
```
├── data/
│   └── cleaned_data.csv
├── notebooks/
│   ├── customer_support_analysis.ipynb
│   └── predict_satisfaction.ipynb
├── README.md

```
