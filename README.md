This repository implements a Pairs trading strategy on Indian stocks (NSE NFO universe) using statistical arbitrage.

There are several methods of implementing stat-arb. One of the more common and robust methods is using cointegration.


**Cointegration Approach**

A. Rolling OLS

The cointegration method has been implemented in the notebook 'StatArb_Coint.ipnyb'.
1. In this method, we shortlist pairs of cointegrated stocks from a universe of stocks.
2. Then, we check the stationarity of the spread of these 2 stocks modeled using Ordinary Least Squares regression on a rolling window.
3. If the spread is stationary, we convert it to z-score and build a trading strategy based on mean reversion. 
4. Finally, we backtest this across all the pairs of stocks we had shortlisted.

We achieved strong results (CAGR: ~20% & IRR: ~80%) across 20 relevant pairs while avoiding any kind of data snooping.

B. Kalman Filter

Kalman filter is advanced method of predicting any estimate that has a state equation (governing laws) and a prior measurement (like sensors).
We will use the Kalman filter to make a better estimate of the spread of our pair of stocks about the spread/hedge ratio.


We end up having comparatively much narrower spread and significantly more trades when using the Kalman filter. When the trade threshold is optimized, we achieved much stronger results as well. (CAGR: & IRR )

We further plan to implement other approaches such as PCA, Copulas, etc and provide a benchmark of performance.
