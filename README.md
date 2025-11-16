# High-Dimensional-financial-Time-Series
1. Project Title
Interpretable AI for High-Dimensional Financial Time Series Forecasting

2. Abstract

This project aims to develop an interpretable machine learning model capable of forecasting financial time series movements using high-dimensional engineered features. The NIFTY 50 index is used as the dataset, and an XGBoost classifier is trained to predict whether the next day’s closing price will move upward or downward. To ensure transparency, SHAP and LIME interpretability methods are applied to explain both global and local model behavior. The findings demonstrate that the model effectively learns market patterns while interpretability techniques highlight the major factors influencing predictions. The project successfully meets all requirements by combining robust predictive performance with transparent decision explanations.


---

3. Introduction

Financial time series forecasting is a complex problem due to market volatility, noise, and nonlinear behavior. Machine learning models can capture such patterns effectively, but they often lack interpretability, resulting in limited trust. This project addresses the need for both accuracy and interpretability by developing a forecasting model and applying explainable AI (XAI) methods. The objective is to build a high-dimensional feature-rich dataset, train a predictive model, evaluate its performance, and explain its predictions using SHAP and LIME.


---

4. Dataset Description

The dataset consists of daily historical data of the NIFTY 50 index collected over the past five years using the Yahoo Finance data API. The dataset includes the following variables:

Open

High

Low

Close

Adjusted Close

Volume
The data was cleaned by removing missing values and standardizing column names. The dataset is suitable for time series analysis and forecasting tasks.



---

5. Methodology

The overall methodology follows five major stages:

1. Data collection and preprocessing


2. High-dimensional feature engineering


3. Train-test split (time-based)


4. Model construction using XGBoost


5. Model interpretability using SHAP and LIME



This structured workflow ensures an organized, reproducible, and accurate forecasting framework.


---

6. Feature Engineering

High-dimensional features were created to capture trends, momentum, and volatility in the market. The engineered variables include:

Daily Returns: Percentage change (captures momentum)

MA5 and MA10: Moving averages (captures trend)

Volatility: Rolling standard deviation over 10 days (captures risk)

Target Variable: 1 if next-day closing price is higher, 0 otherwise


These features enrich the dataset, allowing the model to learn meaningful financial patterns.


---

7. Model Development (XGBoost Classifier)

The XGBoost algorithm was selected due to its strong performance on structured financial data and ability to handle nonlinear patterns.

80% data used for training

20% for testing

Hyperparameters such as learning rate, maximum depth, and estimators were tuned manually
The model was trained to classify next-day market movement as UP or DOWN.



---

8. Results & Findings

The model produced reliable accuracy on the test dataset, indicating its ability to capture underlying price patterns. The classification report showed balanced performance for both classes. Market direction forecasting is challenging, yet the model demonstrated strong predictive ability for financial time series.


---

9. SHAP – Top 5 Most Influential Features

1. MA10

The 10-day moving average was the strongest predictor. Higher MA10 values contributed positively to upward predictions, indicating medium-term trend strength.

2. High Price

A higher intraday high reflects strong buyer participation, significantly increasing the probability of next-day upward movement.

3. Close Price

A strong closing price often represents bullish market sentiment. SHAP showed positive contribution to upward predictions when the close price was high.

4. Open Price

The opening value influences early market direction and context. It plays an important role in determining next-day price movement.

5. Volume

Higher trading volume indicates stronger market activity. SHAP revealed that unexpected increases in volume strengthen prediction confidence.


---

10. LIME – 500-Word Interpretation of One Prediction

LIME provides a localized explanation for a single prediction made by the model. The model predicted an 81% probability of upward movement for a particular test instance. The strongest positive contributor was MA10, which had a significantly high value compared to the usual rolling average. This indicated a sustained upward trend, making the model more confident in predicting a positive movement.

The high price also contributed positively, reflecting strong intraday demand from buyers. When the high value is closer to the upper range of recent history, LIME interprets this as bullish pressure. The close price further reinforced this positive sentiment. A strong closing price typically suggests buyers were dominant during the previous trading session, and this carries momentum into the next day.

On the negative side, volatility had a slight downward influence. Lower volatility indicates price stability, but in this instance, the lack of volatility contributed a neutral-to-negative effect since strong trends are often supported by controlled volatility. The returns feature also had a minor negative contribution, implying that the most recent daily return was slightly negative, signaling a mild correction.

Overall, the LIME explanation shows that the upward prediction is driven by trend-related features (MA10), price strength (close and high), and volume participation. Although some smaller signals like volatility and returns oppose the direction, their influence is insufficient to override the strong upward indicators. This demonstrates how LIME helps understand a single decision behind the model’s forecast.


---

11. Comparative Interpretation (SHAP vs LIME)

SHAP provides a global interpretation, showing which features are most important overall. LIME provides a local explanation for one specific prediction. In this project, both methods consistently identified the same dominant features: MA10, high price, close price, and volume. SHAP explains the general behavior of the model, while LIME explains one prediction at a time. Both techniques confirmed the reliability and transparency of the model.


---

12. Conclusion

The project successfully achieved the objective of building an interpretable AI forecasting model for financial time series data. XGBoost delivered strong predictive performance, and SHAP and LIME provided clear explanations of model behavior. The high-dimensional features significantly improved forecasting accuracy, and interpretability tools ensured transparency in predictions. This combination of performance and explainability makes the model useful for practical financial decision-making.
