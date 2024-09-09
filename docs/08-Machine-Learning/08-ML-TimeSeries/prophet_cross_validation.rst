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




