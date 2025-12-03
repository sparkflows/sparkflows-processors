Sharepoint Data Extraction
=========== 

Retrieves files and pages from a SharePoint site, extracts their content (e.g., text from PDFs, DOCX), and outputs a DataFrame with metadata and content. Designed as the starting node in a PySpark workflow, requiring no input DataFrame.

Output
--------------
A DataFrame with columns: file_name (string), file_type (string), share_point_url (string), content (string).

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeSharepointLoader

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - sharePointConnection
        -  SharePoint Connection
        - Connection details for the SharePoint API, including tenant_id, client_id, client_secret, and sharepoint_url (e.g., https://example.sharepoint.com/sites/SparkflowsProject).
      * - performance
        - Advanced
        - 
      * - start_time
        - Start Time
        - Optional start time for filtering files/pages by lastModifiedDateTime (format: 'YYYY-MM-DD HH:MM:SS' or ISO 8601, e.g., '2025-07-03 02:05:43' or '2025-07-03T02:05:43Z'). Assumes UTC if no timezone is specified.
      * - end_time
        - End Time
        - Optional end time for filtering files/pages by lastModifiedDateTime (format: 'YYYY-MM-DD HH:MM:SS' or ISO 8601, e.g., '2025-07-04 23:59:59' or '2025-07-04T23:59:59Z'). Assumes UTC if no timezone is specified.


Details
-------
SharePoint Data Extraction Node Details
---------------


The SharePoint Data Extraction node retrieves files and pages from a SharePoint site, extracts their content (e.g., text from PDFs, DOCX, or SharePoint pages), and outputs the data as a DataFrame. The node connects to a SharePoint instance using Microsoft Graph API, fetches files and pages modified within a specified time range, and provides metadata and extracted content, making it ideal for integrating SharePoint data into data processing pipelines.


SharePoint Connection:

Specifies the connection details for the SharePoint API, including:

tenant_id: The Azure AD tenant ID for authentication.

client_id: The client ID of the registered application in Azure AD.

client_secret: The client secret for the registered application.

sharepoint_url: The URL of the SharePoint site (e.g., https://example.sharepoint.com/sites/SparkflowsProject).

These parameters are required to authenticate and access the SharePoint instance.


Start Time:

Optional timestamp to filter files and pages by their lastModifiedDateTime. Only items modified after this time are retrieved. Supported formats are:

YYYY-MM-DD HH:MM:SS (e.g., "2025-07-03 02:05:43", assumed UTC).

ISO 8601 (e.g., "2025-07-03T02:05:43Z" or "2025-07-03T02:05:43+00:00").

If not specified, the node uses the last run’s timestamp for subsequent runs (Change Data Capture) or no lower bound for the first run.


End Time:

Optional timestamp to filter files and pages by their lastModifiedDateTime. Only items modified before or at this time are retrieved. Supported formats are:

YYYY-MM-DD HH:MM:SS (e.g., "2025-07-04 23:59:59", assumed UTC).

ISO 8601 (e.g., "2025-07-04T23:59:59Z" or "2025-07-04T23:59:59+00:00").

If not specified, no upper time bound is applied.

Output:


The node outputs a DataFrame with the following columns:

file_name: The name of the file or page retrieved from SharePoint (string).

file_type: The type of the item (e.g., "pdf", "docx", "page" for SharePoint pages) (string).

share_point_url: The URL of the file or page in the SharePoint instance (string).

content: The extracted content from the file or page (e.g., text from PDFs, DOCX, or SharePoint page web parts) (string).


