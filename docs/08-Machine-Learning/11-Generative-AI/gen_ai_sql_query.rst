Natural Language Query
=========== 

Query database with natural language.

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeGenAiSqlQuery

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - jdbcConnection
        - Connection
        - The JDBC connection to connect
      * - query
        - Query
        - Query from database
      * - top_k
        - Top_K
        - Number of results to return from the query
      * - return_sql
        - Return SQL
        - Will return sql-command directly without executing it
      * - include_tables
        - Include Tables
        - Include Tables from database. e.g.: housing, diabetes, ..
      * - advanced
        - LLM Connection
      * - llmConnection
        - Connection
        - The LLM connection to connect
      * - temperature
        - Temperature
        - What sampling temperature to use.
      * - model
        - Model
        - Model name to use.
      * - max_tokens
        - Max Tokens
        - Maximum number of tokens to generate.
      * - max_retries
        - Max Retries
        - Maximum number of retries to make when generating.
      * - n
        - N
        - Number of chat completions to generate for each prompt.
      * - streaming
        - streaming
        - Whether to stream the results or not
      * - OpenAI_organization
        - OpenAI Organization
        - OpenAI Organization
      * - OpenAI_proxy
        - OpenAI Proxy
        - OpenAI Proxy
      * - tiktoken_model_name
        - Tiktoken Model Name
        - The model name to pass to tiktoken




