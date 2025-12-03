Bar Chart
===========

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeBarChart

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
      * - titleColor
        - Title Color
        - 
      * - description
        - Description
        - 
      * - descriptionColor
        - Description Color
        - 
      * - xlabel
        - X Label
        - 
      * - ylabel
        - Y Label
        - 
      * - maxValuesToDisplay
        - Max Values To Display
        - Maximum number of values to display in result.
      * - graphType
        - Chart Type
        - 
      * - chartColors
        - Chart Colors
        - 
      * - isStreaming
        - Is Streaming?
        - Whether the Graph is a Streaming Graph or not
      * - stacked
        - Stacked
        - Create a stacked bar chart by setting the isStacked option to true
      * - material
        - Material Chart
        - Select true will use material design
      * - dualAxis
        - Dual axis
        - Display axis on both side
      * - colorRange
        - Color Range
        - Bar colors will be selected based on min and max value range
      * - xCol
        - X Column
        - 
      * - xSortCol
        - Sort on X Column?
        - Whether to Sort on X column or not
      * - yCols
        - Y Columns
        - 
      * - ySortCol
        - Y Sort Column
        - 
      * - reNameYColumns
        - Rename Y Columns
        - 


Details
-------
Bar Chart Node
+++++++++++++++


This node creates a bar chart to visualize numerical data. It allows you to compare values across different categories or time periods .

You can rename columns,sort the categories and make changes in labels as needed for your visualisation


Examples
-------
Bar Chart Node Example
+++++++++++++++


Scenario:


Let's say you have a dataset with sales figures for different products over time. You can use the Bar Chart node to visualize the sales trends for each product.


Configuration:


1. **Color Range:** Enable or disable color-coding of the bars.

2. **X Column:** Select the column to be used as the X-axis (e.g., product name or time period).

3. **Sort on X Column:** Sort the bars based on the X-axis values.

4. **Y Columns:** Select one or more columns to be displayed on the Y-axis (e.g., sales figures).

5. **Y Sort Column:** Sort the Y-axis values.

6. **Rename Y Columns:** Rename the Y-axis columns for better clarity.


Output:


The node will generate a bar chart visualizing the selected data. You can customize the chart's appearance using various options, such as color palette, chart title, and axis labels.


Use Cases:



* Sales Analysis:Visualize sales trends over time or across different products.
* Financial Analysis:Compare financial metrics for different time periods or business units.
* Market Research: Analyze market share and customer preferences.
