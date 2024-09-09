Arima
=========== 

AutoARIMA

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ts.NodeAutoARIMA

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - y
        - Y
        - The time-series to which to fit the ARIMA estimator
      * - default_model
        - Default Model
        - Ignore all the parameters and build a default model
      * - exogenous
        - Exogenous Columns
        - An optional 2-d array of exogenous variables. If provided, these variables are used as additional features in the regression operation. This should not include a constant or trend.
      * - start_p
        - start_p
        - The starting value of p, the order (or number of time lags) of the auto-regressive (“AR”) model. Must be a positive integer.
      * - d
        - d
        - The order of first-differencing. If None (by default), the value will automatically be selected based on the results of the test.
      * - start_q
        - start_q
        - The starting value of q, the order of the moving-average (“MA”) model. Must be a positive integer.
      * - max_p
        - max_p
        - The maximum value of p, inclusive. Must be a positive integer greater than or equal to start_p.
      * - max_d
        - max_d
        - The maximum value of d, or the maximum number of non-seasonal differences. Must be a positive integer greater than or equal to d.
      * - max_q
        - max_q
        - The maximum value of q, inclusive. Must be a positive integer greater than start_q.
      * - start_P_seasonal
        - start_P_seasonal
        - The starting value of P, the order of the auto-regressive portion of the seasonal model.
      * - D_seasonal
        - D_seasonal
        - The order of the seasonal differencing. If None (by default, the value will automatically be selected based on the results of the seasonal_test. Must be a positive integer or None.
      * - start_Q_seasonal
        - start_Q_seasonal
        - The starting value of Q, the order of the moving-average portion of the seasonal model.
      * - max_P_seasonal
        - max_P_seasonal
        - The maximum value of P, inclusive. Must be a positive integer greater than start_P.
      * - max_D_seasonal
        - max_D_seasonal
        - The maximum value of D. Must be a positive integer greater than D.
      * - max_Q_seasonal
        - max_Q_seasonal
        - The maximum value of Q, inclusive. Must be a positive integer greater than start_Q.
      * - max_order
        - max_order
        - If the sum of p and q is >= max_order, a model will not be fit with those parameters, but will progress to the next combination. Default is 5. If max_order is None, it means there are no constraints on maximum order.
      * - m
        - m
        - The period for seasonal differencing, m refers to the number of periods in each season.
      * - seasonal
        - Seasonal
        - Whether to fit a seasonal ARIMA. Default is True
      * - stationary
        - Stationary
        - Whether the time-series is stationary and d should be set to zero.
      * - information_criterion
        - Information Criterion
        - The information criterion used to select the best ARIMA model.
      * - alpha
        - Alpha
        - Level of the test for testing significance.
      * - test
        - Test
        - Type of unit root test to use in order to detect stationarity if stationary is False and d is None. Default is kpss (Kwiatkowski–Phillips–Schmidt–Shin).
      * - seasonal_test
        - Seasonal Test
        - This determines which seasonal unit root test is used if seasonal is True and D is None. Default is OCSB.
      * - stepwise
        - Stepwise
        - Whether to use the stepwise algorithm to identify the optimal model parameters. 
      * - trend
        - Trend
        - The trend parameter. If with_intercept is True, trend will be used. If with_intercept is False, the trend will be set to a no- intercept value..
      * - method
        - Method
        - The method determines which solver from scipy.optimize is used.
      * - maxiter
        - Maxiter
        - The maximum number of function evaluations. Default is 50.
      * - trace
        - Trace
        - Whether to print status on the fits.
      * - random
        - Random
        - Similar to grid searches, auto_arima provides the capability to perform a “random search” over a hyper-parameter space. If random is True, rather than perform an exhaustive search or stepwise search, only n_fits ARIMA models will be fit (stepwise must be False for this option to do anything).
      * - random_state
        - Random State
        - The PRNG for when random=True. Ensures replicable testing and results.
      * - n_fits
        - N Fits
        - If random is True and a “random search” is going to be performed, n_iter is the number of ARIMA models to be fit.
      * - out_of_sample_size
        - Out of Sample Size
        - The ARIMA class can fit only a portion of the data if specified, in order to retain an “out of bag” sample score. This is the number of examples from the tail of the time series to hold out and use as validation examples. The model will not be fit on these samples, but the observations will be added into the model’s endog and exog arrays so that future forecast values originate from the end of the endogenous vector
      * - scoring
        - Scoring
        - The metric to use for scoring the out-of-sample data. One of (mse, mae)
      * - with_intercept
        - With Intercept
        - Whether to include an intercept term. Default is “auto” which behaves like True until a point in the search where the sum of differencing terms will explicitly set it to True or False.




