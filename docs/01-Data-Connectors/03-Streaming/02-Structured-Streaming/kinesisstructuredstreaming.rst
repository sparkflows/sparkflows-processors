Structured Streaming Kinesis
=========== 

Reads in streaming text from Kinesis stream

Input
--------------
It does not take any DataFrame as input

Output
--------------
It reads events from Kinesis and creates DataFrame from the resulting rows. This DataFrame is passed to the output Nodes.

Type
--------- 

sparkstreaming

Class
--------- 

fire.nodes.structuredstreaming.NodeStructuredStreamingKinesis

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - streamName
        - Stream Name
        - Kinesis Stream Name
      * - endpointUrl
        - Endpoint Url
        - Kinesis Endpoint Url
      * - awsAccessKeyId
        - AwsAccessKeyId
        - 
      * - awsSecretKey
        - AwsSecretKey
        - 
      * - startingPosition
        - StartingPosition
        - Starting Position in Kinesis to fetch data from. Possible values are latest, trim_horizon, earliest




