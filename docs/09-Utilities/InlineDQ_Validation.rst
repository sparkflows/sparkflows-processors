InlineDQ_Validation
===========

Node to perform InlineDQ validation and generate pass/fail result

Type
--------- 

transform

Class
--------- 

fire.nodes.ge.InlineDQ_Validation

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - env
        - Environment
        - Environment ex. development, qa, preprod, production
      * - input_data_path
        - Input Data Path
        - S3 location of input data. Either folder or a single file
      * - output_data_path
        - Output Data Path
        - S3 location of great expectation output
      * - dq_config_path
        - DQ Config Path
        - S3 location of DQ Config YAML file for a specific file type which we are processing
      * - report-parameters
        - Report Parameters
        - 
      * - report_type
        - Report Type
        - Report Type ex. file-level, detail
      * - report_version
        - Report Version
        - Report Version ex. 1.0.0, 1.0.1
      * - report_format
        - Report Format
        - Report Format ex. json, csv
      * - report_location
        - Report Location
        - S3 location of pass/fail report
      * - report_email_list
        - Report Email Recipients
        - Comma separated email list to whom the validation report needs to be sent
      * - readonly-parameters
        - Read-Only Parameters
        - 
      * - year
        - Year
        - Current Year
      * - month
        - Month
        - Current Month
      * - day
        - Day
        - Current Day
      * - hour
        - Hour
        - Current Hour
      * - log_level
        - Log Level
        - Logging level
      * - correlation_id
        - Correlation Id
        - 
      * - parent_activity_id
        - Activity Id
        - 




