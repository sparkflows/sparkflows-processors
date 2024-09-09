Graph Subplots
=========== 

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeGraphSubPlots

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
      * - maxValuesToDisplay
        - Max Values To Display
        - Maximum number of values to display in result.
      * - chartColors
        - Chart Colors
      * - xCols
        - X-Column
        - X axis Column
      * - yCols
        - Y-Column
        - Y axis Column
      * - graphTypes
        - GraphTypes
        - Graph Types
      * - xLabels
        - X Label
        - X axis Label
      * - yLabels
        - Y Label
        - Y axis Label
      * - chartTitle
        - Chart Title
      * - sortByYCol
        - Sort by Y-Column


Details
-------


Graph Subplots Details
+++++++++++++++

Subplots let you place several plots beside each other on a grid, Subplots are helpful when you want to show different data presentation in a single view, for instance Dashboards.

Each Graph can be configured separately in terms of data columns and GraphTypes.

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  TITLE : The title of a graph can be set here.
*  MAX VALUES TO DISPLAY : The total number of data points to be selected in the graph output.
*  CHART COLORS : Select the color palette to be used for data visualization.
*  VARIABLES: Define the individual plots that are to be created
*     X-Columns : Select the column to be used on the horizontal axis.
*     Y-Columns : Select the column to be used for the vertical axis.
*     GraphTypes : Select the type of graph to be used for data visualization.
*     X Labels : Enter the description of the horizontal axis.
*     Y Labels : Enter the description of the vertical axis.


 List of GraphTypes:
```````````````

*    Bar Chart
*    Column Chart
*    Dual Line Chart
*    Line Chart
*    Pie Chart
*    Scatter Chart


 When to use SubPlots
```````````````

*    This node is useful for displaying dense information in data visualization. Subplots fit multiple plots on the same figure.
*    This is good for comparison: aligning comparable attributes, and columns side by side for convenient visualization.
*    It gives us a sense of how comparable data attributes vary, sometimes with the same horizontal axis and scale.


