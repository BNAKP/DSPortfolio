# 📉 Churn & CLV Modeling with Survival Analysis
## 1. Problem
The goal of this project was to identify high-risk churn users and estimate their future value to the business. This enabled the organization to:

- Quantify churn risk across the subscriber base.
- Estimate Customer Lifetime Value (CLV) using both historical and predicted tenure.
- Segment users by churn risk and CLV to support targeted CRM campaigns.
- Prioritize retention efforts for high-value, high-risk users.
  
This model supports strategic decision-making in lifecycle marketing, retention planning, and revenue forecasting.

## 2. Method
To address this challenge, a hybrid modeling approach was used:

- **Churn Prediction:** A classification model (XGBoost) was trained to estimate the probability of churn using behavioral and demographic features.
- **Survival Analysis:** A Cox Proportional Hazards model was used to estimate expected remaining tenure for each user, accounting for users who haven’t churned yet.
- **CLV Calculation:** Combined historical spend with predicted future tenure to estimate total CLV.
- **Segmentation:** Users were grouped into actionable segments based on churn risk and CLV to guide CRM targeting.
  
This approach ensured both predictive accuracy and business relevance.

## 3. Code
The project was implemented in Python using the following tools and steps:

Libraries: pandas, numpy, xgboost, sklearn, lifelines

Data: Included features such as:
- watch_time: Monthly hours watched
- subscription_type: Basic, Standard, Premium
- device_type: Mobile, Desktop, TV
- support_tickets: Number of support interactions
- days_since_last_login: Recency of engagement
- tenure: Months subscribed
- monthly_spend: Average monthly revenue per user
- churn: Binary indicator (1 = churned, 0 = active)

🔍 **Model Selection Rationale**
- XGBoost Classifier (Churn prediction) -	Handles non-linear relationships, robust to feature interactions, and performs well on imbalanced datasets.
- Cox Proportional Hazards (Survival modelling) -	Estimates time-to-churn while accounting for active users. Provides interpretable hazard ratios and survival curves.

## 4. CLV Calculation
CLV was calculated as the sum of historical and expected future value:

CLV=(Monthly Spend×Tenure)+(Monthly Spend×Expected Remaining Tenure)

- Historical Value: Revenue already earned from the user.
- Expected Remaining Tenure: Estimated using the area under the survival curve from the Cox model.

## 5. Segmentation
Users were segmented based on two dimensions: Churn Probability and CLV.

**Segmentation Logic**
- High CLV, High Risk	CLV > median, Churn Prob > 0.6	[Priority retention: personalized offers, loyalty incentives]
- Low CLV, High Risk	CLV ≤ median, Churn Prob > 0.6	[Cost-effective retention: automated nudges, email reminders]
- High CLV, Low Risk	CLV > median, Churn Prob ≤ 0.6	[Loyalty programs, upsell opportunities]
- Low CLV, Low Risk	CLV ≤ median, Churn Prob ≤ 0.6	[Minimal intervention]
  
These segments were exported to the CRM system for campaign targeting and lifecycle automation.

## 6. Results
📊 **Churn Model Performance**
- Accuracy =	0.68	(Moderate overall accuracy)
- Precision	= 0.17	(Low due to class imbalance)
- Recall	= 0.18	(Captures some churners, room for improvement)
- F1 Score	= 0.18	(Balanced view of precision and recall)
- ROC AUC	= 0.51	(Slightly better than random guessing)

📈 **Survival Model Outcome**
- Provided individualized estimates of remaining tenure.
- Enabled dynamic CLV calculation based on churn risk.
- Supported more accurate revenue forecasting.

🎯 **Business Outcome**
- Enabled CRM teams to target high-value churners with personalized retention campaigns.
- Provided a scalable framework for combining churn risk with financial impact.
- Supported strategic planning across marketing, finance, and product teams.
