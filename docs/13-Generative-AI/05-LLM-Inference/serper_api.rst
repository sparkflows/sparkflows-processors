SerperAI Search
=========== 

The SerperAI Search node fetches real-time search results from Google services (Web, News, Images, Shopping, Places) using the SerperAI API. It processes user queries and returns results as a structured DataFrame or raw JSON, ideal for retrieval-augmented generation (RAG) workflows.

Input
--------------
No input DataFrame required

Output
--------------
Returns search results as a DataFrame

Type
--------- 

pyspark

Class
--------- 

fire.nodes.gai.NodeSerperAISearch

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - serperConnection
        - Select Connection
        - The serper api connection to connect
      * - query
        - Query
        - Search query to send to the SerperAI API (e.g., 'latest AI tools').
      * - userQueryCol
        - User Query Column
        - Column name for user query, (if the query is in a column)
      * - Advanced
        - Advanced
        - 
      * - search_type
        - Search Type
        - Type of search to perform: web, news, images, shopping, places, youtube, scholar, patents, autocomplete, etc.
      * - num_results
        - Number of Results
        - Number of search results to fetch (default: 10).
      * - country
        - Country Code (gl)
        - Two-letter country code (e.g., 'us' for United States, 'in' for India). Used to localize results.
      * - language
        - Language Code (hl)
        - Two-letter language code (e.g., 'en' for English, 'fr' for French). Used to return results in a specific language.
      * - date_range
        - Date Range Filter
        - Restrict search results to a specific time range.
      * - additional_params
        - Additional Parameters
        - Optional JSON object for advanced search parameters (e.g., {"gl": "us", "hl": "en"}).
      * - output_format
        - Output Format
        - Output format: Parsed DataFrame (structured columns) or Raw JSON (full response).


Details
===============
SerperAI Search Node Details
---------------

The SerperAI Search node fetches real-time search results from Google services (Web, News, Images, Shopping, Places) using the SerperAI API. It processes user queries and returns results as a structured DataFrame or raw JSON, ideal for retrieval-augmented generation (RAG) workflows.



General:
+++++++++++++++



API Key:
+++++++++++++++

Specifies the SerperAI API key obtained from serper.ai. This field is required to authenticate requests to the SerperAI API.



Query:
+++++++++++++++

Defines the search query to send to the SerperAI API (e.g., 'latest AI tools'). This is required unless a *User Query Column* is specified.



User Query Column:
+++++++++++++++

Specifies a DataFrame column containing search queries. This is optional and used when queries are stored in an input DataFrame column instead of the *Query* field.



Search Type:
+++++++++++++++

Selects the type of search to perform. Options include:


* search: Standard web search results.
* news: News articles related to the query.
* images: Image search results.
* shopping: Product listings from shopping searches.
* places: Local business or place information.
* autocomplete: Search query suggestions.
* webpage: Webpage-specific search results (treated as standard search).

If not specified, defaults to *search*.



Number of Results:
+++++++++++++++

Sets the number of search results to fetch. Default is 10. Must be a positive integer.



Country Code (gl):
+++++++++++++++

Specifies a two-letter country code (e.g., 'us' for United States, 'in' for India) to localize search results. Optional.



Language Code (hl):
+++++++++++++++

Specifies a two-letter language code (e.g., 'en' for English, 'fr' for French) to return results in a specific language. Optional.



Date Range Filter:
+++++++++++++++

Restricts search results to a specific time range. Options are:


* Any Time: No time restriction (default).
* Past Hour: Results from the last hour.
* Past 24 Hours: Results from the last day.
* Past Week: Results from the last week.
* Past Month: Results from the last month.
* Past Year: Results from the last year.


Additional Parameters:
+++++++++++++++


Allows advanced search parameters as a JSON object (e.g., {"gl": "us", "hl": "en"}). Optional and overrides *Country Code* and *Language Code* if provided.



Output Format:
+++++++++++++++

Determines the output format of the search results. Options are:


* Parsed DataFrame: Structured columns specific to the search type (e.g., title, link, snippet for web search).
* Raw JSON: Full API response as a JSON string.

Defaults to *Parsed DataFrame*.



Input:
+++++++++++++++

No input DataFrame is required unless *User Query Column* is used, in which case an input DataFrame with the specified query column is needed.



Output:
+++++++++++++++

The node outputs a DataFrame with columns depending on the *Search Type* and *Output Format*:


* For *Parsed DataFrame*:
* Web search: title, link, snippet, query.
* News: title, link, source, date, query.
* Images: title, imageUrl, source, query.
* Shopping: title, link, price, query.
* Places: title, address, rating (float), query.
* Autocomplete: suggestion, query.
* For *Raw JSON*: search_results (JSON string), query.


Examples
===============
Example: SerperAI Search Node
---------------



Input:
+++++++++++++++

The SerperAI Search node is configured as follows:


* API Key: abc123xyz (valid SerperAI API key).
* Query: "latest AI tools 2025".
* User Query Column: Empty (uses *Query* field).
* Search Type: search (web search).
* Number of Results: 5.
* Country Code (gl): us.
* Language Code (hl): en.
* Date Range Filter: Past Month.
* Additional Parameters: {} (empty).
* Output Format: Parsed DataFrame.


No input DataFrame is provided since *User Query Column* is empty.



Output:
+++++++++++++++

The node processes the query and produces a DataFrame with the following structure:


::

    title                          | link                                      | snippet                                   | query
    -------------------------------|-------------------------------------------|-------------------------------------------|--------------------
    Top AI Tools for 2025          | https://example.com/ai-tools-2025         | Best AI tools for productivity...         | latest AI tools 2025
    AI Innovations in 2025         | https://techsite.com/ai-2025              | Discover the latest AI advancements...    | latest AI tools 2025
    2025 AI Software Guide         | https://reviews.com/ai-guide              | Comprehensive guide to AI tools...       | latest AI tools 2025
    New AI Tools Released          | https://news.com/ai-releases             | Latest AI tool announcements...          | latest AI tools 2025
    AI Trends for 2025             | https://insights.com/ai-trends           | Emerging AI technologies for 2025...     | latest AI tools 2025



Explanation:
+++++++++++++++


* The node sends the query "latest AI tools 2025" to the SerperAI API with the *search* type, requesting 5 results.
* The *Country Code (gl)* is set to 'us' and *Language Code (hl)* to 'en', localizing results to the United States in English.
* The *Date Range Filter* is set to *Past Month*, restricting results to content from the last 30 days.
* Since *Output Format* is *Parsed DataFrame*, the results are structured into columns: *title*, *link*, *snippet*, and *query*.
* Each row corresponds to a search result, with the *query* column reflecting the input query.
* If *Output Format* were *Raw JSON*, the output would include a *search_results* column with the full JSON response and a *query* column.
* The API key authenticates the request, and no input DataFrame is needed since *User Query Column* is empty.
