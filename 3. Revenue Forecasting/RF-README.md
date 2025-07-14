# 🎬 Forecasting New Release Revenue

This project demonstrates a data-driven approach to forecasting digital revenue for new film releases using historical performance indicators.

---

## 🎯 1. Problem

Forecasting revenue for new film releases was previously a manual and often inaccurate process. This project was initiated to develop a more reliable and data-driven method to predict **New Release Revenue** using historical performance indicators. The goal was to improve forecast accuracy and reduce the time spent manually estimating revenue outcomes.

---

## 🧠 2. Method

To tackle the problem, I explored how different **film genres** behave in terms of revenue generation. By identifying genre groupings that exhibited similar performance patterns, I was able to cluster films in a way that preserved predictive power without fragmenting the dataset too much. This balance allowed for meaningful generalisation while maintaining model robustness.

Additional data exploration, cleaning, and transformation of the data were performed prior to loading the data. Through this exploration, it was determined that **UK Box Office**, **Film Genre**, and **Days to Digital Release** were the most strongly correlated factors influencing digital revenue. These factors were also picked as forecasts often need to be set **well ahead of digital release**, and in many cases even **before theatrical release**, to support **marketing campaign planning**, **budget allocation**, and **film greenlighting** decisions.

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

> **Disclaimer**: This notebook is a local recreation of the actual forecasting process. For data protection reasons, real data and predictions cannot be included. The primary goal of the provided notebook is to outline the project structure and its process.

---

## 📈 4. Results

### Statistical Results 

The UK market is constantly undergoing changes due to release strategy, retailer landscape changes, covid and strike implications so once there are more years of comparable data this model is expected to improve in future iterations.

- R-Squared for this version of the model was 0.76 and adjusted r-squared was 0.74 so explains approximately 76% of the variance in New Release Revenue, with the adjusted value accounting for the number of predictors—indicating a strong overall fit. Given the complexity and variability of film performance and limited number of releases per year to include, 0.76 is a strong result 

- UK Box Office is the most significant predictor (coef = 0.7795, p < 0.001), while Genre_2 also shows a meaningful positive effect (coef = 0.9467, p = 0.008); other predictors like Days to Release and most genres have higher p-values (> 0.05), suggesting limited individual impact.

- UK Box Office has a tight 95% confidence interval ([0.635, 0.924]), reinforcing its reliability in predicting digital revenue.

### Outcomes

The model significantly improved the accuracy of our revenue forecasts. By automating the prediction process, it also reduced the time spent manually estimating outcomes. This approach has since been used to support strategic decisions around release timing and marketing investment allowing us to react quicker when films have a poor theatrical performance.
