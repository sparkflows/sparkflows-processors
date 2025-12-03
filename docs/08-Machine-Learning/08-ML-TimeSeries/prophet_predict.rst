Prophet Predict
===========



Type
--------- 

ml-predict

Class
--------- 

fire.nodes.ts.NodeProphetPredict

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description


Details
-------
Prophet Predict Node Details
+++++++++++++++


This node generates predictions using a trained Prophet model. The output includes forecasted timestamps and associated values based on the time series data provided.


ds: Schema detail of the output DataFrame, representing timestamps.

Output Storage Level: Specifies the storage persistence level for the output DataFrame.


Examples
-------
Prophet Predict Node Examples
+++++++++++++++


Example Configuration:


Output:


Given a trained Prophet model and an input DataFrame containing future timestamps, the node will output a DataFrame with the schema:


ds

timestamp

Example:


Input DataFrame with timestamps:


ds

2023-12-01

2024-01-01

2024-02-01

The node processes these timestamps and outputs the predictions based on the Prophet model, appending forecasted values to this structure.
