Execute Workflow
=========== 

Fires the given workflow. Does not wait for the workflow to complete to resume execution

Type
--------- 

transform

Class
--------- 

fire.nodes.util.NodeExecuteWorkflow

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - workflowUuid
        - Workflow
        - The workflow to execute
      * - isEnabled
        - IsEnabled
        - isEnabled true execute the selected workflow.
      * - parameterName
        - Parameter Name
        - parameters name.
      * - parameterValue
        - Parameter Value
        - parameters value.


Details
-------


Execute Workflow Node Details
+++++++++++++++

The `Execute Workflow` node allows a workflow to call and execute another workflow. This enables creating a DAG of workflows where you can pass, if required, additional parameters to the called workflow .

Input Parameters
```````````````

*  OUTPUT STORAGE LEVEL : Keep this as DEFAULT.
*  WORKFLOW : Select the workflow to be called/executed.
*  isEnabled : If set to be `true` it will execute the specified workflow.
*  KEY VALUE ARRAY : OPTIONAL, Used to pass values to the specified workflow from the current workflow. 

- Parameter Name : An unique name to identify the parameter that is being passed. 
- Parameter Value : A value that is assigned to a parameter name, can be of numeric or string type. 


Examples
-------


Execute Workflow Node Example
+++++++++++++++

An example for `Execute Workflow` can be found at the below page:

https://docs.sparkflows.io/en/latest/user-guide/pipeline-development/execute-workflow.html#create-workflow
