Append Fields
=========== 

Append fields from a Source DataFrame to every row of a Target DataFrame (Cartesian-style append).

Type
--------- 

join2inputs

Class
--------- 

fire.nodes.etl.NodeAppendFields

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - selectSourceFields
        - Select Source Fields
        - selectSourceFields
      * - dataTypeSourceFields
        - Data Type Source Fields
        - New data type(INTEGER, DOUBLE, STRING, LONG, SHORT)
      * - renameSourceFields
        - Rename Source Fields
        - rename column
      * - selectTargetFields
        - Select Target Fields
        - Columns
      * - dataTypeTargetFields
        - Data Type Target Fields
        - New data type(INTEGER, DOUBLE, STRING, LONG, SHORT)
      * - renameTargetFields
        - Rename Target Fields
        - rename column
      * - options
        - Options
        - 
      * - prefix
        - Prefix
        - Optional prefix to add to appended column names.
      * - suffix
        - Suffix
        - Optional suffix to add to appended column names.
      * - enforceThresholdMode
        - Threshold Behavior
        - Behavior when Source row count exceeds threshold: none / warn / error (default: warn).
      * - multiRowSourceBehavior
        - Join Type
        - 
      * - drop
        - Drop
        - 
      * - inputPropagateSchema
        - Propagate Input Schema
        - propagate input schema
      * - dropSourceFields
        - Drop Source Fields
        - Drop Source Fields
      * - dropTargetFields
        - Drop Target Fields
        - Drop Target Fields
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Output Column Names
        - Name of the Output Columns
      * - outputColTypes
        - Output Column Types
        - Data Type of the Output Columns
      * - outputColFormats
        - Output Column Formats
        - Format of the Output Columns




