Prophet Cross Validator
===========



Type
--------- 

ml-predict

Class
--------- 

fire.nodes.ts.NodeProphetCrossValidation

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - horizon
        - Horizon
        - String with pd.Timedelta compatible style, e.g., '5 days','3 hours', '10 seconds'.
      * - period
        - Period
        - String with pd.Timedelta compatible style. Simulated forecast will be done at every this period. If not provided, 0.5 * horizon is used.
      * - initial
        - Initial
        - String with pd.Timedelta compatible style. The first training period will include at least this much data. If not provided,3 * horizon is used.
      * - cutoffs
        - Cutoffs
        - list of pd.Timestamp specifying cutoffs to be used during cross validation. If not provided, they are generated as described above.




Examples
-------
Prophet Cross Validator Node Examples
+++++++++++++++


Example 1: Evaluating Forecast Accuracy for Demand


Input Schema:

Time-series data with columns such as "Date" and "Demand".

Configuration:

Horizon: "30 days" (e.g., evaluating forecasts for the next 30 days).

Period: "15 days" (e.g., cutoffs occur every 15 days).

Initial: "90 days" (e.g., initial training period covers 90 days).

Output:

Metrics such as Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE) for each fold of the cross-validation.

Example 2: Cross-Validation for Monthly Revenue Prediction


Input Schema:

Time-series data with columns "Month" and "Revenue".

Configuration:

Horizon: "3 months".

Period: "1 month".

Initial: "12 months".

Output:

Forecast error metrics aggregated across all cutoff points.
