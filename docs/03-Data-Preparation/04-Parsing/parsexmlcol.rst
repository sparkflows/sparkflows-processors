Parse XML Col
=========== 

Parses XML content in a given column

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeParseXMLColumn

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - stringXmlColNames
        - String XML ColNames
        - Specifies the input column containing the XML data
      * - rowTags
        - Row Tags
        - In XML element that defines each record.
      * - outputStructColNames
        - Output Struct ColNames
        - uses the schema from the column you provide and create the new output column.
      * - outputSchema
        - InferSchema
        - 
      * - outputColNames
        - Output Column Name
        - Output Columns
      * - outputColTypes
        - Output Column Type
        - Data Type of the Output Columns
      * - outputColFormats
        - Output Column Format
        - Format of the Output Columns


Details
===============
Parse XML Column Node
---------------



Overview:
+++++++++++++++


The Parse XML Column node parses a XML content in a column.



Input:
+++++++++++++++


XML Column Name: The name of the column containing the XML data.

Root Tag:


Output:
+++++++++++++++


The node creates new columns for each specified XML field, with rootTag, extracting the relevant data from the XML column.


Examples
===============
Example:


XML

<books>

  <book>

    <title>Python</title>

    <author>Guido</author>

  </book>

  <book>

    <title>Scala</title>

    <author>Martin</author>

  </book>

</books>


For above example rowTag field value is books
