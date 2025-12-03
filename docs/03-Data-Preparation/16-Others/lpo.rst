Linear Programming Optimisation
===========



Type
--------- 

pyspark2inputs

Class
--------- 

fire.nodes.lpo.NodeLinearProgrammingOptimisation

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - objective
        - Objective
        - Minimise or Maximise the objective function?


Details
-------
Select Weather to Maximise or minimise the objective function :

The Node takes in two dataframes as Input:

Lower edge Dataframe must have these columns :

var, value, type, relationship and bound which would help declare the Decision Variables


Higher Edge Datafrane must have these column along with all the var Decision variables which were declared in the above dataframe :

constarint,x1,x2,x3,relationship,value

These would create the constraint equations from the dataframe.


After solving the equations the Output is :

Variables Names and Values,Constraints Names and Values & Objective Value


Examples
-------
Incoming Dataframe has following rows:


::

    var           |    value     |    type        |    relationship    |    bound
    -------------------------------------------------------------------------------------
    tables        |    40        |    Integer     |    >=             |    0
    chairs        |    30        |    Integer     |    >=             |    0
    bookcases     |    35        |    Continuous  |    <=             |    0




::

    constraint | tables | chairs | bookcases | relationship | value
    -----------------------------------------------------------------
    labor      | 2      | 1      | 2.5       | <=           | 60
    machine    | 0.8    | 0.6    | 1         | <=           | 16
    wood       | 30     | 20     | 30        | <=           | 400
    tables     | 1      | 0      | 0         | >=           | 10


The above table would correspond to equations:


2 * tables + 1 * chairs + 2.5 * bookcases <= 60, "labour"

0.8 * tables + 0.6 * chairs + 1 * bookcases <= 16, "machine"

30 * tables + 20 * chairs + 30 * bookcases <= 400, "wood"

2 * tables + 0 * chairs + 0 * bookcases >= 10, "tables"



The output for the above Problem when the Objective function is Maximised is:


Variables Names and Values

bookcases = 0.0

chairs = 5.0

tables = 10.0


Constraints Names and Values

Labor = -35.0

machine = -5.0

wood = 0.0

tables = 0.0


Objective Value is : 550.0
