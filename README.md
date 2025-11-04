# Time Series Analysis and Forecasting Report

## Dataset Description  
The dataset contains the following features:  
- DateLocal  
- RouteLight RailPeak Service  
- Rapid Route  
- School  
- Other  

![alt text](image-9.png)

The data spans different dates and includes counts or measures for each route category. The "DateLocal" feature was set as the index and the data was sorted based on it.

## Exploratory Data Analysis (EDA)  
- Missing values and outliers were handled by dropping the respective rows to ensure clean data quality.
![alt text](image-4.png) 
- All the time series commponents were decomposed using STL decompose method because of non-assuption characteristic.
![alt text](image-3.png) 
- Stationarity was tested using the Augmented Dickey-Fuller (ADF) test. The p-value was found to be less than 0.05 indicating the series is non-stationary and requires differencing or other transformations. 
- Anomaly detection was carried out but no significant anomalies were detected in the data. 
![alt text](image-2.png) 
- Autocorrelation Function (ACF) and Partial Autocorrelation Function (PACF) plots were created for all target attributes to determine appropriate model orders.

## Model Development and Results  
Five models were fit to different routes with the following configurations and evaluation results:

| Route          | Model           | MAE (Mean Absolute Error) |
|----------------|-----------------|---------------------------|
| Local Route    | ARIMA(10,0,1)   | 1929.28                   |
| Light Rail     | ARIMA(10,0,1)   | 970.56                    |
| Peak Service   | ARIMA(3,1,1)    | 85.38                     |
| Rapid Route    | SARIMA(4,0,10)   | 2203.35                 |
| School         | ARIMA(4,1,8)    | 947.39                    |

## Forecasting for 7-days
![alt text](image-5.png)
![alt text](image-6.png)
![alt text](image-7.png)
![alt text](image-10.png)
![alt text](image-1.png)

## Insights  
Here’s a **concise version** of your insights — short, clear, and presentation-ready 👇

---

Perfect 👍 Here’s your **Insights + Actionable Recommendations** section — concise, professional, and ready to include in your report:

---

Here’s a **concise, stakeholder-focused version** of your **Actionable Insights** section — written to clearly link data findings to strategic decisions 👇

---

### Actionable Insights for Stakeholders

1. **Increase Service Capacity on Local Routes**
   Steady ridership growth indicates a need for capacity expansion or more frequent trips to maintain service quality and reduce overcrowding.

2. **Optimize Scheduling for Rapid Routes**
   Strong seasonal trends suggest aligning fleet availability and driver shifts with peak months to improve efficiency and minimize idle resources.

3. **Investigate Light Rail Performance Drop (Oct 2024)**
   A ridership decline during this period may point to operational disruptions or external factors; reviewing maintenance logs and passenger feedback could identify root causes.

4. **Leverage Stable Time Series for Predictive Planning**
   Since the data is stationary, stakeholders can rely on consistent trend patterns for accurate forecasting and data-driven decision-making.

5. **Use Forecast Insights for Budget and Policy Decisions**
   The projected upward trend in ridership can guide long-term investment planning, infrastructure upgrades, and policy formulation to meet future transport demand.



### Recommendations for Further Improvement


* **Experiment with Advanced Models:**
  Beyond ARIMA and Prophet, consider exploring models like **SARIMA**, **Exponential Smoothing (ETS)**, or **machine learning approaches** (e.g., LSTM, XGBoost). These can capture more complex temporal patterns, particularly for routes with higher forecast errors such as *Rapid Route*.

* **Incorporate External Factors:**
  Including relevant external variables (e.g., weather conditions, holidays, special events) as regressors can enhance the model’s ability to explain variability in ridership trends.


***