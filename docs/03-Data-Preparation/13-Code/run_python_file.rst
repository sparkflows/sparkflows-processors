Run Python File
===========

This node executes the given python file.

Type
--------- 

dataset

Class
--------- 

fire.nodes.etl.NodeRunPythonFile

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
        - path of the python file.


Details
-------
Run Python File Node
+++++++++++++++


This node executes a specified Python script, allowing you to incorporate custom Python code into your data processing workflow.


Examples
-------
Run Python File Node Example
+++++++++++++++


Scenario:


Let's say you want to perform a custom data transformation that isn't available as a built-in node. You can write a Python script to implement the desired transformation and then use the Run Python File node to execute it.


Usage:


Place the Run Python File node: Position the node in your workflow where you want to execute the Python script.

Set the Python file path: Configure the node with the path to your Python script.

Run the workflow: When the workflow reaches the Run Python File node, the specified Python script will be executed.
