# 🛍️ Social Media Purchase Prediction

This project is a simple machine learning model that predicts whether a user will make a purchase based on their demographics and salary, using data from a social media platform.

---

## 📌 Project Overview

Using supervised learning, a classification model is trained to predict user purchase behavior based on:

- **Gender**
- **Age**
- **Estimated Salary**

---

## 📊 Dataset

The dataset contains the following columns:

| Column Name       | Description                       |
|-------------------|-----------------------------------|
| User ID           | Unique identifier for each user   |
| Gender            | Male/Female (encoded as 0/1)      |
| Age               | Age of the user                   |
| EstimatedSalary   | Estimated yearly salary (in ₹)    |
| Purchased         | Target: 0 (No), 1 (Yes)           |

---

## ⚙️ Model Pipeline

1. **Data Preprocessing**
   - Encoding gender
   - Feature scaling
   - Splitting into train/test sets

2. **Model Training**
   - Logistic Regression (or other classifiers)
   - Evaluation using accuracy

3. **Model Saving**
   - Trained model saved using `joblib` as `social_media.pkl`

---

## 🧪 How to Use

### ▶️ Load and Predict

```python
import joblib

# Mapping predicted output
out = {0: "Nil", 1: "purchase"}

# Load the saved model
loaded_model = joblib.load('social_media.pkl')

# Input Format: [Gender (1 = Male, 0 = Female), Age, Estimated Salary]
y_pred = loaded_model.predict([[1, 19, 19000]])

# Get readable label
predicted_label = out.get(y_pred[0], "unknown")
print("Predicted Output:", predicted_label)
