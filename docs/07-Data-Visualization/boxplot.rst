Box Plot
=========== 



Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeBoxPlot

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
      * - chartColors
        - Chart Colors
      * - xlabel
        - X Label
      * - ylabel
        - Y Label
      * - maxValuesToDisplay
        - Max Values To Display
        - Maximum number of values to display in result.
      * - groupByColumn
        - Group By Column
      * - valueColumn
        - Value Column


Details
-------


BoxPlot details
+++++++++++++++

This node shows the five-number summary of a set of data including the minimum score, first (lower) quartile, median, third (upper) quartile, and maximum score.

Input
```````````````

*    TITLE :- The title of a graph can be set here.
*    X LABEL :- X-axis label can be set here.
*    Y LABEL :- Y-axis label can be set here.
*    MAX VALUES TO DISPLAY :- The total number of the data points can be selected from dataframe.
*    GROUP BY COLUMN :- The column is selected from the drop-down list to perform group by operation and aggregate the values and plot them on X-axis.
*    VALUE COLUMN :- The column(double datatype) is selected to plot boxes along Y-axis.


Output
```````````````

*    The output result will contain <b>Min values, First quartile, Median, Third quartile, and max value</b>.


Example
```````````````

*    This node can be used to visualize the distribution of quantitative values in a field. They are also valuable for comparisons across different 

    categorical variables or for identifying outliers.


