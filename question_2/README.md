# Summary

## **Question** 

Purely based on historical returns since 01 January 2011, which Indian E&P company would you invest in? How did you calculate the returns?

## **Answer**

### Data

We download historical data (01/01/2011 - 05/08/2023) about 5 Idian E&P companies from YahooFinance. These datas belong to National Stock Exchange of India Limited (NSE).

* <a href="https://finance.yahoo.com/quote/RELIANCE.NS/history?p=RELIANCE.NS" target="_blank">Reliance Industries Limited (RIL)</a>

* <a href="https://finance.yahoo.com/quote/ONGC.NS/history?p=ONGC.NS" target="_blank">Oil and Natural Gas Corporation Limited (ONGC)</a>

* <a href="https://finance.yahoo.com/quote/PETRONET.NS/history?p=PETRONET.NS" target="_blank"> Petronet LNG Limited (PETRONET)</a>

* <a href="https://finance.yahoo.com/quote/OIL.NS/history?p=OIL.NS" target="_blank"> Oil India Limited (OIL)</a>

* <a href="https://finance.yahoo.com/quote/HINDOILEXP.NS/history?p=HINDOILEXP.NS" target="_blank">Hindustan Oil Exploration Company Limited (HINDOILEXP)</a>

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
            <th colspan=2>Models</th>
            <th>RIL</th>
            <th>ONGC</th>
            <th>PETRONET</th>
            <th>OIL</th>
            <th>HINDOILEXP</th>
            <th>Avg R2</th>
            <th>Weight</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=2>kNN</td>
            <td>R-Squared</td>
            <td>0.8696</td>
            <td>0.8979</td>
            <td>0.7846</td>
            <td>0.8670</td>
            <td>0.9111</td>
            <td rowspan=2>0.86604</td>
            <td rowspan=2>1.25</td>
        </tr>
        <tr>
            <td>Predictions</td>
            <td>0.0224</td>
            <td>0.1370</td>
            <td>-0.0524</td>
            <td>0.0798</td>
            <td>0.3161</td>
        </tr>
        <tr>
            <td rowspan=2>Linear Regression</td>
            <td>R-Squared</td>
            <td>0.8908</td>
            <td>0.9094</td>
            <td>0.8386</td>
            <td>0.9108</td>
            <td>0.9202</td>
            <td rowspan=2>0.89396</td>
            <td rowspan=2>1.5</td>
        </tr>
        <tr>
            <td>Predictions</td>
            <td>0.0141</td>
            <td>0.1072</td>
            <td>0.0329</td>
            <td>0.1209</td>
            <td>0.3435</td>
        </tr>
        <tr>
            <td rowspan=2>Gradient Boosting Trees</td>
            <td>R-Squared</td>
            <td>0.8526</td>
            <td>0.8967</td>
            <td>0.7504</td>
            <td>0.8742</td>
            <td>0.9140</td>
            <td rowspan=2>0.85758</td>
            <td rowspan=2>1</td>
        </tr>
        <tr>
            <td>Predictions</td>
            <td>0.2105</td>
            <td>0.2877</td>
            <td>0.2951</td>
            <td>0.3759</td>
            <td>0.5184</td>
        </tr>
        <tr>
            <td colspan=2>Stock Score</td>
            <td>0.25965</td>
            <td>0.61975</td>
            <td>0.27895</td>
            <td>0.657</td>
            <td>1.428775</td>
            <td colspan=2></td>
        </tr>
    </tbody>
</table>

We choose Indian E&P company to invest in 3 steps: 

* **Step 1:** Calculate the average R-Squared score of each model on 5 stocks. After that, we assign weight for each model based on its average R-Squared.

* **Step 2:** Calculate score for each company's stock according the formula: $Stock~Score_j = \sum Predictions_{i,j}*Weight_{i}$ where $Predictions_{i,j}$ is Prediction of model $i$ for stock $j$ and $Weight_{i}$ is weight of model $i$.

* **Step 3:** Choosing the model has the best $Stock~Score$.

After following these step, we choose Hindustan Oil Exploration Company Limited (HINDOILEXP) invest.

There are some images predicting the Returns of HINDOILEXP stock in the next 30 days:

* **kNN**

![HINDOILEXP_kNN](https://github.com/thangdv509/dtl-2023/assets/74363928/fb90d606-9124-4715-bce9-5c12a44de1c3)

* **Linear Regression**

![HINDOILEXP_LR](https://github.com/thangdv509/dtl-2023/assets/74363928/c2c5d009-5f3f-4d58-882a-90774b45886c)

* **Gradient Boosting Tree**

![HINDOILEXP_xgb](https://github.com/thangdv509/dtl-2023/assets/74363928/b6558811-0044-4b1c-aa78-bdd3d54dcb38)
