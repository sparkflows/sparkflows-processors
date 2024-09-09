Prophet
=========== 



Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ts.NodeProphet

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - ds
        - DS Column
        - Date or DateTime variable
      * - y
        - Y
        - Target Variable
      * - growth
        - Growth
        - linear or logistic to specify a linear or logistic trend
      * - yearly_seasonality
        - Yearly Seasonality
        - Fit yearly seasonality.
      * - weekly_seasonality
        - Weekly Seasonality
        - Fit weekly seasonality.
      * - daily_seasonality
        - Daily Seasonality
        - Fit daily seasonality.
      * - seasonality_mode
        - Seasonality Mode
        - additive(default) or multiplicative
      * - interval_width
        - Interval Width
        - Float, width of the uncertainty intervals provided for the forecast
      * - changepoints
        - Changepoints
        - List of dates at which to include potential changepoints. If not specified, potential changepoints are selected automatically.
      * - changepoints_format
        - Changepoints Format
        - datetime format for the comma seperated Changepoint specified.
      * - n_changepoints
        - N Changepoints
        - Number of potential changepoints to include. Not used if input `changepoints` is supplied. If `changepoints` is not supplied, then n_changepoints potential changepoints are selected uniformly from the first `changepoint_range` proportion of the history.
      * - changepoint_range
        - Changepoint Range
        - Proportion of history in which trend changepoints will be estimated. Defaults to 0.8 for the first 80%. Not used if `changepoints` is specified.
      * - seasonality_prior_scale
        - Seasonality Prior Scale
        - Parameter modulating the strength of the seasonality model. Larger values allow the model to fit larger seasonal fluctuations, smaller values dampen the seasonality.
      * - holidays_prior_scale
        - Holidays Prior Scale
        - Parameter modulating the strength of the holiday components model, unless overridden in the holidays input. changepoint_prior_scale: Parameter modulating the flexibility of the automatic changepoint selection. Large values will allow many changepoints, small values will allow few changepoints.
      * - changepoint_prior_scale
        - Changepoint Prior Scale
        - Parameter modulating the flexibility of the automatic changepoint selection. Large values will allow many changepoints, small values will allow few changepoints.
      * - mcmc_samples
        - mcmc samples
        - Integer, if greater than 0, will do full Bayesian inference with the specified number of MCMC samples. If 0, will do MAP estimation.
      * - uncertainty_samples
        - Uncertainty Samples
        - Number of simulated draws used to estimate uncertainty intervals. Settings this value to 0 or False will disable uncertainty estimation and speed up the calculation.
      * - custom_seasonality
        - Custom Seasonality
        - Add a seasonal component with specified period, number of Fourier components, and prior scale. Input will be of form name=monthly,period=30.5,fourier_order=5,prior_scale=0.9(optional),mode=additive(optional).
      * - regressor
        - Regressor
        - Add an additional regressor to be used for fitting and predicting. Input will be of form name=column_name1,prior_scale=30.5(optional),standardize=auto(optional),mode=additive(optional):name=column_name2,prior_scale=40.5(optional),standardize=auto(optional),mode=additive(optional)
      * - country_holidays
        - Country Holidays
        - Built-in country holidays can only be set for a single country. Takes country as input like US




