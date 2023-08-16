# Summary

## **Question** 

Identify key drivers for revenue and profitability. Forecast Revenue and EPS for any one company: ONGC or OIL.

## **Answer**

### Indentifying key drivers

* **Revenue Key Drivers**

Based on the E&P companies' activities, which normally revolve around the process of oil & gas geographical 
exploration, producing by drilling wells and providing those raw materials to refineries, distributors, retailers, 
etc. (downstream) through the process and transportation section (midstream), we've identified some common 
Key Revenue Drivers used by those companies, as shown below:

<p align="center"> 
  <img width="483" align="center" alt="Screenshot 2023-08-16 at 19 09 11" src="https://github.com/thangdv509/dtl-2023/assets/74363928/9a245ff5-a9c7-4005-b33f-24e6007fa9ea">

  <p align="center"> <b>Figure 1.</b> Revenue Key Drivers of E&P companies </p>
</p>

* **Profitability Key Drivers**

There are numerous Key Drivers for Profitability that are being used among E&P companies, however, Profitability 
Drivers are mostly identified as financial ratios because of simplistic calculations and analysis for either 
companies or investors. These ratios are commonly categorized into 2 groups: Margin Ratios and Return Ratios, 
as shown in Figure below:

<p align="center"> 
  <img width="442" alt="Screenshot 2023-08-16 at 19 10 15" src="https://github.com/thangdv509/dtl-2023/assets/74363928/c201baa0-5df9-4b4a-b201-8be79d8d0d62">

  <p align="center"> <b>Figure 2.</b> Profitability Key Drivers of E&P companies </p>
</p>

* **Earnings per Share (EPS) Key Drivers**

Based on the Basic EPS formula, key drivers of EPS are listed in the following figure:

<p align="center"> 
  <img width="543" alt="Screenshot 2023-08-16 at 19 11 33" src="https://github.com/thangdv509/dtl-2023/assets/74363928/5399b8ab-0ec7-4c73-9cba-3cec8e35dff7">

  <p align="center"> <b>Figure 3.</b> EPS Key Drivers of E&P companies </p>
</p>

### Forecasting Revenue and EPS for OIL Company

After analyzing data from India E&P to see which is worth the investment, we discovered that an 
OIL company could bring more benefits for investors than that of ONGC. Therefore, in this section, 
OIL company is selected to forecast its Revenue and EPS within the next 5 years, based on the 
historical data from 2014 to 2023.

* **Method:** ARIMA Model on IBM SPSS Software. ARIMA model serves as a statistical tool employed
for time series forecasting, it contains three core components Autoregressive (AR),
Integration (I), and Moving Average (MA), which are shortened to p, d, and
q respectively:

* **Step:** The process of forecasting OIL’s Revenue and EPS is summarized through 4 steps

  * Importing the historical data from OIL’s annual reports to SPSS.
 
  *  Plotting the time series values to see if they are linear or quadratic.
 
  *  Determining p, d, q values.
 
  *  Run the ARIMA forecasting model and interpret the results.
 

* **Results:**

  * Revenue:
  
| Fiscal Year | Total Revenue (million $) | Crude Oil Revenue  (million $) | Natural Gas Revenue (million $) | Other Products Revenue (million $) |
|:-----------:|:-------------------------:|:------------------------------:|:-------------------------------:|:----------------------------------:|
|     2024    |          4,390.64         |            2,664.44            |             1,567.15            |               159.05               |
|     2025    |          6,729.62         |            3,362.61            |             3,165.55            |               201.46               |
|     2026    |         10,034.03         |            4,213.63            |             5,573.09            |               247.31               |
|     2027    |         14,517.99         |            5,258.49            |             8,962.88            |               296.62               |
|     2028    |         27,418.55         |            13,534.59           |            13,534.59            |               349.37               |
  

  * EPS:

| Fiscal Year | EPS (USD) |
|:-----------:|:---------:|
|     2024    |    0.82   |
|     2025    |    0.78   |
|     2026    |    0.75   |
|     2027    |    0.72   |
|     2028    |    0.68   |
