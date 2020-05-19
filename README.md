# Forecasting vegetable prices in an Indian market seeting (a typical mandi)
The problem required to forecast the minPrice , maxPrice and modalprice

Libraries Used : pandas, numpy, matplotlib and statsmodels libraries in Python 

Approach:

1. Basic preprocessing of data, dropping unnecessary features to create three timeseries data for min , max and modal prices.

2. Removing duplicate index values (priceDate column is treated as index) and of the three varieties in "variety" column, only Potato is 
   used as the frequecy of "Potato" was significantly higher than other two varieties. (Shown in notebook)

3. Creating seperate series for min , max and modal prices and forecast

4. I have taken simple log transformation of data to make the time series stationary by penalising extreme values in data.

5. I have used ARIMA (Autoregressive integrated moving average) model to fit the data and forecast for the next 30 days.

6. For the q and p (p,d,q) tuple of the "order" parameter of the model, I have used the Autocorrelation and Partial Autocorrelation plots 
   respectively, d is taken as 0 as no difference is taken.

Possible Improvements:

1. The ARIMA model can be trained on higher values of q as evident in Autocorrelation plot.
2. The missing values corresponding to missing dates have been taken through linear interpolation. Perhaps more complex interpolation
   can be used or the missing data can itself be predicted or be taken as average of n previous observations, where n is the optimum
   number of lagged observations
3. To make the timeseries stationary, log transformation is taken, other methods can be used such as taking residual of data after
   removing trend and seasonality , differencing exponentially weighted moving average from the data.

Difficulties faced :
1. training ARIMA model on higher values of q
2. dealing with negative correlation near the origin (such was the case when differencing was used to make timeseries stationary.)   
     
