Scatter Cluster Chart
===========

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeScatterClusterChart

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
      * - xCol
        - X Column
        - 
      * - yCol
        - Y Column
        - 
      * - clusterColumn
        - Cluster Column
        - 
      * - centroid
        - Centroid
        - 
      * - chartColors
        - Chart Colors
        - 
      * - xlabel
        - X Label
        - 
      * - ylabel
        - Y Label
        - 
      * - description
        - Description
        - 
      * - descriptionColor
        - Description Color
        - 


Details
-------
Scatter Cluster Chart Node
+++++++++++++++


Purpose:


This node creates a scatter plot with clusters, visualizing the relationship between two numerical variables and grouping similar data points together.


Configuration:


Title: Set the title for the chart.

Title Color: Set the color for the chart title.

X Column: Select the column to be used as the X-axis.

Y Column: Select the column to be used as the Y-axis.

Cluster Column: Select the column that defines the clusters.

Centroid: Enable or disable displaying the centroids of the clusters.

Chart Colors: Customize the color palette for the clusters.

X Label: Set the label for the X-axis.

Y Label: Set the label for the Y-axis.

Description: Add a description for the chart.

Description Color: Set the color for the description.

Output:


The node will generate a scatter plot with data points grouped into clusters. Each cluster will have a different color, and the centroids of the clusters can be displayed as well.


Use Cases:


Customer Segmentation: Group customers based on their behavior or demographics.

Market Segmentation: Identify different market segments based on customer preferences.

Anomaly Detection: Detect outliers that don't belong to any cluster.


Examples
-------
Example:


Let's say you have a dataset of customer information, including their age, income, and a cluster label. You can use the Scatter Cluster Chart node to visualize the clusters of customers based on their age and income.


Configuration:


X Column: Age

Y Column: Income

Cluster Column: Cluster

Output:


The scatter plot will show clusters of customers with similar age and income. The color of each cluster will represent a different customer segment.
