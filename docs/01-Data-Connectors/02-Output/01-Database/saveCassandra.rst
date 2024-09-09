Save Cassandra
=========== 

Saves the rows of the incoming DataFrame into Apache Cassandra

Type
--------- 

transform

Class
--------- 

fire.nodes.cassandra.NodeSaveCassandra

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - connection
        - Connection
        - The Cassandra connection to connect
      * - table
        - Cassandra Table Name
        - Cassandra Table into which data gets loaded
      * - keyspace
        - Cassandra Keyspace Name
        - The keyspace where table is looked for


Details
-------


This node saves the rows of the incoming DataFrame into Apache Cassandra.


