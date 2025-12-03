Explode
=========== 

Explode the array of values into multiple rows with columnname_explode.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeExplode

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - inputCols
        - Input Colums
        - Select the columns to be exploded.


Details
===============
Explode Node
---------------


This node explodes a column containing arrays or maps into multiple rows, creating a new row for each element in the array or map. This is useful for flattening nested data structures.


Examples
===============
Explode Node Example
---------------


Given the following dataset:


ProductID    ProductName    Categories

P1    Laptop    ["Electronics", "Computers"]

P2    Phone    ["Electronics", "Mobile"]


If we configure the Explode Node to explode the Categories column, the output would look like this:


ProductID    ProductName    Categories

P1    Laptop    Electronics

P1    Laptop    Computers

P2    Phone    Electronics

P2    Phone    Mobile
