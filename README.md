# Johns Hopkins COVID-19 India
---
## 1. Introduction
---
This project focuses on building a comprehensive COVID-19 forecasting framework for India using time-series data from the Johns Hopkins University repository. The objective is to analyze historical trends, build predictive models, evaluate their performance, and provide actionable insights for public health planning.

---
## 2. Dataset Overview
The dataset contains daily cumulative counts of confirmed cases, deaths, and recoveries reported globally. For this project, India-specific data was extracted and analyzed. Due to inconsistencies in recovery reporting, confirmed cases and deaths were used for modeling.

---
## 3. Exploratory Data Analysis (EDA)
EDA included trend analysis, daily case computation, rolling averages, growth rates, case fatality ratio, distribution analysis, and wave identification. These analyses revealed strong non-linearity, multiple pandemic waves, and high volatility, justifying the use of advanced machine learning and deep learning models.

---
## 4. Modeling Approach
The following models were implemented:
- Linear Regression
- ARIMA
- SARIMA
- Holt-Winters
- Prophet
- Random Forest
- XGBoost
- LSTM (tuned)

Each model was trained on historical data and evaluated using a common aligned evaluation window to ensure fair comparison.

---
## 5. Model Evaluation
Models were evaluated using MAE, RMSE, and residual analysis. LSTM achieved the lowest MAE and RMSE, indicating the best predictive accuracy. SARIMA emerged as the strongest classical statistical model. XGBoost demonstrated the most stable and randomly distributed residuals.

---
## 6. Residual Analysis
Residual analysis shows that ARIMA exhibits large and structured residuals, indicating poor adaptability to sudden changes in COVID-19 trends. SARIMA significantly improves upon ARIMA by modeling seasonality and achieves lower error metrics; however, its residuals still exhibit mild temporal structure, suggesting sensitivity to regime shifts and non-stationary behavior.

XGBoost demonstrates the most randomly distributed and stable residuals, with errors well-centered around zero and minimal visible structure. This indicates strong robustness to noise, reporting inconsistencies, and sudden changes in case trends, making XGBoost highly suitable for real-world deployment.

LSTM residuals are generally centered around zero and show no strong systematic bias, confirming the model’s high predictive accuracy. However, the residual distribution is wider and slightly skewed compared to XGBoost, indicating higher variance and reduced stability during abrupt surges. While LSTM excels in short-term prediction accuracy, its residual behavior suggests greater sensitivity to data volume and temporal window selection.

---
## 7. Final Model Selection
LSTM was identified as the best-performing model in terms of accuracy. However, XGBoost was selected as the production-ready model due to its robustness, stability, and ease of deployment. Justification:
•	Demonstrated more stable and well-behaved residuals compared to other models
•	Robust to noise, reporting inconsistencies, and sudden case fluctuations
•	Easier to deploy, monitor, and retrain in real-world systems
•	Computationally efficient and less sensitive to data size
•	More interpretable than deep learning models
Although LSTM achieved the lowest MAE and RMSE, XGBoost was selected as the production model due to its superior residual stability, robustness, and operational reliability.


---
## 8. Recommendations
- Proactive healthcare capacity planning
- Medical resource stockpiling
- Targeted interventions during predicted surges
- Integration of forecasting into monitoring dashboards

---
## 9. Conclusion
This project presents a comprehensive and well-validated COVID-19 forecasting framework for India, incorporating detailed exploratory data analysis along with multiple statistical, machine learning, and deep learning models, evaluated using consistent and rigorous performance criteria.

Among all evaluated models, LSTM achieved the highest predictive accuracy, as reflected by the lowest MAE and RMSE values, demonstrating its strong capability in learning temporal dependencies and short-term trends. SARIMA emerged as the best-performing classical statistical model, delivering competitive error metrics by effectively modeling seasonality and trend components. However, XGBoost exhibited the most stable and well-behaved residual patterns, indicating greater robustness to noise, reporting inconsistencies, and sudden fluctuations in case trends.

Accordingly, LSTM is identified as the best model in terms of prediction accuracy, SARIMA as the strongest traditional time-series model, and XGBoost as the most reliable and production-ready model. Together, these findings provide a balanced and technically sound foundation for informed public health planning and decision-making.

LSTM → Best prediction accuracy

SARIMA → Best classical statistical model

XGBoost → Best residual behavior & production stability

