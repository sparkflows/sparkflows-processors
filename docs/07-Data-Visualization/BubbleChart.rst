Bubble Chart
=========== 

A bubble chart is used to visualize a data set with two to four dimensions

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeBubbleChart

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
      * - maxValuesToDisplay
        - Max Values To Display
        - Maximum number of values to display in result.
      * - isStreaming
        - Is Streaming?
        - Whether the Graph is a Streaming Graph or not
      * - chartColors
        - Chart Colors
        - 
      * - bubbles
        - Bubbles label
        - Name of the bubble
      * - xCoordinate
        - X coordinate
        - X coordinate
      * - yCoordinate
        - Y coordinate
        - Y coordinate
      * - color
        - Bubbles color
        - Representing a color of bubble
      * - size
        - Bubbles size
        - Representing size of bubble
      * - xlabel
        - X Label
        - 
      * - ylabel
        - Y Label
        - 


Details
===============
Bubble Chart Details
---------------


Purpose:


This node creates a bubble chart to visualize data with two to four dimensions. Each data point is represented by a bubble, where the size and color of the bubble can be used to represent additional dimensions.


Configuration:


Title: Set the title for the chart.

Title Color: Set the color for the chart title.

Description: Add a description for the chart.

Description Color: Set the color for the description.

Max Values to Display: Limit the number of data points displayed on the chart.

Is Streaming: Enable or disable streaming updates to the chart.

Chart Colors: Customize the color palette for the bubbles.

Bubbles Label: Specify the column to use for labeling the bubbles.

X Coordinate: Sets the column to use for the X-axis.

Y Coordinate: Sets the column to use for the Y-axis.

Bubbles Color: Sets the column to use for coloring the bubbles.

Bubbles Size: Sets the column to use for sizing the bubbles.

Output:


The node will generate a bubble chart visualizing the data points. The size and color of the bubbles can be used to represent additional dimensions, making it easy to identify patterns and trends.


Use Cases:


Financial Analysis: Visualize stock performance over time, with bubble size representing market capitalization and color representing industry.

Sales Analysis: Compare sales figures for different products or regions, with bubble size representing sales volume and color representing profit margin.

Geographic Analysis: Map geographic data, with bubble size representing population density and color representing different regions.


Examples
===============
Example:


Let's say you have a dataset with information about different cities, including their population, GDP, and geographical location. You can use the Bubble Chart node to visualize this data on a world map.


Configuration:


X Coordinate: Longitude

Y Coordinate: Latitude

Bubbles Size: Population

Bubbles Color: GDP

Output:


The bubble chart will display a world map with bubbles representing different cities. The size of each bubble will represent the population of the city, and the color will represent the GDP.
