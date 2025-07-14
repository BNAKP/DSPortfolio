# 🎬 Forecasting New Release Revenue

This project demonstrates a data-driven approach to forecasting digital revenue for new film releases using historical performance indicators.

---

## 🎯 1. Problem

Forecasting revenue for new film releases was previously a manual and often inaccurate process. This project was initiated to develop a more reliable and data-driven method to predict **New Release Revenue** using historical performance indicators. The goal was to improve forecast accuracy and reduce the time spent manually estimating revenue outcomes.

---

## 🧠 2. Method

To tackle the problem, I explored how different **film genres** behave in terms of revenue generation. By identifying genre groupings that exhibited similar performance patterns, I was able to cluster films in a way that preserved predictive power without fragmenting the dataset too much. This balance allowed for meaningful generalisation while maintaining model robustness.

Through this exploration, it was determined that **UK Box Office**, **Film Genre**, and **Days to Digital Release** were the most strongly correlated factors influencing digital revenue. These insights were especially valuable because forecasts often need to be set **well ahead of digital release**, and in many cases even **before theatrical release**, to support **marketing campaign planning**, **budget allocation**, and **film greenlighting** decisions.

> Additional exploration, cleaning, and transformation of the data were performed prior to this version. The primary goal of this notebook is to outline the project structure and its objectives.

---

## 🛠️ 3. Code

The project was built in Python using:
- **Pandas** and **NumPy** for data manipulation  
- **Seaborn** and **Matplotlib** for visualisation  
- **Scikit-learn** for linear regression modelling  
- **Statsmodels** for statistical diagnostics  

The script includes:
- Data cleaning and log transformation of skewed variables  
- Dummy encoding of categorical genres  
- Model training and evaluation using linear regression  
- Visualisation of actual vs predicted revenue  
- An example prediction scenario for a new film  

> ⚠️ **Disclaimer**: This notebook is a local recreation of the actual forecasting process. For data protection reasons, real data and predictions cannot be included.

---

## 📈 4. Results

The model significantly improved the accuracy of our revenue forecasts. By automating the prediction process, it also reduced the time analysts spent manually estimating outcomes. This approach has since been used to support strategic decisions around release timing and marketing investment.
