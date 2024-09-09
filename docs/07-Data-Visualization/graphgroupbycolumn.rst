Graph Group By Column
=========== 

Groups the data by the given column and plots the number of records in each group

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeGraphGroupByColumn

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
      * - titleColor
        - Title Color
      * - description
        - Description
      * - descriptionColor
        - Description Color
      * - xlabel
        - X Label
      * - ylabel
        - Y Label
      * - maxValuesToDisplay
        - Max Values To Display
        - Maximum number of values to display in result.
      * - chartColors
        - Chart Colors
      * - groupByColumn
        - Group By Column
      * - graphType
        - Chart Type


Details
-------


Graph Group By Column Details
+++++++++++++++

This node represents the distribution/count of a group of data in Graphical format.

A numeric column from the incoming dataset is selected to aggregate data into multiple groups. The count of data points in each group is plotted in the Chart.

The chart type used to represent data can be selected in the node.

Input
```````````````

*    TITLE :- The title of a graph can be set here.
*    X LABEL :- X-axis label can be set here.
*    Y LABEL :- Y-axis label can be set here.
*    MAX VALUES TO DISPLAY :- The total number of data points can be selected here.
*    CHART COLORS :- The different types of color can be selected for better visualization.
*    GROUP BY COLUMN :- A categorical column is selected to show the counts of observations of each category.
*    CHART TYPE :- The desired chart can be selected from the drop-down list(Column chart, Bar Chart, Line Chart)


 Output
```````````````

*    This node is good for comparing between each element in the categories and comparing elements across categories.


