# Customer Churn Prediction using Deep Learning

This project builds a **binary classification model** to predict **customer churn** using the **Telco Customer Churn dataset**. The objective is to identify customers who are likely to leave a telecom service based on demographic, service usage, and billing information.

---

## 📌 Dataset
- **Source:** Telco Customer Churn Dataset
- **Rows:** 7,043 customers
- **Target Variable:** `Churn` (Yes / No)
- **Features:** Demographics, services subscribed, contract type, payment method, tenure, and billing details

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

- Dropped irrelevant column: `customerID`
- Converted `TotalCharges` from object to numeric
- Removed rows with missing `TotalCharges`
- Encoded binary categorical features (`Yes/No`, `Male/Female`)
- One-hot encoded multi-class categorical features:
  - `InternetService`
  - `Contract`
  - `PaymentMethod`
- Feature scaling using **MinMaxScaler** on:
  - `tenure`
  - `MonthlyCharges`
  - `TotalCharges`

Final feature count: **26**

---

## 📊 Exploratory Data Analysis (EDA)

- Churn vs Tenure distribution
- Churn vs Monthly Charges distribution
- Clear observation:  
  - Customers with **shorter tenure** and **higher monthly charges** are more likely to churn

---

## 🧠 Model Architecture

A **Neural Network** built using **TensorFlow / Keras**:

```text
Input Layer: 26 features
Hidden Layer 1: Dense (26 neurons, ReLU)
Hidden Layer 2: Dense (15 neurons, ReLU)
Output Layer: Dense (1 neuron, Sigmoid)
