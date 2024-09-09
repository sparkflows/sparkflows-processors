Graph Values
=========== 

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeGraphValues

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
      * - graphType
        - Chart Type
      * - chartColors
        - Chart Colors
      * - isStreaming
        - Is Streaming?
        - Whether the Graph is a Streaming Graph or not
      * - markerSize
        - Marker size
      * - xCol
        - X Column
      * - xSortCol
        - Sort on X Column?
        - Whether to Sort on X column or not
      * - yCols
        - Y Columns
      * - ySortCol
        - Y Sort Column
      * - reNameYColumns
        - Rename Y Columns


Details
-------


Graph Values Details
+++++++++++++++

This node represents variation between data of various data series in Graphical format.

Multiple numeric columns can be plotted along Y-Coordinate. Only one can be selected along X-Coordinate.

Variation between dataseries is plotted as graph of the selected type such as Line-Chart, Bar-Chart or so on.

Input
```````````````

*    TITLE :- The title of a graph can be set here.
*    X LABEL :- X-axis label can be set here.
*    Y LABEL :- Y-axis label can be set here.
*    MAX VALUES TO DISPLAY :- The total number of the data points can be selected here.
*    CHART TYPE :- The desired chart can be selected from the drop-down list(Line Chart,Side By Side Bar Chart,Pie Chart,Scatter Chart)                                                 
*    CHART COLORS :- The different types of color can be selected for better visualization.
*    IS STREAMING? :- If the graph is stream graph set the option as true else false(by default it is false). 
*    X COLUMN :- Select the column for X-axis.
*    Y COLUMNS :- Select the colum for Y-axis.


Output
```````````````

*    It will plot a graph and will represent the trends between mentioned columns.
*    The different types of a graph can be plotted between specified columns to check the trends.


Types Of Chart
```````````````

*    Line Chart
*    Side By Side Bar Chart
*    Stack Bar Chart
*    Pie Chart
*    Scatter Chart
*    Dual Line Chart
*    Area Chart


Example
```````````````

*    A line chart allows us to track the development of several variables at the same time.
*    Scatter plots are used to determine whether or not two variables have a relationship or correlation.
*    The main motive of a stacked bar chart is to compare numeric values between levels of a categorical variable.


