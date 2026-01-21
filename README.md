# 📡 Telecom Churn Prediction: High-Recall Engineering
> **Optimizing customer retention through Ensemble Learning and Cost-Sensitive Analysis.**

## 📌 Executive Summary
A machine learning solution to minimize revenue loss by predicting customer attrition. In this project, I prioritized **Recall (Sensitivity)** over global Accuracy to ensure that 80% of at-risk customers are identified for proactive retention, acknowledging that the cost of a lost customer far outweighs the cost of a false-positive intervention.

## 🛠️ Technical Implementation
* **Data Engineering:** Automated ingestion via Kaggle API. Handled data leakage and "Hidden Nulls" in `TotalCharges` using type-coercion and imputation.
* **Feature Architecture:** * Implemented **One-Hot Encoding** for categorical variance.
    * Addressed 3:1 class imbalance using **Synthetic Weighting (`class_weight='balanced'`)** to prevent model bias toward the majority class.
* **Benchmarking:** Evaluated Traditional Ensembles (Random Forest, XGBoost) against Deep Learning (ANN) architectures.

## 📈 Performance Comparison
| Metric | Random Forest (Winner) | XGBoost | Neural Network (ANN) |
| :--- | :--- | :--- | :--- |
| **Recall (Churn)** | **0.80** | 0.79 | 0.73 |
| **Accuracy** | 0.78 | 0.79 | 0.76 |
| **Interpretability** | High | Medium | Low |

## 🚀 Key Engineering Insights
1. **The "Danger Zone":** Feature importance reveals that **Tenure** is the strongest predictor; the first 6 months are critical for intervention.
2. **Contract Optimization:** Month-to-month contracts are the primary churn driver. Business recommendation: Incentivize migration to annual contracts.
3. **Architecture Choice:** While the ANN utilized ReLU/Sigmoid layers and `StandardScaler` normalization, it failed to outperform the **Random Forest** on Recall. 

## 💻 Deployment & Reproducibility
* **Environment:** Google Colab / Python 3.10+
* **Dependencies:** `scikit-learn`, `xgboost`, `tensorflow`, `pandas`
* **Execution:** Use the provided `.ipynb` to load the saved `.pkg` model and run real-time inference on new customer batches.
