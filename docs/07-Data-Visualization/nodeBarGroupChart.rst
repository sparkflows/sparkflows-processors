Bar Group Chart
===========

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeBarGroupChart

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
      * - xSort
        - X Axis Sorting order
        - Choose sorting for X-axis if needed.
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
      * - material
        - Material Chart
        - Select true will use material design
      * - percent
        - Use percent
        - Select true to present data in percent
      * - xCol
        - X Column
        - 
      * - groupByCol
        - Group by Column
        - 
      * - yCol
        - Y Column
        - 


Details
-------
Bar Group Chart Node
+++++++++++++++


This node creates a grouped bar chart to visualize data with multiple categories. Each group of bars represents a category, and the bars within each group represent different values depending on the grouping criteria.


Examples
-------
Bar Group Chart Node Example
+++++++++++++++


Scenario:


Let's say you have a dataset with sales figures for different products across multiple regions. You can use the Bar Group Chart node to visualize the sales for each product in each region.


Configuration:


1. **X Label:** Set the label for the X-axis (e.g., "Region").

2. **Y Label:** Set the label for the Y-axis (e.g., "Sales").

3. **X Axis Sorting Order:** Choose how to sort the groups on the X-axis (e.g., alphabetically, numerically).

4. **Max Values to Display:** Limit the number of groups displayed on the chart.

5. **Chart Type:** Select the type of chart (e.g., grouped bar chart, stacked bar chart).

6. **Chart Colors:** Customize the color palette for the bars.

7. **Is Streaming:** Enable or disable streaming updates to the chart.

8. **Material Chart:** Use Material Design for the chart's appearance.

9. **Use Percent:** Display the Y-axis values as percentages.

10. **X Column:** Select the column to be used for the X-axis (e.g., "Region").

11. **Group By Column:** Select the column to group the data by (e.g., "Product").

12. **Y Column:** Select the column to be used for the Y-axis (e.g., "Sales").


Output:


The node will generate a grouped bar chart visualizing the selected data. Each group of bars will represent a product, and the height of each bar will represent the sales for that product in a particular region.
