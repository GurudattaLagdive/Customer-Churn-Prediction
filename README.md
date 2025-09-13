# 📊 Customer Churn Prediction (Telco Dataset)

## 🔎 Overview
Customer churn is one of the biggest challenges for subscription-based businesses.  
This project uses **machine learning** to predict whether a customer will **leave (churn)** or **stay** based on their service details and account information.  

We built a **Random Forest Classifier** and used **SMOTEENN** to handle class imbalance.  
The final trained model is saved as `model.sav` and can be served through APIs for integration with a User Interface (UI).  

---

## 📂 Dataset
- **Source:** [Kaggle – Telco Customer Churn Dataset](https://www.kaggle.com/blastchar/telco-customer-churn)  
- **Records:** 7,043 customers  
- **Features:**  
  - Demographic: gender, senior citizen, partner, dependents  
  - Account: tenure, contract type, payment method  
  - Services: phone service, internet service, streaming services  
  - Target: `Churn` (Yes/No)  

---

## ⚙️ Workflow
1. **Data Preprocessing**
   - Handle missing values  
   - Encode categorical variables  
   - Normalize numerical features  

2. **Imbalance Handling**
   - Dataset is imbalanced (`Churn ~26%` vs `No Churn ~74%`)  
   - Applied **SMOTEENN** = SMOTE (oversampling minority) + ENN (cleaning noise)  

3. **Model Training**
   - Algorithm: **Random Forest Classifier**  
   - Parameters: `max_depth=6`, `min_samples_leaf=8`, `random_state=42`  

4. **Model Saving**
   - Trained model dumped as `model.sav` using `joblib`  

5. **API Development**
   - Built a REST API with **Flask / FastAPI**  
   - Input: Customer details in JSON  
   - Output: Prediction (`Churn = Yes/No`)  

---

## 📊 Model Performance

- **Accuracy:** 0.93 (~93%)  
- **Precision:** 0 → 0.92, 1 → 0.93  
- **Recall:** 0 → 0.91, 1 → 0.94  
- **F1-Score:** 0 → 0.92, 1 → 0.94  

The model predicts both "Churn" and "Not Churn" accurately and handles class imbalance well.

*(Values are approximate, update with your actual results)*  

---

## 📂 Project Structure
