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

🤖 Deep Learning Extension (ANN)I implemented an Artificial Neural Network (ANN) using TensorFlow/Keras to benchmark against the Random Forest model.

Key Technical Implementations:
Scaling: Applied StandardScaler to normalize features for the neural network.
Architecture: Designed a sequential model with ReLU activation in hidden layers and Sigmoid for the output.
Cost-Sensitive Learning: Implemented class_weights to address the 3:1 imbalance between stayers and churners.

📊 Final Comparison & Decision
Metric                      Random Forest (Winner)       Neural Network
Overall Accuracy             ~78%                        76%
Recall(Catching Churners)    ~80%                        73%
Model Complexity             Low (Interpretive)          High (Black Box)

Conclusion: While the Neural Network is a more "advanced" architecture, the Random Forest remains the superior choice for this business case. It provides a higher Recall, ensuring we catch more customers before they leave, and is easier to explain to business stakeholders.

## 📊 Final Performance Comparison
After testing three distinct architectures, here are the results for catching churners (Recall):

| Model | Technology | Recall (Churn) | Verdict |
| :--- | :--- | :--- | :--- |
| **Random Forest** | Ensemble | ~80% | **Winner: Best for Business** |
| **XGBoost** | Gradient Boosting | 79% | High Performance / Industry Standard |
| **Neural Network** | Deep Learning | 73% | Complex / Prone to Overfitting |

**Project Conclusion:** For this dataset, the **Random Forest** provided the highest recall, making it the most cost-effective solution for identifying customers likely to leave.

