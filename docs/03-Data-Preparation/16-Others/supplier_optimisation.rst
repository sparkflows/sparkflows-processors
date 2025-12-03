Supplier Optimization
===========



Type
--------- 

pyspark2inputs

Class
--------- 

fire.nodes.lpo.NodeSupplierOptimisation

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - lead_week
        - Lead Week
        - Weeks before project start for allowing delivery.
      * - DeliveryWeek
        - Delivery Week
        - If -1, deliver by endWeek. Else, deliver by startWeek + DeliveryWeek.
      * - MinMaxLevel
        - MinMax Level
        - Project (apply Min/Max PCT at project level) or Product (per product).
      * - bundle_size
        - Bundle Size
        - Fixed units per bundle.
      * - solver_choice
        - Solver Choice
        - Solver name: HiGHS or CBC
      * - gap_rel
        - Gap Rel
        - Relative optimality gap for solver.
      * - running_time
        - Running Time
        - Solver timeout in seconds.




