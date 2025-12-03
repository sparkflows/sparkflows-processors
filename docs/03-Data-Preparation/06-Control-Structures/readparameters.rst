Read Parameters
=========== 

Reads in the parameters from the given file.

Input
--------------
Input file has records in the following form on each line : name=value

Output
--------------
It adds the input parameters into the JobContext

Type
--------- 

shellcommand

Class
--------- 

fire.nodes.util.NodeReadParameters

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - path
        - Path
        - Path of the parameters file containing the parameter name and value in each line


Details
===============
Read Parameters Node
---------------


This node reads key-value pairs from a file and stores them as parameters, which can be used in subsequent nodes.


Examples
===============
Read Parameters Node Example
---------------


Given a parameter file with the following content:


PartID=A1

SupplierID=S1

PartName=Bolt

PartCategory=Hardware

PartQualityScore=8

If you configure the Read Parameters node to read this file, the parameters will be stored in the node's output and can be used in other nodes.


For example, you could use a Filter node to filter data based on the PartID parameter.
