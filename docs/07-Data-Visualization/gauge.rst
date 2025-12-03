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
      * - keyCol
        - Key Column
        - 
      * - valueCol
        - Value Column
        - 
      * - redfrom
        - RedFrom
        - 
      * - redTo
        - RedTo
        - 
      * - yellowfrom
        - YellowFrom
        - 
      * - yellowTo
        - YellowTo
        - 
      * - minorTicks
        - MinorTicks
        - 


Details
-------
Gauge Details
---------------


This node represents data for different categories in Gauge format.


Multiple categories can be represented using separate Gauges.


A numeric column from the incoming dataset is selected to represent the value in the Gauges.



Input
+++++++++++++++


* TITLE :- The title of a graph can be set here.
* KEY COLUMN :- Categorical column is set here.
* VALUE COLUMN :- Numerical column is set.
* REDFROM :- Minimum threshold is set for red.
* REDTO :- Maximum threshold is set for red.
* YELLOWFROM :- Minimum threshold is set for yellow.
* YELLOWTO :- Maximum threshold is set for yellow.
* MINORTICKS :- MinorTicks can be set to style the minor tick marks.


Output
+++++++++++++++

* This node is best to give a visual representation of how something is performing against a set goal.
* This node helps in identifying the problems in important data points or measures.


Examples
-------
Example:


Let's say you have a dataset with a column ServerLoad representing the current load on a server. You can configure the Gauge Chart node as follows:


Key Column: Server

Value Column: ServerLoad

Red From: 90

Red To: 100

Yellow From: 75

Yellow To: 90

Minor Ticks: 5

This will create a gauge chart for each server, showing its current load. The gauge will be colored red if the load is between 90 and 100, yellow if it's between 75 and 90, and green otherwise.
