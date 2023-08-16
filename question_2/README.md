# Summary

## **Question** 

Purely based on historical returns since 01 January 2011, which Indian E&P company would you invest in? How did you calculate the returns?

## **Answer**

### Data

We download historical data (01/01/2011 - 05/08/2023) about 5 Idian E&P companies from YahooFinance. These datas belong to National Stock Exchange of India Limited (NSE).

1. <a href="https://finance.yahoo.com/quote/RELIANCE.NS/history?p=RELIANCE.NS" target="_blank">Reliance Industries Limited (RIL)</a>

2. <a href="https://finance.yahoo.com/quote/ONGC.NS/history?p=ONGC.NS" target="_blank">Oil and Natural Gas Corporation Limited (ONGC)</a>

3. <a href="https://finance.yahoo.com/quote/PETRONET.NS/history?p=PETRONET.NS" target="_blank"> Petronet LNG Limited (PETRONET)</a>

4. <a href="https://finance.yahoo.com/quote/OIL.NS/history?p=OIL.NS" target="_blank"> Oil India Limited (OIL)</a>

5. <a href="https://finance.yahoo.com/quote/HINDOILEXP.NS/history?p=HINDOILEXP.NS" target="_blank">Hindustan Oil Exploration Company Limited (HINDOILEXP)</a>

6. <a href="https://finance.yahoo.com/quote/GUJGASLTD.NS/history?p=GUJGASLTD.NS" target="_blank">Gujarat Gas Limited (GUJGASLTD)</a>

7. <a href="https://finance.yahoo.com/quote/IOC.NS/history?p=IOC.NS" target="_blank">Indian Oil Corporation Limited (IOC)</a>

8. <a href="https://finance.yahoo.com/quote/CHENNPETRO.NS/history?p=CHENNPETRO.NS" target="_blank">Chennai Petroleum Corporation (CHENNPETRO)</a>

9. <a href="https://finance.yahoo.com/quote/MRPL.NS/history?p=MRPL.NS" target="_blank">Mangalore Refinery & Petrochemicals (MRPL)</a>

10. <a href="https://finance.yahoo.com/quote/BPCL.NS/history?p=BPCL.NS" target="_blank">Bharat Petroleum Corporation Limited (BPCL)</a>

### Historical returns calculation

We decide to use **EMA (Exponential Moving Average) Returns** because the original form of Historical Returns is very sensitive to price fluctuations, and maybe not suitable for forecasting. 

When applying EMA, we calculate Historical Return following 3 steps:

* Calculate the daily returns using the formula: $Daily~Return_t = \frac{AC_{t} - AC_{t-1}}{AC_{t-1}}$

* Calculate the smoothing factor (alpha) for the EMA: $\alpha = \frac{2}{period + 1}$

* Calculate the Historical return for each day using the formula: $R_t = R_{t-1} + \alpha*(Daily~Return_t - R_{t-1})$

### Method

* Using **Machine Learning** to forecast the Future Returns of each stocks.

* Making decision bases on model's results.

### Machine Learning model

* **Goal:** Based on the Historical return of a certain stock, feed the data into a prediction model and use that data to make predictions about the future returs of that stock.

* **Method:** Bagging Ensemble Learning. (Train more than one models. Each model will be trained independently. The results based on all model results.)

* **Models:** 
    * Linear Regression 

    * Gradient Boosting Tree 
    
    * k-Nearest Neighbors

* **Evaluate:** 
    * RMSE (Root Mean Squared Error) 

    * R-Squared

### Results

We used EMA-60days (The period of 2 months) for predicting.

The predictions and models evaluating are presented on the table: 

<table>
    <thead>
        <tr>
            <th rowspan=2 colspan=2>Models</th>
            <th colspan=2>kNN</th>
            <th colspan=2>Linear Regression</th>
            <th colspan=2>Gradient Boosting Tree</th>
            <th rowspan=2 colspan=2>Stock Score</th>
        </tr>
       <tr>
            <th colspan=1>${R^2}$</th>
            <th colspan=1>Average Return</th>
            <th colspan=1>${R^2}$</th>
            <th colspan=1>Average Return</th>
            <th colspan=1>${R^2}$</th>
            <th colspan=1>Average Return</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td colspan=2>MRPL</td>
            <td>0.9313</td>
            <td>0.3002</td>
            <td>0.9410</td>
            <td>0.3398</td>
            <td>0.9290</td>
            <td>0.4222</td>
            <td colspan=2>1.3072</td>
        </tr>
        <tr>
            <td colspan=2>OIL</td>
            <td>0.8671</td>
            <td>0.2781</td>
            <td>0.9108</td>
            <td>0.1131</td>
            <td>0.8742</td>
            <td>0.3762</td>
            <td colspan=2>0.8935</td>
        </tr>
        <tr>
            <td colspan=2>CHENNPETRO</td>
            <td>0.9328</td>
            <td>0.2621</td>
            <td>0.9602</td>
            <td>0.1452</td>
            <td>0.9524</td>
            <td>0.3282</td>
            <td colspan=2>0.8736</td>
        </tr>
        <tr>
            <td colspan=2>ONGC</td>
            <td>0.8979</td>
            <td>0.1679</td>
            <td>0.9094</td>
            <td>0.1001</td>
            <td>0.8965</td>
            <td>0.2876</td>
            <td colspan=2>0.6476</td>
        </tr>
        <tr>
            <td colspan=2>PETRONET</td>
            <td>0.7834</td>
            <td>0.0640</td>
            <td>0.8384</td>
            <td>0.0429</td>
            <td>0.7497</td>
            <td>0.2933</td>
            <td colspan=2>0.4377</td>
        </tr>
        <tr>
            <td colspan=2>IOC</td>
            <td>0.9086</td>
            <td>0.0088</td>
            <td>0.9333</td>
            <td>0.0634</td>
            <td>0.9089</td>
            <td>0.2195</td>
            <td colspan=2>0.3256</td>
        </tr>
        <tr>
            <td colspan=2>RELIANCE</td>
            <td>0.8697</td>
            <td>0.0224</td>
            <td>0.8907</td>
            <td>0.0140</td>
            <td>0.8522</td>
            <td>0.2110</td>
            <td colspan=2>0.2600</td>
        </tr>
        <tr>
            <td colspan=2>BPCL</td>
            <td>0.8848</td>
            <td>-0.0750</td>
            <td>0.9114</td>
            <td>-0.0405</td>
            <td>0.8704</td>
            <td>0.2366</td>
            <td colspan=2>0.2036</td>
        </tr>
        <tr>
            <td colspan=2>HINDPETRO</td>
            <td>0.8980</td>
            <td>-0.0853</td>
            <td>0.9244</td>
            <td>-0.0429/td>
            <td>0.9073</td>
            <td>0.3118</td>
            <td colspan=2>0.1408</td>
        </tr>
        <tr>
            <td colspan=2>GUJGASLTD</td>
            <td>0.8883</td>
            <td>-0.0313</td>
            <td>0.9057</td>
            <td>-0.0865/td>
            <td>0.8820</td>
            <td>0.1848</td>
            <td colspan=2>0.0159</td>
        </tr>
        <tr>
            <td colspan=2>Average ${R^2}$</td>
            <td colspan=2>0.88673</td>
            <td colspan=2>0.91253</td>
            <td colspan=2>0.88226</td>
        </tr>
       <tr>
            <td colspan=2>Weight</td>
            <td colspan=2>1.25</td>
            <td colspan=2>1.5</td>
            <td colspan=2>1</td>
        </tr>
    </tbody>
</table>

We choose Indian E&P company to invest in 3 steps: 

* **Step 1:** Calculate the average R-Squared score of each model on 5 stocks. After that, we assign weight for each model based on its average R-Squared.

* **Step 2:** Calculate score for each company's stock according the formula: $Stock~Score_j = \sum Predictions_{i,j}*Weight_{i}$ where $Predictions_{i,j}$ is Prediction of model $i$ for stock $j$ and $Weight_{i}$ is weight of model $i$.

* **Step 3:** Choosing the model has the best $Stock~Score$.

After following these step, we choose Mangalore Refinery & Petrochemicals (MRPL) invest.

There are some images predicting the Returns of MRPL stock in the next 30 days:

* **kNN**

![knn](https://github.com/thangdv509/dtl-2023/assets/74363928/b90c9718-2b55-457e-b3ab-ff3938a09705)

* **Linear Regression**

![linear_regression](https://github.com/thangdv509/dtl-2023/assets/74363928/ece1da38-18d9-4c3a-abf8-0e42647b3359)

* **Gradient Boosting Tree**

![gradient_boosting_tree](https://github.com/thangdv509/dtl-2023/assets/74363928/2a38c853-b69e-4380-a161-abb83c9444ca)

