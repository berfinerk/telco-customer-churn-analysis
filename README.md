# Telco Customer Churn Prediction

This project predicts customer churn for a telecom company and converts model outputs into an actionable campaign targeting strategy.

## Dataset
- Source: Telco Customer Churn dataset
- Target variable: **Churn** (No/Yes → 0/1)

## Project Workflow
1. **Data Preparation**
   - Dropped identifier column (`customerID`)
   - Converted `TotalCharges` to numeric and handled missing values
   - One-hot encoded categorical variables

2. **Baseline Model: Logistic Regression**
   - Used as a reference model for churn prediction

3. **Model: Random Forest**
   - Trained a Random Forest classifier
   - Evaluated using confusion matrix, classification report, and ROC-AUC

4. **Threshold Tuning**
   - Different probability thresholds were tested
   - Final threshold selected: **0.35** to improve churn recall

5. **Model Interpretation**
   - Analyzed feature importance
   - Key drivers: tenure, MonthlyCharges, TotalCharges, contract type, payment method

6. **Actionable Output**
   - Customers segmented into risk groups: Low, Medium, High, Very High
   - **Very High (top 5%)** segment identified for retention campaigns

## Results
- Logistic Regression ROC-AUC: ~0.84
- Random Forest ROC-AUC: ~0.82
- Random Forest (threshold=0.35) churn recall: ~0.68

## Repository Structure
```text
data/
 └── raw/
     └── WA_Fn-UseC_-Telco-Customer-Churn.csv

notebooks/
 ├── 01_eda.ipynb           # Exploratory Data Analysis
 ├── 02_modelling.ipynb     # Baseline Logistic Regression
 └── 03_random_forest.ipynb # Random Forest, threshold tuning, feature importance, risk segmentation
```
## How to Run
1. Clone the repository
2. Install required libraries
3. Run notebooks in order:
   - `notebooks/01_eda.ipynb`
   - `notebooks/02_modelling.ipynb`
   - `notebooks/03_random_forest.ipynb`