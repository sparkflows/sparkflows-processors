Geo Chart
=========== 

This node maps the values on a Map

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeGraphRegionGeo

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
      * - groupByColumn1
        - Group By Column1
        - Group by Group By Column1 & Group By Column2, get a count of the rows in each group and then display the count in a graph
      * - groupByColumn2
        - Group By Column2
        - Group by Group By Column1 & Group By Column2, get a count of the rows in each group and then display the count in a graph
      * - displayMode
        - Display Mode
      * - resolution
        - Resolution
      * - region
        - Region
        - Region of the world to display


Details
-------


Geo Chart Details
+++++++++++++++


*    This node provide an easy way to visualize the data distribution across a geographic area by the help of map of country, a continent, or a region. 


Input
```````````````

*    TITLE :- The title of a graph can be set here.
*    MAX VALUES TO DISPLAY :- The total number of the data points can be selected here.
*    GROUP BY COLUMN1 :- The column can be selected from the drop-down list to perform group by. 
*    GROUP BY COLUMN2  :- The column can be selected from the drop-down list to perform group by. 
*    DISPLAY MODE :- The type of map can we selected from the drop-down list(Region or marker). 
*    RESOLUTION :- The resolution of a map can be adjusted with the help of given options. 
*    REGION :- Region can be selected here(World,US and IND).


Output
```````````````

*    The trends of data are displayed on maps depending on the display mode.
*    If the display mode is region mode then it will highlight whole regions, such as countries, provinces, or states.
*    If the display mode is markers mode then it will use circles to designate regions that are scaled according to a value that you specify.


Example
```````````````

*    The node can be used to study different aspects of the data like various of data with respect to a country, a continent or a region wise.


