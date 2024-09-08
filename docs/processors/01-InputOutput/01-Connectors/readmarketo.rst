Read Marketo
=========== 

This node reads data from Marketo files

Type
--------- 

dataset

Class
--------- 

fire.nodes.marketo.NodeReadMarketo

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - clientId
        - Client Id
        - Marketo account clientId
      * - clientSecret
        - Client Secret
        - Marketo account clientSecret
      * - instanceUrl
        - Instance Url
        - Instance URL to be used to access Marketo. It has to be specified without /rest. i.e it should be like https://119-AAA-888.mktorest.com
      * - object
        - Object
        - Object to be queried from Marketo. ex. leads
      * - filterType
        - Filter Type
        - Filter field to be used
      * - filterValues
        - Filter Values
        - Comma separated filter values to be applied
      * - fromDate
        - From Date
        - (Optional) Datatime from which the data has to be fetched. It has to be in ISO 8601 format
      * - customObject
        - Custom Object
        - (Optional) Boolean to specify if the specified object is custom object, Default value is false
      * - apiVersion
        - Api Version
        - (Optional) API Version to be used. Default value is v1
      * - modifiedFields
        - Modified Fields
        - (Optional) Fields to be considered for leadChanges. It has to be comma separated field names
      * - queryType
        - Query Type
        - Query Type of Marketo
      * - outputColNames
        - Column Names for the Marketo
        - New Output Columns of the SQL
      * - outputColTypes
        - Column Types for the Marketo
        - Data Type of the Output Columns
      * - outputColFormats
        - Column Formats for the Marketo
        - Format of the Output Columns


Details
-------


This node reads data from Marketo files.


