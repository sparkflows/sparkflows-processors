Prophet Make Future Dataframe
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.ts.NodeProphetMakeFutureDataframe

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - future_period
        - Future Period
        - Int number of periods to forecast forward.
      * - frequency
        - Frequency
        - Any valid frequency for pd.date_range, such as 'D' or 'M'.
      * - include_history
        - Include History
        - Boolean to include the historical dates in the dataframe for predictions


Details
-------
Prophet Make Future Dataframe Node Details
---------------


This node generates a future DataFrame for time series forecasting using the Prophet library. The generated DataFrame includes future periods and optionally includes historical data. Key parameters allow customization of the output, including the number of future periods, frequency of data points, and whether to include historical data.


PartID, SupplierID, PartName, PartCategory, PartQualityScore: Schema details of the generated DataFrame.

Output Storage Level: Defines the storage persistence level of the generated DataFrame.

Future Period: Number of future time steps to include.

Frequency: The granularity of time steps (e.g., MS for monthly start).

Include History: Boolean flag to specify whether historical data is included.


Examples
-------
Prophet Make Future Dataframe Node Examples
---------------


Example Configuration:


Future Period: 24

Frequency: MS (Monthly Start)

Include History: True

Output:


If the current DataFrame has data up to December 2023 and Future Period is set to 24 months, the generated DataFrame will include:


Historical data (if Include History is True).

Future timestamps extending to December 2025, with monthly granularity (MS frequency).

Schema of the output DataFrame:


::

    PartID    |SupplierID    |PartName    |PartCategory    |PartQualityScore
    string    |string        |string      |string          |integer

Note: The output will follow the schema defined above, ensuring compatibility with downstream nodes for time series analysis and forecasting.
