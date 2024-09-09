Run Python Code
=========== 

This node executes the given python code.

Type
--------- 

dataset

Class
--------- 

fire.nodes.etl.NodeRunPythonCode

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - code
        - Python
        - Python Code.


Details
-------


 Run Python Code Details
+++++++++++++++

The Run Python Code node executes the given python code.
The node takes the code provided in the "code" field as input and runs it in the PySpark engine. The code can be used to perform operations on a DataFrame, such as filtering, aggregating, and transforming data.


Examples
-------


 Run Python Code Examples
+++++++++++++++

Below are some examples of the Python code that can be run in the Run Python Code node.

 Filter data based on a condition
```````````````
def filter_data(df):
return df.filter(df['price'] > 100)

result = filter_data(df)

 Group data based on a column
```````````````
def group_data(df):
return df.groupBy(df['bedrooms']).agg({'price': 'mean'})

result = group_data(df)
