Hierarchy Chart
=========== 

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeHierarchyChart

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
      * - maxValuesToDisplay
        - Max Values To Display
        - Maximum number of values to display in result.
      * - chartColors
        - Chart Colors
        - 
      * - xCol
        - X Column
        - 
      * - yCols
        - Hierarchy Columns
        - 


Details
-------
Hierarchy Chart Node
---------------


Purpose:


This node creates a hierarchical chart to visualize hierarchical relationships between data points. It's useful for displaying organizational structures, family trees, or any other hierarchical data.


Configuration:


Title: Set the title for the chart.

Title Color: Set the color for the chart title.

Description: Add a description for the chart.

Description Color: Set the color for the description.

Max Values to Display: Limit the number of levels displayed in the hierarchy.

Chart Colors: Customize the color palette for the nodes and edges.

X Column: Select the column to be used as the root node.

Hierarchy Columns: Select the columns that define the hierarchical relationships between nodes.


Output:


The node will generate a hierarchical chart, where each node represents a data point, and the edges between nodes represent the hierarchical relationships. The chart can be customized with various options, such as node size, color, and shape.


Use Cases:


Organizational Charts: Visualize the structure of an organization.

Family Trees: Display family relationships.

Product Hierarchies: Show the hierarchy of products and categories.


Examples
-------
Example:


Let's say you have a dataset with information about employees and their managers. You can use the Hierarchy Chart node to visualize the organizational structure.


Configuration:


X Column: EmployeeID

Hierarchy Columns: ManagerID


Output:


The hierarchy chart will display the employees and their managers in a hierarchical structure. The root node will be the top-level manager, and the child nodes will represent their subordinates.
