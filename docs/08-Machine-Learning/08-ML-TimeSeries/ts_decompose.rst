TS Decompose
=========== 



Input
--------------
A Dataframe consists of times series. The dataframe must have two columns containing values and periods.

Output
--------------
A dataframe consists of original data along with trend, seasonal, and residuals

Type
--------- 

transform

Class
--------- 

fire.nodes.ts.NodeTSDecompose

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - period_name
        - Period Column
        - Select Date Column
      * - value_name
        - Value Column
        - Select Value Column
      * - model
        - Model
        - Type of seasonal component.
      * - period
        - Period
        - Period of the series.
      * - seasonal_name
        - Seasonal Name
        - Seasonal Name
      * - trend_name
        - Trend Name
        - Trend Name
      * - resid_name
        - Residual Name
        - Residual Name




