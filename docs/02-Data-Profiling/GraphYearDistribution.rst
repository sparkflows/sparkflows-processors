Graph Year Distribution
===========

This node Finds the distribution of Years from Date values

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeGraphYearDistribution

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - title
        - Title
        - 
      * - graphType
        - Chart Type
        - input graph type
      * - yCols
        - Y Columns
        - input to y axis


Details
-------
This node plots a graph depicting distribution of dataset against each Year derived from the specified Date column.


Graph can be plotted based on the chart type selected in the node.


Key Configuration Options:



* Output Storage Level: Specifies the storage level for the output data.
* Title: Sets the title of the graph.
* Chart Type: Selects the type of chart to be used (e.g., bar chart, line chart).
* Y Columns: Defines the columns to be used for the Y-axis of the graph.


Examples
-------
Example:


Input Data:


::

    | Timestamp | Value |
    |---|---|
    | 2020-11-27 10:00:00 | 10 |
    | 2021-11-28 12:30:00 | 15 |
    | 2022-11-29 14:15:00 | 8 |
    | ... | ... |


Output Graph :


The X-axis of the chart represents the years (2020, 2021, 2022, etc.), and the Y-axis represents the count or sum of values for each year. The height of each bar corresponds to the value associated with that year.
