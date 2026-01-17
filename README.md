Telecom Churn Prediction
A Supervised Learning project to identify high-risk customers using Random Forest.

📌 The Problem
The goal of this project is to predict which customers are likely to leave a telecom provider. Instead of just looking for "Accuracy," I focused on Recall—because missing a customer who is about to leave is more expensive for the business than a false alarm.

🛠️ Technical Highlights
Data Pipeline: Connected directly to Kaggle via API for a cloud-native workflow.

Cleaning: Identified and handled "Hidden Nulls" in TotalCharges (converting objects to numeric).

Feature Engineering: Used One-Hot Encoding to transform categories like "Contract Type" and "Internet Service" into machine-readable data.

Handling Imbalance: Applied class_weight='balanced' to ensure the model didn't ignore the minority "Churn" class.

📈 Key Insights
According to the model's Feature Importance, the top drivers for churn are:

Total Charges / Monthly Charges: Price sensitivity is the #1 factor.

Tenure: The first few months are the "danger zone" for new customers.

Contract Type: Long-term contracts significantly reduce the probability of leaving.

🚀 How to Run
Open Churn_Analysis.ipynb in Google Colab.

Provide your Kaggle API credentials.

Run the cells to see the evaluation and the saved model file (.pkg).
