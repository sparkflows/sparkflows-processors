VAR
=========== 



Type
--------- 

ml-estimator

Class
--------- 

fire.nodes.ts.NodeStatsModelVAR

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - maxlags
        - MaxLags
        - Maximum number of lags to check for order selection, defaults to 12 * (nobs/100.)**(1./4), see select_order function
      * - method
        - Method
        - Estimation method to use.
      * - ic
        - Information Criterion
        - Information criterion to use for VAR order selection. They can be aic:Akaike, fpe:Final prediction error, hqic:Hannan-Quinn, bic:Bayesian
      * - trend
        - Trend
        - One of these trends can be used c:add constant, ct:constant and trend, ctt:constant,linear and quadratic trend, n:no constant and no trend




