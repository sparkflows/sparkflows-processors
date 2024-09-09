Sarimax
=========== 

Seasonal Autoregressive Integrated Moving Average, SARIMA or Seasonal ARIMA, is an extension of ARIMA that explicitly supports univariate time series data with a seasonal component.

Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ts.NodeStatsModelSarimax

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - endog
        - Endog Column
        - The observed time-series process Eg:col1
      * - exogenous
        - Exogenous Columns
        - An optional 2-d array of exogenous variables. If provided, these variables are used as additional features in the regression operation. This should not include a constant or trend.
      * - order
        - Order
        - The (p,d,q) order of the model for the number of AR parameters, differences, and MA parameters. d must be an integer indicating the integration order of the process, while p and q may either be an integers indicating the AR and MA orders (so that all lags up to those orders are included) or else iterables giving specific AR and or MA lags to include. Default is an AR(1) model: (1,0,0)
      * - seasonal_order
        - Seasonal Order
        - The (P,D,Q,s) order of the seasonal component of the model for the AR parameters, differences, MA parameters, and periodicity. D must be an integer indicating the integration order of the process, while P and Q may either be an integers indicating the AR and MA orders (so that all lags up to those orders are included) or else iterables giving specific AR and / or MA lags to include.s is an integer giving the periodicity (number of periods in season), often it is 4 for quarterly data or 12 for monthly data. Default is no seasonal effect.
      * - trend
        - Trend
        - Parameter controlling the deterministic trend polynomial.Can be specified as a string where c indicates a constant (i.e. a degree zero component of the trend polynomial), t indicates a linear trend with time, and ct is both. Can also be specified as an iterable defining the non-zero polynomial exponents to include, in increasing order.
      * - measurement_error
        - Measurement Error
        - 
      * - time_varying_regression
        - Time Varying Regression
        - 
      * - mle_regression
        - Mle Regression
        - 
      * - simple_differencing
        - Simple Differencing
        - 
      * - enforce_stationarity
        - Enforce Stationarity
        - 
      * - enforce_invertibility
        - Enforce Invertibility
        - 
      * - hamilton_representation
        - Hamilton Representation
        - 
      * - concentrate_scale
        - Concentrate Scale
        - 
      * - trend_offset
        - Trend Offset
        - 
      * - use_exact_diffuse
        - Use Exact Diffuse
        - 
      * - fit
        - Fit
      * - transformed
        - Transformed
        - 
      * - includes_fixed
        - Includes Fixed
        - 
      * - cov_type
        - Cov Type
        - 
      * - method
        - Method
        - 
      * - maxiter
        - Maxiter
        - 
      * - full_output
        - Full Output
        - 
      * - optim_score
        - OptimScore
        - The method by which the score vector is calculated. like harvey, approx
      * - optim_complex_step
        - Optim Complex Step
        - 
      * - optim_hessian
        - Optim Hessian
        - The method by which the Hessian is numerically approximated. opg, oim & approx




