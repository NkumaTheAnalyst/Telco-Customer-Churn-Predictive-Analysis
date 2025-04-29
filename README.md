# Telco-Customer-Churn-Predictive-Analysis

**1. Introduction**  
This report outlines the analysis and modeling process for predicting customer churn using a logistic regression model. The dataset used is the Telco Customer Churn dataset, which includes customer demographics,   service usage, and billing information. The goal is to identify factors influencing churn and evaluate model performance.  
  
**2. Data Overview**  
Dataset: 21 features, including SeniorCitizen, Contract, InternetService, MonthlyCharges, and the target variable Churn.  

**Class Distribution:**  

Original dataset had an imbalance between churn ("Yes": 1,869, "No": 1,869).  

A balanced subset was created by undersampling the majority class ("No") to match the minority class ("Yes").  

**3. Methodology**  
Data Preprocessing  
Balancing: Equal samples of churn ("Yes") and non-churn ("No") cases were selected.  

Feature Engineering: Categorical variables (e.g., Contract, InternetService) were converted into dummy variables.  

Train-Test Split: 80% training, 20% testing.  

**Model Building**  
Algorithm: Logistic Regression (with default hyperparameters).  

**Key Steps:**  

Standardization of features.  

Training on the balanced dataset.  

**4. Results**  
Model Performance  
Confusion Matrix:  

[[264  105]  
 [ 65  314]]    
Accuracy: 77%  

Precision/Recall:  

No Churn: Precision = 80%, Recall = 72%  

Churn: Precision = 75%, Recall = 83%  

Key Features Influencing Churn  
**Contract Type:**  

Contract_Month-to-month (Coefficient = +1.03, Odds Ratio = 2.8) strongly increases churn likelihood.  

Contract_Two year (Coefficient = -1.15, Odds Ratio = 0.32) reduces churn risk.  

**Internet Service:**  

InternetService_Fiber optic (Coefficient = +0.33) correlates with higher churn.  

InternetService_DSL (Coefficient = -0.34) reduces churn likelihood.  

Senior Citizen Status: Positive coefficient (+0.26) suggests seniors are slightly more likely to churn.  

Notable Observation: Many TotalCharges categories had zero coefficients, indicating minimal impact or potential redundancy.  

**5. Visualization**
Confusion Matrix Heatmap: Highlighted correct predictions (diagonal) and misclassifications.  

**6. Limitations**  
Convergence Warning: The logistic regression model did not fully converge, suggesting a need for increased iterations or adjusted hyperparameters.  

High Cardinality: Features like TotalCharges were split into many dummy variables (3,544 total features), likely leading to overfitting or noise.  

Simplistic Model: Logistic regression may not capture non-linear relationships; ensemble methods (e.g., Random Forest) could improve performance.  

**7. Business Implications**  
Actionable Insights:  

Focus retention efforts on customers with month-to-month contracts and fiber optic users.  

Promote long-term contracts (e.g., discounts for two-year commitments).  

Cost-Saving: Prioritizing high-risk customers can reduce marketing expenses.  

**8. Recommendations**  
Feature Reduction: Aggregate or bin high-cardinality variables (e.g., TotalCharges).  

Model Enhancement: Experiment with regularization, tree-based models, or neural networks.  

Data Enrichment: Include additional features like customer satisfaction scores.  

**9. Conclusion**  
The logistic regression model achieved moderate accuracy (77%) and identified key drivers of churn, notably contract type and internet service. Addressing these factors can help reduce customer attrition. Future work should refine feature engineering and explore advanced algorithms for better predictive power.  
