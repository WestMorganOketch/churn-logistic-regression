# Customer Churn Prediction using Logistic Regression

A machine learning project that predicts customer churn using Logistic Regression on the Telco Churn dataset.

## Project Overview

Customer churn refers to when a customer stops using a company's service. This project builds a classification model to identify which customers are likely to churn, enabling businesses to take proactive retention actions.

## Dataset

**Telco Churn dataset.xlsx** — Contains customer information including demographics, account details, and service usage patterns, with a `Churn` label (Yes/No).

> **Note:** The dataset file is not included in this repository. To run the notebook, download the Telco Churn dataset and place `Telco Churn dataset.xlsx` in the same folder as the notebook.

## Project Structure

```
├── Customer_Churn_Prediction_Logistic_Regression.ipynb   # Main notebook
└── README.md
```

## Steps Covered

1. **Import Libraries** — pandas, scikit-learn
2. **Load Dataset** — Read from Excel file
3. **Exploratory Data Analysis** — Preview data, check for missing values
4. **Data Preprocessing**
   - Encode target variable (`Churn`: Yes → 1, No → 0)
   - One-hot encode categorical variables
   - Drop missing values
5. **Train/Test Split** — 80% training, 20% testing
6. **Model Building** — Logistic Regression (`max_iter=1000`)
7. **Predictions** — Custom threshold of 0.3 (optimized for recall)
8. **Model Evaluation** — Accuracy, Confusion Matrix, Precision, Recall
9. **Interpretation** — Feature coefficients
10. **Conclusion**

## Results

| Metric | Value |
|--------|-------|
| **Accuracy** | 88.3% |
| **Precision** | 54.5% |
| **Recall** | 74.2% |

**Confusion Matrix:**
```
Predicted →    No Churn    Churn
Actual No Churn:  523        55
Actual Churn:      23        66
```

## Key Findings

- **CustomerServiceCalls** — Higher number of calls increases churn probability
- **Long Tenure** — Longer tenure decreases churn probability
- The model uses a **threshold of 0.3** (instead of default 0.5) to prioritize recall — catching more true churners at the cost of some precision
- **Recall of 74.2%** means the model identifies about 3 out of every 4 customers who will churn

## Why Recall Matters Here

In churn prediction, **missing a churner is more costly** than falsely flagging a loyal customer. Lowering the threshold from 0.5 to 0.3 improved recall from 43% to 74%, making the model much more useful for business decisions.

## How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/<your-username>/customer-churn-prediction.git
   cd customer-churn-prediction
   ```

2. Install dependencies:
   ```bash
   pip install pandas scikit-learn openpyxl
   ```

3. Add the `Telco Churn dataset.xlsx` file to the project folder

4. Open the notebook:
   ```bash
   jupyter notebook Customer_Churn_Prediction_Logistic_Regression.ipynb
   ```
   Or open it in [Google Colab](https://colab.research.google.com/)

## Dependencies

- Python 3.7+
- pandas
- scikit-learn
- openpyxl (for reading `.xlsx` files)

## Author

Built as a machine learning assignment on Customer Churn Prediction using Logistic Regression.
