## Bartłomiej Adamiec

**Why this data?**

The dataset stands out from others, including holidays for, United States and payment days for SNAP programme benefit days (exogenous variables). The full dataset requires forecasting for 30 490 simultaneous time series organized hierarchically: States → Stores → Categories → Departments → Products.

**Goal:**

The object of this analysis is to optimize food inventory management to prevent stockouts and minimize overstocking. This is particularly critical for fresh food categories due to their limited shelf life.

**Kaggle:**

A popular platform for data analysts and machine learning engineers. It organizes competitions for data community, collect datasets etc. People can share their work e.g. Jupyter Notebooks.

**Dataset description:**

Competition data (M5 Forecasting - Accuracy) from Kaggle. Task in competition was to predict sales in Walmart chain-store for next 28 days period. Dataset
consists of 5 `.csv` files reminding relational database in star scheme. The historical sales (`sales_train_validation.csv`) is fact table, time (`calendar.csv`) and prices (`sales_prices.csv`) are dimensions tables.

**Short files description**

* `sell_prices.csv` - contains the unit price of products in USD per store and week.
* `calendar.csv` - provides information about dates (various formats), SNAP entitlement days, and holidays.
* `sales_train_validation.csv` -  historical daily unit sales data per product and store in wide format (covering days d_1 to d_1913).
* `sales_train_evaluation.csv` - identical to validation but includes next 28 days. Released after the competition.
* `sample_submission.csv` - the required submission format for competition participants.

[Source](https://www.kaggle.com/competitions/m5-forecasting-accuracy/datam)

## Conclusions
An increase in overall food sales at Walmart. This isn't a large trend, but it is noticeable and confirmed by the Kendall's Tau test.
Possible explanations:
* Population growth in California/USA
* Attractive prices at the massive discount store
* Walmart's monopolization of the market

Slight increase in loose and processed foods. I think it's worth to deep into it.

The days with the **lowest** sales volume are consistently **Christmas** (25.12.XXXX), when sales drop to zero due to store closures.

**Strong weekly seasonality:**
* Peak of sales volume - Saturdays
* Lowest sales volume - Tuesdays and Wednesdays

Foods combined are non-stationary in both tests. Ambiguous non-stationarity for time series grouped by departments, both KPPS (non-stationary around trend) and ADF (stationary) are significant. This suggests that time series are difference stationary. In ARIMA I would need to difference before training model, but in Holt - Winters I don't have to.

Residuals from STL decomposition do not follow a normal distribution. Very high kurtosis due to high fluctuations in extreme values.

The **"Fresh Food"** department (produce, raw meat) accounts for t**he highest sales volume.**

Despite of my earlier assumptions simpler model show better predictions. Prophet predicted with bigger error (MAPE = 10.67%) than Holt - Winters exponential smoothing for additional trend and seasonality (MAPE = **7.09%**). Which positions my predictions in **top of the competition's results.**
