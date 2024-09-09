Gauge Chart
=========== 

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeGauge

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
      * - keyCol
        - Key Column
      * - valueCol
        - Value Column
      * - redfrom
        - RedFrom
      * - redTo
        - RedTo
      * - yellowfrom
        - YellowFrom
      * - yellowTo
        - YellowTo
      * - minorTicks
        - MinorTicks


Details
-------


Gauge Details
+++++++++++++++

This node represents data for different categories in Gauge format.

Multiple categories can be represented using separate Gauges.

A numeric column from the incoming dataset is selected to represent the value in the Gauges.

Input
```````````````

*    TITLE :- The title of a graph can be set here.
*    KEY COLUMN :- Categorical column is set here.
*    VALUE COLUMN :- Numerical column is set.
*    REDFROM :- Minimum threshold is set for red.
*    REDTO :- Maximum threshold is set for red.
*    YELLOWFROM :- Minimum threshold is set for yellow.
*    YELLOWTO :- Maximum threshold is set for yellow.
*    MINORTICKS :- MinorTicks can be set to style the minor tick marks.


Output
```````````````

*    This node is best to give a visual representation of how something is performing against a set goal.
*    This node helps in identifying the problems in important data points or measures.


