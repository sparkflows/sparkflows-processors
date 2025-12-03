Data Wrangling
===========

This node creates a new DataFrame by applying each of the Rules specified

Input
--------------
It takes in a DataFrame as Input

Output
--------------
It creates the output DataFrame by applying the data wrangling rules provided

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeDataWrangling

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - rules
        - Rules
        - Rules to be applied on column and rows


Details
-------
Rename one column to another

rename col:c1 to c2;


Drop Column

drop col:col4


Delete columns with some condition

delete col:col3 > 44


Substring col:col2 0,3

get substring between 0 and 3rd column from the column col2


Trim Values : Removes leading and trailing whitespace from a string value. 


set col:Name value: trim(Name)


Sets the new value of Name column to be trim(Name)


Examples
-------
Example:
+++++++++++++++


Let's assume we have a DataFrame with the following columns: id, column1, column2, column3, column4, column5, column6, column7, column8.


We want to:


Rename column1 to col2.

Drop columns column1 and column2.

Delete rows where column3 is greater than 100.

Delete rows older than 90 days.

Convert the values in column4 to uppercase.

Convert the values in column5 to lowercase.

Derive a new column avgScore by calculating the average of column6 and column7.

Derive a new column zipCodeSubstring by extracting the last 3 characters from the column8.

Configuration:


rename col:cl to c2;

drop col:cl,c2;

delete row:(column3 > 100);

delete row:(dateAge > 90);

set col:c4 value:UPPER(c4);

set col:c5 value:LOWER(c5);

derive value: AVERAGE(Score) avgScore;

derive value: SUBSTRING(ZipCode,3,5)

Node Execution:


The node will apply the specified rules to the DataFrame, resulting in a transformed DataFrame with the desired modifications.
