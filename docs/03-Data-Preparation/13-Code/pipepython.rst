Pipe Python
=========== 

This node runs any given Python code. It pipes the incoming DataFrame through pipe to the Python Script. Output back to Spark has to be written out using print.

Input
--------------
It pipes the incoming DataFrame through pipe to the Python Script. It also passes the Schema of the DataFrame to the Python script through the command line argument - argv[1]

Output
--------------
Output back to Spark has to be written out using print.

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodePipePython

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - code
        - Pipe Python
        - Python code to be run. It receives each record as a string and outputs records back as a string.
      * - outputColNames
        - Output Column Names
        - Output Schema of Pipe Python Processor
      * - outputColTypes
        - Output Column Types
        - Data Type of the Output Columns
      * - outputColFormats
        - Output Column Formats
        - Format of the Output Columns


Details
-------


Pipe Python Details
+++++++++++++++

The Pipe Python node receives an incoming DataFrame. It pipes the DataFrame through to a Python script that runs the given Python code. The script can operate on each row of the DataFrame and returns an updated row.

The input to the script is passed as a string and the output from the script is also passed as a string. The input schema of the DataFrame is also passed to the Python script through the command line argument - argv[1].

The output from the Python script has to be written back to Spark using print. The node then creates an updated DataFrame based on the output from the script and passes it on to the next node in the pipeline.


Examples
-------


Pipe Python Examples
+++++++++++++++

Below are some examples of the Python code that can be run in the Pipe Python node.

The schema of the Input DataFrame is : id, price, lotsize, bedrooms, bathrms, stories, driveway, recroom, fullbase, gashw, airco, garagepl, prefarea

 Update the value of price
```````````````
def update_price(record):
  record['price'] = int(record['price']) + 1000
  return record

print(update_price(record))
