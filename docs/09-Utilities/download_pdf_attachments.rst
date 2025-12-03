Pdf Attachments from Emails
===========

This node reads emails and download Pdf Attachments from all provided email addresses

Type
--------- 

pyspark

Class
--------- 

fire.nodes.util.NodeDownloadMailAttachments

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - subjectFilter
        - Filter By Subject
        - Filter emails with attachments based on the subject.(Optional)
      * - attachmentsDir
        - Save Attachments To Path
        - Directory path to save the downloaded attachments.
      * - top
        - Top
        - Number of most recent Emails to Fetch
      * - emailAddressList
        - Email Address List
        - List of email addresses separated by commas or semicolon. Attachments will be fetched from these emails.
      * - Microsoft
        - Microsoft Graph API Configuration
        - Configuration for Microsoft Graph API.
      * - clientId
        - Client Id
        - Client ID for Microsoft authentication.
      * - clientSecret
        - Client Secret
        - Client secret for Microsoft authentication.
      * - tenantId
        - Tenant Id
        - Tenant ID for Microsoft authentication.


Details
-------
Pdf Attachments From Email Node Details
+++++++++++++++


This node reads emails from specified email addresses and downloads PDF attachments. It filters emails based on a subject filter and saves the attachments in the provided directory. The node uses Microsoft Graph API for authentication and email access.



Parameters to be set:
+++++++++++++++


### General:



* Subject Filter: Filter emails based on their subject. Only emails containing the specified text in the subject will be processed.

* Attachments Directory: Specify the directory path where attachments will be saved.

* Top : Specify the number of most recent emails to look for attachments.

* Email Address List: Provide a list of email addresses separated by commas. Attachments will be fetched from these email accounts.


### Microsoft App Configuration:



* Client ID: Enter the Client ID for the Microsoft application used for authentication.

* Client Secret: Provide the Client Secret for the Microsoft application.

* Tenant ID: Specify the Tenant ID associated with the Microsoft application.


