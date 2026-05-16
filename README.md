# Personal Loan Acceptance Prediction

A machine learning classification project that predicts whether a bank customer will accept a personal loan offer based on demographic, financial, and campaign-related attributes. Two models, Logistic Regression and Decision Tree, are trained, evaluated, and compared with detailed business insights included.

---

## Project Overview

Banks run marketing campaigns to promote personal loan products. Predicting which customers are likely to accept helps banks target the right audience and reduce campaign costs. This project builds a complete ML pipeline on the UCI Bank Marketing Dataset including exploratory data analysis, feature engineering, model training, evaluation with ROC-AUC, and business-level insights.

---

## Project Structure

```
Personal-Loan-Acceptance-Prediction/
│
├── personal_loan_prediction.ipynb   # Main Jupyter Notebook
├── bank-full.csv                    # Dataset (input)
└── README.md
```

---

## Workflow

```
Load Data --> Exploratory Data Analysis --> Data Preprocessing
    --> Feature Encoding --> Train/Test Split --> Feature Scaling
        --> Model Training --> Evaluation --> Feature Importance
            --> Business Insights --> Model Comparison
```

---

## Dataset

**File:** `bank-full.csv`
**Source:** UCI Machine Learning Repository — Bank Marketing Dataset
**Separator:** Semicolon (;)

| Feature | Description |
|---|---|
| age | Age of the customer |
| job | Type of job |
| marital | Marital status |
| education | Education level |
| default | Has credit in default — yes or no |
| balance | Average yearly account balance in EUR |
| housing | Has housing loan — yes or no |
| loan | Has personal loan — yes or no |
| contact | Contact communication type |
| month | Last contact month of the year |
| duration | Last contact duration in seconds |
| campaign | Number of contacts during this campaign |
| poutcome | Outcome of the previous marketing campaign |
| y | Target variable — yes (Accepted) / no (Not Accepted) |

---

## Exploratory Data Analysis

Seven visualizations are generated to understand loan acceptance patterns:

- Target Distribution — Bar chart of accepted vs not accepted
- Age Distribution by Loan Acceptance — Overlapping histogram
- Loan Acceptance Rate by Job Type — Bar chart with percentage labels
- Loan Acceptance by Marital Status — Grouped bar chart
- Account Balance by Loan Acceptance — Box plot
- Correlation Heatmap — Numeric features correlation matrix
- Loan Acceptance Rate by Contact Month — Line chart with shaded area

---

## Data Preprocessing

- No missing values found in this dataset
- Binary columns (default, housing, loan, y) encoded using Label Encoding
- Nominal categorical columns (job, marital, education, contact, month, poutcome) encoded using One-Hot Encoding with drop_first applied
- Features scaled using StandardScaler for Logistic Regression
- Decision Tree does not require feature scaling
- class_weight set to balanced on both models to handle the class imbalance (88% no, 12% yes)

---

## Models Used

| Model | Library |
|---|---|
| Logistic Regression | sklearn.linear_model |
| Decision Tree Classifier | sklearn.tree |

**Train/Test Split:** 80% training and 20% testing with stratification applied

**Cross Validation:** 5-fold Stratified K-Fold applied to both models

---

## Evaluation Metrics

Both models are evaluated using the following metrics:

- Accuracy Score
- ROC-AUC Score
- Classification Report (Precision, Recall, F1-Score)
- Confusion Matrix
- ROC Curve
- 5-Fold Stratified Cross-Validated Accuracy

---

## Visualizations

- Confusion Matrix and ROC Curve — side by side for both models
- Top 20 Feature Importances — Decision Tree bar chart
- Top 20 Logistic Regression Coefficients — Horizontal bar chart
- Decision Tree Visualization — Tree diagram shown up to depth 3

---

## Business Insights

- Duration of the last call is the strongest predictor — longer calls strongly correlate with loan acceptance
- Customers with a successful previous campaign outcome (poutcome = success) have a significantly higher acceptance rate
- Students and retired customers show the highest acceptance rates by job category
- Age groups 18-25 and 65+ show higher acceptance rates than middle-aged groups
- The dataset is heavily imbalanced — approximately 88% not accepted and 12% accepted

---

## Model Comparison

| Model | Accuracy | ROC-AUC |
|---|---|---|
| Logistic Regression | Based on dataset | Based on dataset |
| Decision Tree | Based on dataset | Based on dataset |

Use Decision Tree for interpretability and explainability. Use Logistic Regression for stable probability estimates.

---

## Tech Stack

- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn

---

## Getting Started

**1. Clone the Repository**

```bash
git clone https://github.com/SyedAfzaalShah/Personal-Loan-Acceptance-Prediction.git
```

**2. Install Dependencies**

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

**3. Add the Dataset**

Place `bank-full.csv` in the project root directory.

**4. Run the Notebook**

```bash
jupyter notebook personal_loan_prediction.ipynb
```

---

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
