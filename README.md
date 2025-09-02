# 🏦 Credit Default Prediction

This project predicts whether a person will **default on their credit card payment** in the next month using machine learning models.  
It uses classification algorithms such as **Logistic Regression, LightGBM, and XGBoost**, and evaluates them with multiple metrics.

---

## 📌 Project Purpose
Credit default prediction is crucial for **financial institutions** (like banks, credit card companies, and fintech firms).  
It helps in:
- Assessing customer **credit risk**  
- Reducing **financial losses**  
- Improving **loan approval processes**  
- Ensuring **responsible lending**

---

## 📂 Dataset
-Source: https://www.kaggle.com/datasets/kushjain08/loan-default

- **Features include**:  
  - `LIMIT_BAL` → Credit limit  
  - `SEX` → Gender  
  - `EDUCATION` → Education level  
  - `MARRIAGE` → Marital status  
  - `AGE` → Age  
  - `PAY_0, PAY_2, PAY_3...` → Past monthly payment records  
  - `BILL_AMT1, BILL_AMT2...` → Previous bill amounts  
  - `PAY_AMT1, PAY_AMT2...` → Previous payment amounts  

- **Target Variable**:  
  - `default.payment.next.month` → (1 = Default, 0 = No Default)

---

## ⚡ Steps Followed
### 1. Data Preparation  
- Merged **train** and **test** sets for consistency  
- Handled **missing values**  
- Encoded **categorical variables**  
- Applied **scaling** with StandardScaler  
- Performed **feature selection**

### 2.Exploaratory Data Analysis (EDA)
- Understand feature distributions and correlations.
- Visualize default vs non-default patterns.

### 3. Model Training  
We trained three models:  
- Logistic Regression  
- LightGBM  
- XGBoost  

### 4. Model Evaluation  
Metrics used:  
- **ROC AUC**  
- **Precision-Recall AUC (PR AUC)**  
- **F1-score**  

📊 Comparison charts were plotted for all models:
- ROC AUC bar plot  
- PR AUC bar plot  
- F1-score bar plot  

### 5. Best Model Selection  
- The **best model** was chosen based on **ROC AUC / PR AUC**  
- The trained model was **saved using joblib**  

### 6. Predictions on Test Data  
- Loaded the saved model  
- Scaled the test dataset  
- Generated predictions (`submission.csv`)  

---

## 📊 Results
- Best performing model: XGBoost
- ROC AUC: 0.778478
- PR AUC:  0.276089
-  F1: 0.078578

---

## 🛠️ Tech Stack
- **Python** 🐍  
- **Pandas / NumPy** → Data processing  
- **Scikit-learn** → ML pipeline, metrics, Logistic Regression  
- **LightGBM & XGBoost** → Gradient boosting models  
- **Matplotlib / Seaborn** → Visualization  
- **Joblib** → Model saving  

---

## 📈 Example Usage
If someone wants to check whether a person will **default or not**, they need to provide values for all input features, such as:

```json
{
  "LIMIT_BAL": 20000,
  "SEX": 1,
  "EDUCATION": 2,
  "MARRIAGE": 1,
  "AGE": 30,
  "PAY_0": 0,
  "PAY_2": -1,
  "PAY_3": 0,
  "BILL_AMT1": 3913,
  "PAY_AMT1": 0,
  ...
}
