Dataset Structured
===========

This Node creates a DataFrame by reading data from HDFS, HIVE etc. The dataset was defined earlier in Fire by using the Dataset Feature. As a user, you just have to select the Dataset of your interest.

Input
--------------
It reads in data from HIVE or files in HDFS

Output
--------------
It creates a DataFrame from the input data and sends it to its output.

Type
--------- 

dataset

Class
--------- 

fire.nodes.dataset.NodeDatasetStructured

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - dataset
        - Dataset
        - Selected Dataset


Details
-------
This Node creates a DataFrame by reading data from HDFS, HIVE etc.


The data has been defined earlier in Fire by using the Dataset Feature. As a user, you just have to select the Dataset of your interest.


Examples
-------
Dataset Structured Node Example
+++++++++++++++


Scenario:


Let's say you have multiple datasets available in your workflow and you want to select one of them as input for the next node. You can use the Dataset Structured node to choose the desired dataset.


Configuration:


1. **Output Storage Level:** Select the desired storage level for the output DataFrame.

2. **Dataset:** Choose the dataset from the dropdown list.


Output:


The node will output the selected dataset as a DataFrame.
