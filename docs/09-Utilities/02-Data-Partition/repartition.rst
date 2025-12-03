Repartition
===========

This node repartitions incoming dataframe into a specified number of partitions

Input
--------------
It accepts a DataFrame as input from the previous Node

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeRepartition

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - numPartitions
        - Number of Partitions
        - Number of Partitions


Details
-------
Repartition Node


Overview:


This node is used to repartition a DataFrame, which involves distributing the data across multiple partitions for improved performance and parallel processing.


Configuration:


1. Number of Partitions: Specifies the desired number of partitions.

2. Output Storage Level: Sets the storage level for the repartitioned DataFrame.


Examples
-------
Example:


If you have a DataFrame with 1000 rows and you set the number of partitions to 10, the node will distribute the data evenly across 10 partitions. This can significantly improve performance for operations like joins, aggregations, and sorting.
