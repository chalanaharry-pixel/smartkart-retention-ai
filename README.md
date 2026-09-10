# 🛒 SmartKart Customer Churn Prediction

An end-to-end **Machine Learning project** that predicts which SmartKart customers are likely to churn using **Logistic Regression**.

The project takes a dirty customer dataset through a complete ML pipeline — from data cleaning and preprocessing to model training, evaluation, interpretation, and a business-ready churn risk report.

---

## 🎯 Project Objective

The main objective is to identify customers who are **likely to leave SmartKart** so that the business can take proactive retention actions.

The model predicts:

* **0 → No Churn**
* **1 → Churn**

---

## 📊 Dataset

The project uses a **100-row retail customer dataset** containing customer information and churn status.

### Main Columns

| Column          | Description                              |
| --------------- | ---------------------------------------- |
| `Customer_ID`   | Unique customer identifier               |
| `Age`           | Customer age                             |
| `Monthly_Spend` | Customer's monthly spending              |
| `Complaints`    | Number of customer complaints            |
| `Churn`         | Target variable: 0 = No Churn, 1 = Churn |

The dataset intentionally contains real-world data quality issues such as:

* Duplicate records
* Missing values
* Invalid age values
* Negative monthly spending
* Extreme outliers

---

## 🔄 Machine Learning Pipeline

The project follows a complete **15-step ML pipeline**:

### 1. Data Loading

Load the SmartKart customer dataset using Pandas.

### 2. Data Understanding

Inspect the dataset structure, data types, missing values, and basic statistics.

### 3. Data Cleaning

* Remove duplicate records
* Identify invalid values
* Convert invalid values to missing values
* Fill missing numeric values using the median

### 4. Outlier Treatment

The **IQR (Interquartile Range)** method is used to identify extreme values.

Outliers in:

* `Monthly_Spend`
* `Complaints`

are capped instead of deleting the complete customer record.

### 5. Feature Selection

The model uses three business-relevant features:

```text
Age
Monthly_Spend
Complaints
```

`Customer_ID` is excluded because it is only an identifier.

### 6. Target Definition

The target variable is:

```text
Churn
```

where:

```text
0 = No Churn
1 = Churn
```

### 7. Target Verification

The project verifies that the churn variable is already numeric and does not require additional encoding.

### 8. Train-Test Split

The cleaned dataset is divided into:

* **80% Training Data**
* **20% Testing Data**

Stratification is used to maintain a similar churn ratio in both sets.

### 9. Feature Standardisation

`StandardScaler` is used to standardise the numerical features.

The scaler is fitted only on the training data to avoid **data leakage**.

### 10. Model Building

The selected machine learning algorithm is:

**Logistic Regression**

It is suitable because customer churn is a **binary classification problem**.

### 11. Model Training

The Logistic Regression model learns the relationship between:

```text
Age
Monthly_Spend
Complaints
```

and customer churn.

### 12. Prediction

The model generates:

* Predicted churn class
* Churn probability

The probability helps rank customers according to their risk.

### 13. Model Evaluation

The model is evaluated using:

* Confusion Matrix
* Accuracy
* Precision
* Recall
* F1-Score

The notebook reports approximately **90% accuracy** and very high churn recall on the test set.

### 14. Model Interpretation

The Logistic Regression coefficients are examined to understand the factors associated with churn.

Key business insights from the notebook:

* **Monthly Spend:** Higher spending is associated with lower churn risk.
* **Complaints:** More complaints are associated with higher churn risk.
* **Age:** Shows a comparatively smaller positive relationship with churn risk.

### 15. Business-Ready Output

The project creates a ranked customer risk report:

```text
smartkart_churn_risk_report.csv
```

Customers are sorted according to their **Churn Probability**, allowing the retention team to focus on the highest-risk customers first.

---

## 📈 Business Insights

The analysis highlights two important retention areas:

### 💬 Reduce Customer Complaints

Customers with more complaints show higher churn risk.

SmartKart can therefore focus on:

* Faster complaint resolution
* Better customer support
* Tracking repeated complaints
* Improving service quality

### 💰 Protect High-Spend Customers

Higher monthly spending is associated with lower churn risk in this dataset.

SmartKart should continue focusing on retaining valuable customers through strong customer relationships and personalised offers.

---

## 🧰 Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Scikit-learn**
* **Matplotlib**
* **Seaborn**
* **Google Colab**
* **Jupyter Notebook**
* **GitHub**

---

## 📁 Project Structure

```text
smartkart-churn-prediction/
│
├── SmartKart_Churn_Prediction_ML_Pipeline.ipynb
│
├── SmartKart_dirty_100_rows.csv
│
├── smartkart_churn_risk_report.csv
│
└── README.md
```

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/your-username/smartkart-churn-prediction.git
```

### 2. Open the notebook

Open:

```text
SmartKart_Churn_Prediction_ML_Pipeline.ipynb
```

using **Google Colab** or **Jupyter Notebook**.

### 3. Upload the dataset

Make sure the SmartKart CSV dataset is available in the notebook environment.

### 4. Run the notebook

Run the cells sequentially from data loading through the final churn risk report.

---

## 📌 Final Deliverable

The main business output is:

**`smartkart_churn_risk_report.csv`**

It contains:

* Customer ID
* Age
* Monthly Spend
* Complaints
* Actual Churn
* Predicted Churn
* Churn Probability
* Risk Label

Example risk labels:

```text
Likely to Churn
Not Likely to Churn
```

---

## 💼 Business Use Case

This project demonstrates how Machine Learning can support **customer retention and business decision-making**.

Instead of waiting for customers to leave, SmartKart can use churn probabilities to identify **at-risk customers and take preventive action**.

---

## 👨‍💻 Project Skills Demonstrated

This project demonstrates practical skills in:

* Data Cleaning
* Exploratory Data Analysis
* Data Preprocessing
* Missing Value Treatment
* Outlier Detection
* Feature Selection
* Feature Scaling
* Logistic Regression
* Classification
* Model Evaluation
* Model Interpretation
* Business Analytics
* Customer Churn Prediction
* GitHub Project Management

---

## 📜 License

This project is created for **educational and portfolio purposes**.
