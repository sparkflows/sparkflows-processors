Transpose Advanced
=========== 

Transpose Node

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeTransposeColumns

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - transpose
        - Transpose
        - 
      * - keyCols
        - Key Columns
        - Columns to keep fixed (identifiers)
      * - dataCols
        - Data Columns
        - Columns to unpivot (convert to rows)
      * - inputColumnPropagation
        - Select all fields as Data Columns
        - When enabled, automatically include all unspecified input columns as data cols leaving selected key cols.
      * - schema
        - InferSchema
        - 
      * - outputColNames
        - Column Names of the Table
        - Output Columns Names of the Table
      * - outputColTypes
        - Column Types of the Table
        - Output Column Types of the Table
      * - outputColFormats
        - Column Formats
        - Output Column Formats


Details
===============
This node creates a DataFrame by transposing (unpivoting) the incoming DataFrame.


It converts selected data columns into rows, preserving key columns, and creates new columns for the original column names (`Name`) and their corresponding values (`Value`).


When **Input Column Propagation** is enabled (`inputColumnPropagation = True`), the node automatically treats **all non-key columns** as data columns.

This means any new or unknown columns appearing in the input will also be included in the transpose operation without requiring reconfiguration.


Examples
===============
### Example 1: Standard Transpose



* *Incoming DataFrame:**

::

    DEPT         |    NEW JERSEY       |    NEW YORK
    ---------------------------------------------------
    FRONT DESK   |    1                |    1
    MARKETING    |    1                |    1
    HR           |    0                |    1
    SALES        |    1                |    0
    MAINTENANCE  |    1                |    1


* *Configuration:**


KEY COLUMNS      :    DEPT

DATA COLUMNS     :    NEW JERSEY, NEW YORK

INPUT COLUMN PROPAGATION :    False



* *Output DataFrame:**

::

    DEPT         |    Name             |    Value
    ---------------------------------------------------
    FRONT DESK   |    NEW JERSEY       |    1
    FRONT DESK   |    NEW YORK         |    1
    MARKETING    |    NEW JERSEY       |    1
    MARKETING    |    NEW YORK         |    1
    HR           |    NEW JERSEY       |    0
    HR           |    NEW YORK         |    1
    SALES        |    NEW JERSEY       |    1
    SALES        |    NEW YORK         |    0
    MAINTENANCE  |    NEW JERSEY       |    1
    MAINTENANCE  |    NEW YORK         |    1



::

    ---



### Example 2: With Input Column Propagation Enabled



* *Incoming DataFrame:**

::

    DEPT         |    NEW JERSEY   |    NEW YORK   |    CALIFORNIA   |    TEXAS
    ---------------------------------------------------------------------------
    FRONT DESK   |    1            |    1          |    0            |    1
    MARKETING    |    1            |    1          |    1            |    1
    HR           |    0            |    1          |    0            |    1
    SALES        |    1            |    0          |    1            |    0


* *Configuration:**


KEY COLUMNS      :    DEPT

DATA COLUMNS     :    (not explicitly selected — auto-inferred)

INPUT COLUMN PROPAGATION :    True



* *Explanation:**

Since propagation is enabled, all non-key columns (`NEW JERSEY`, `NEW YORK`, `CALIFORNIA`, `TEXAS`)

are automatically considered for transposition.



* *Output DataFrame:**

::

    DEPT         |    Name           |    Value
    --------------------------------------------
    FRONT DESK   |    NEW JERSEY     |    1
    FRONT DESK   |    NEW YORK       |    1
    FRONT DESK   |    CALIFORNIA     |    0
    FRONT DESK   |    TEXAS          |    1
    MARKETING    |    NEW JERSEY     |    1
    MARKETING    |    NEW YORK       |    1
    MARKETING    |    CALIFORNIA     |    1
    MARKETING    |    TEXAS          |    1
    HR           |    NEW JERSEY     |    0
    HR           |    NEW YORK       |    1
    HR           |    CALIFORNIA     |    0
    HR           |    TEXAS          |    1
    SALES        |    NEW JERSEY     |    1
    SALES        |    NEW YORK       |    0
    SALES        |    CALIFORNIA     |    1
    SALES        |    TEXAS          |    0


* *Result:**

The node automatically includes all new fields without requiring updates to the configuration.
