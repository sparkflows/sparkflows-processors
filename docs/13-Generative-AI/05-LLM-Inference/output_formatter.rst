Output Formatter
===========

This node formats output from Columns.

Input
--------------
It reads data input DataFrame column

Type
--------- 

transform

Class
--------- 

fire.nodes.graph.NodeOutputFormatter

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - column
        -  Select Column
        - Select Column to format
      * - key
        - Key
        - Specify a key Name


Details
-------
Output Formatter Node Details
+++++++++++++++

The Output Formatter node formats data from a specified column in an input DataFrame and outputs it with a user-defined key. It is designed for use in PySpark-based data processing pipelines to extract and present data in a structured format, typically for downstream use or display. The node processes a single column from the input DataFrame, formats the content, and sends it as a JSON message with a specified key.



General:
+++++++++++++++


Select Column:

Specifies the column in the input DataFrame from which to extract data. This field is required and must correspond to a valid column name in the DataFrame.


Key:

Defines a key name for the formatted output. This field is required and is used to label the extracted column value in the output JSON message.



Output:
+++++++++++++++

The node does not modify the input DataFrame but instead generates a JSON-formatted message containing the following:


* id: The node’s ID.
* name: The node’s name ("Output Formatter").
* title: The display title ("Output Formatter").
* type: The node type ("formatter").
* resultType: Set to 3, indicating the output is a formatted message.
* visibility: Set to "EXPANDED" for display purposes.
* text: A nested structure containing:
* key: The user-specified key name.
* string: The value extracted from the selected column (from the first row of the DataFrame).
* format: Set to "plaintext" for the output format.


The JSON message is sent to the workflow context for further processing or display. The input DataFrame is passed through unchanged as the node’s output schema.


Examples
-------
Example: Output Formatter Node
+++++++++++++++



Input:
+++++++++++++++

A DataFrame with the following structure, containing a single row of data:


::

    | summary_text                     |
    |----------------------------------|
    | Project meeting: Plan Q1 goals...|


The Output Formatter node is configured as follows:


* Select Column: summary_text
* Key: meeting_summary


Output:
+++++++++++++++


The node processes the DataFrame and generates a JSON-formatted message sent to the workflow context, with the following structure:


```json

{

"id": "11",

"name": "Output Formatter",

"title": "Output Formatter",

"type": "formatter",

"resultType": 3,

"visibility": "EXPANDED",

"text": {

"key": "meeting_summary",

"string": "Project meeting: Plan Q1 goals...",

"format": "plaintext"

}

}

```


The input DataFrame is passed through unchanged as the node’s output schema.



Explanation:
+++++++++++++++


* The summary_text column is selected, and the value from its first row ("Project meeting: Plan Q1 goals...") is extracted.
* The key field is set to "meeting_summary", which is used to label the extracted value in the output JSON.
* The node formats the extracted value into a JSON message with a nested text object, specifying the key, string value, and format ("plaintext").
* The JSON message is sent to the workflow context for further processing or display.
* The original DataFrame is returned as the output schema without modification.
