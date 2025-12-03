Apache Logs
=========== 

Reads in Apache Log files from a given path, parses them and loads them into a DataFrame

Type
--------- 

dataset

Class
--------- 

fire.nodes.logs.NodeApacheFileAccessLog

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
        - Full path for the directory or file for the Apache File Logs


Details
-------
The Apache Log Parser node provides the following functionality:


 * Reads in Apache log files from a specified path

 * Parses the log data into relevant columns

 * Loads the parsed data into a pandas DataFrame


Examples
-------
Input
+++++++++++++++


The input for the Apache Log Parser is a file path to the Apache log file. This can be provided through a user interface, such as a browse-to-file-path widget.



Output
+++++++++++++++


The output of the Apache Log Parser is a pandas DataFrame containing the parsed log data. The DataFrame schema includes the following columns:


 * clientIdentd: client identification

 * contentSize: content size

 * endpoint: endpoint URL

 * ipAddress: IP address

 * method: request method (e.g., GET, POST, etc.)

 * protocol: protocol used (e.g., HTTP/1.1, etc.)

 * responseCode: response code

 * ts: timestamp

 * userID: user ID (if available)
