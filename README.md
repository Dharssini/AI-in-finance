

# <div align="center">Bitcoin price prediction using ARIMA, XGBoost, LSTM and FBProphet</div>
<div align="center"><img src="https://github.com/Pradnya1208/Bitcoin-Price-Prediction-using-ARIMA/blob/main/output/intro.gif?raw=true"></div>


## Overview:
Bitcoin is the longest running and most well known cryptocurrency, first released as open source in 2009 by the anonymous Satoshi Nakamoto. Bitcoin serves as a decentralized medium of digital exchange, with transactions verified and recorded in a public distributed ledger (the blockchain) without the need for a trusted record keeping authority or central intermediary. Transaction blocks contain a SHA-256 cryptographic hash of previous transaction blocks, and are thus "chained" together, serving as an immutable record of all transactions that have ever occurred. As with any currency/commodity on the market, bitcoin trading and financial instruments soon followed public adoption of bitcoin and continue to grow. Included here is historical bitcoin market data at 1-min intervals for select bitcoin exchanges where trading takes place.
### Time series analysis:
Time Series is a series of observations taken at specified time intervals usually equal intervals. Analysis of the series helps us to predict future values based on previous observed values. In Time series, we have only 2 variables, time & the variable we want to forecast.

### Components of Time Series:
There are 4 components:<br>
- **Trend** - Upward & downward movement of the data with time over a large period of time. Eq: Appreciation of Dollar vs rupee.
- **Seasonality** - seasonal variances. Eq: Icecream sales increases in Summer only
- **Noise or Irregularity** - Spikes & troughs at random intervals
- **Cyclicity** - behavior that repeats itself after large interval of time, like months, years etc.

### ARIMA Model:
ARIMA(Auto Regressive Integrated Moving Average) is a combination of 2 models AR(Auto Regressive) & MA(Moving Average). It has 3 hyperparameters - P(auto regressive lags),d(order of differentiation),Q(moving avg.) which respectively comes from the AR, I & MA components. The AR part is correlation between prev & current time periods. To smooth out the noise, the MA part is used. The I part binds together the AR & MA parts.
<br>
In order to find the values of P and Q, We need to take help of ACF(Auto Correlation Function) & PACF(Partial Auto Correlation Function) plots. ACF & PACF graphs are used to find value of P & Q for ARIMA. We need to check, for which value in x-axis, graph line drops to 0 in y-axis for 1st time.
From PACF(at y=0), get P
From ACF(at y=0), get Q
## Dataset:
[Bitcoin Historical Data](https://www.kaggle.com/mczielinski/bitcoin-historical-data)

CSV files for select bitcoin exchanges for the time period of Jan 2012 to December March 2021, with minute to minute updates of OHLC (Open, High, Low, Close), Volume in BTC and indicated currency, and weighted bitcoin price. Timestamps are in Unix time. Timestamps without any trades or activity have their data fields filled with NaNs. If a timestamp is missing, or if there are jumps, this may be because the exchange (or its API) was down, the exchange (or its API) did not exist, or some other unforeseen technical error in data reporting or gathering.
## Implementation:

**Libraries:**  `NumPy` `pandas` `datetime` `matplotlib` `sklearn` `seaborn` `statsmodels`



