Scatter Chart
=========== 

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeScatterChart

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
      * - chartColors
        - Chart Colors
        - 
      * - material
        - Material Chart
        - Select true will use material design
      * - dualAxis
        - Dual axis
        - Display axis on both side
      * - xCol
        - X Column
        - 
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
===============
This node creates a scatter plot to visualize the relationship between two numerical variables. Each data point is represented by a dot on the chart.


Configuration:


Max Values to Display: Limits the number of data points displayed on the chart.

Chart Colors: Customizes the color palette for the scatter plot.

Material Chart: Enables or disables Material Design for the chart.

Dual Axis: Allows for multiple Y-axes.

X Column: Selects the column to be used as the X-axis.

Y Columns: Selects the columns to be used as the Y-axis.

Output:


The node generates a scatter plot visualizing the relationship between the selected X and Y variables. The size and color of the markers can be used to represent additional information.


Use Cases:


Correlation Analysis: Identify relationships between variables.

Outlier Detection: Find data points that deviate significantly from the trend.

Clustering: Group similar data points together.


Examples
===============
Example:


Let's say you have a dataset with information about houses, including their size (in square feet) and price. You can use the Scatter Chart node to visualize the relationship between these two variables.


Configuration:


X Column: Size

Y Column: Price

Output:


The scatter plot will show the relationship between the size of a house and its price. If there's a positive correlation, larger houses will generally have higher prices.
