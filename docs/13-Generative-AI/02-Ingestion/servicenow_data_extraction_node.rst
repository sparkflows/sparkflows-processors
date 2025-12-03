Service Now Data Extraction
===========



Input
--------------
It wont take any input, as this will be the 1st node in the workflow

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeReadFromServiceNow

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - serviceNowConnection
        - Select ServiceNow Connection
        - Select Service now Connection


Details
-------
Service Now Data Extraction Node Details
+++++++++++++++

The Service Now Data Extraction node retrieves incident data from a ServiceNow instance and outputs it as a DataFrame. It serves as the starting node in a workflow, requiring no input DataFrame, and is designed for PySpark-based pipelines. The node connects to the ServiceNow API to fetch records and extracts specific fields, making it suitable for integrating ServiceNow data into data processing workflows.



General:
+++++++++++++++



Select ServiceNow Connection: Specifies the connection details for the ServiceNow API, including the instance URL, user ID, and password. This is required to authenticate and access the ServiceNow instance.
+++++++++++++++



Output:
+++++++++++++++

The node outputs a DataFrame with the following columns:


* inc_number: The incident number from the ServiceNow record.
* state: The state of the incident (e.g., "New", "In Progress", "Closed").
* short_description: A brief description of the incident.


Examples
-------
Example: Service Now Data Extraction Node
+++++++++++++++



Input:
+++++++++++++++

No input DataFrame is required, as this is the first node in the workflow.


The Service Now Data Extraction node is configured as follows:


* Select ServiceNow Connection: Configured with a valid ServiceNow instance URL, user ID, and password


Output:
+++++++++++++++


The node queries the ServiceNow API and produces a DataFrame with the following structure:


::

    inc_number | state      | short_description
    -----------|------------|------------------------------
    INC001     | New        | Network outage reported
    INC002     | In Progress| Software installation issue
    INC003     | Closed     | Server maintenance completed



Explanation:
+++++++++++++++


* The node connects to the ServiceNow instance using the provided connection details (instance URL, user ID, and password).
* It queries the ServiceNow API to fetch incident records, limited to a default of 10 records (configurable via the node's internal parameters).
* The retrieved data is processed into a DataFrame with columns inc_number, state, and short_description, containing the incident number, state, and brief description of each incident, respectively.
* If a record lacks a specific field (e.g., short_description), it is populated with 'N/A' in the output DataFrame.
* The node does not require an input DataFrame, as it is designed to be the starting point of the workflow, directly fetching data from ServiceNow.
