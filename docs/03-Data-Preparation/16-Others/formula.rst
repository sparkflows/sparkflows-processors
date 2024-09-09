Formula
=========== 

test

Input
--------------
It accepts a DataFrame as input from the previous Node

Output
--------------
The incoming DataFrame is sent to the output

Type
--------- 

transform

Class
--------- 

fire.nodes.etl.NodeFormula

Fields
--------- 

.. list-table::
      :widths: 10 5 10
      :header-rows: 1

      * - Name
        - Title
        - Description
      * - outputCol
        - Output Column
        - 
      * - functionsArray
        - Functions
        - 
      * - formula
        - Formula
        - 


Details
-------


Formula Node Details
+++++++++++++++

This node allows the user to use functions to build expressions that perform a variety of calculations and operations.


Examples
-------


 conditional
+++++++++++++++
Node configrations:
outputCol -> Result
functionsArray -> Conditional
formula :
CASE WHEN cat_col = 1 THEN "Gold" WHEN cat_col = 2 THEN "Silver" ELSE "Other" END

Input Dataframe :
+-------+
|cat_col|
+-------+
|      1|
|      2|
|      1|
|      3|
+-------+

Output Dataframe:
+-------+------+
|cat_col|Result|
+-------+------+
|      1|  Gold|
|      2|Silver|
|      1|  Gold|
|      3| Other|
+-------+------+

Here are a few more examples for Conditional statements:
Eg: IF(Class == 1, "Gold", "Other")
Eg: IF(CUSTOMER, "Send flyer", "Send documentation")
Apart from these you can also write any spark SQL expression, and this will get evaluated in the configured outputCol.

Conversion
+++++++++++++++

Examples:
binary_string   integer_value   char_value   integer_value_2   BinToInt   CharFromInt   CharToInt   HexToNumber   IntToBin   IntToHex
--------------  --------------  -----------  ----------------  ---------  ------------  ----------  ------------  ---------  --------
0  101010101       341             🏈           66                341        B             127         66            101010101  155

BinToInt(s): Converts the binary string s to an integer.
Example:
BinToInt(binary_string) results in 341.

CharFromInt(x): Returns the Unicode® character that matches the input number x.
Example
CharFromInt(integer_value_2) returns B (U+0042 'Latin Capital Letter B').

CharToInt(s): Returns the number that matches the input Unicode® character s.
Example
CharToInt(CharFromInt) returns 66 (U+0042 'Latin Capital Letter B').

HexToNumber(x): Converts a HEX string to a number (Limited to 53 bits).
Example
HexToNumber(dd) converts to the number 221.

IntToBin(x): Converts x to a binary string.

IntToHex(x): Converts x to a hexadecimal string.

String
+++++++++++++++

Contains(String, Target, CaseInsensitive=1): Searches for the occurrence of a particular string within a string. Returns True if (String) contains (Target), else returns False.
Example
Contains('123ABC', 'ABC') returns True.
Contains('input_col', 'abc') returns True/ False depending upon the column value.
CountWords(string): Returns the count of words in the specified string. Words are defined by characters separated by a space.
Example
CountWords("Basic Variables Households") returns 3.
CountWords(input_col) returns count of number of words based on input column values.

EndsWith(String, Target, CaseInsensitive=1): Checks if a string ends with a particular string. Returns True if (String) ends with (Target), else returns False. It defaults to case insensitive.
Example
EndsWith('123ABC', 'ABC',1) returns True.
EndsWith('123ABC', 'abc', 0) returns False.
EndsWith(input_col, 'abc',1) returns True/False depending upon the column values.

FindString(String,Target): Searches for the occurrence of a particular string (Target) within another string (String) and returns the numeric position of its occurrence in the string.
Returns the 0-based index of the first occurrence of (Target) in (String). Returns -1 if no occurrence. The FindString function is case sensitive.
Example
FindString(input_col, "John") returns 0 when the string starts with John and returns -1 when the string does not.

GetWord(string, n): Returns the Nth (0-based) word in the string (0-based index means the first word is at the 0 position, the second is at the 1 position, and so on). Words are defined as a collection of characters separated by a space, tab, return, or newline character. Multiple delimiters in a row are treated as a single delimiter.
Example
GetWord("Basic Variables Households", 0) returns "Basic".
GetWord(input_col, 1) returns corresponding words from column values.

Left(String, len): Returns the first (len) characters of the string (String). If len is less than 0 or greater than the length of String, String remains unchanged.
Example
Left("92688", 3) returns a value of "926".
Left(input_col, 3) returns a value of "926".

Length(String): Returns the length of the string (String).
Example
Length("92688") returns a value of 5.
Length results might differ between this Designer function and SQL functions. This depends on how any particular database handles wide characters and line breaks. For Example, newline characters aren't counted in Length in PostgreSQL while they are counted in the Designer Length function, and results in Designer may differ depending on whether the ANSI or Unicode driver is used.

LowerCase(String): Converts a string to lower case.
Example
LowerCase(input_col) returns lowecase from input_col.

PadLeft (String, len, char): Pads the string to the left with the specified character to the specified length.
Example
PadLeft("M", 4, "x") returns "xxxM".
PadLeft(char_col, 4, "x") returns "xxxM".

PadRight (String, len, char): Pads the string to the right with the specified character to the specified length.
Example
PadRight("M", 4, "x") returns "Mxxx".
PadRight(char_col, 4, "x") returns "Mxxx".

Replace(String, Target, Replacement): Returns the string (String) after replacing each occurrence of the String (Target) with the String (Replacement).
Example
Replace("Good judgment comes from experience", "experience", "awareness") returns "Good judgment comes from awareness"
Replace(input_col, "experience", "awareness") returns replaced values based on column values.

ReplaceChar(String, y, z): Returns the string (String) after replacing each occurrence of the character (y) with the character (z). If the replacement character (z) is a string with more than one character, only the first character is used. If (z) is empty, each character (String) that matches any character in (y) is simply removed.
Example
ReplaceChar("abcdefb", "b", "") returns "a_cdef".
ReplaceChar(input_col, "b", "") returns .

ReplaceFirst(String, Target, Replacement): Returns the string (String) after replacing the first occurrence of the string (Target) with the string (Replacement).
Example
ReplaceFirst("abcdefb", "b", "_") returns "a_cdefb".
ReplaceFirst(input_col, "b", "_") returns corresponding column_values.

ReverseString(String): Reverses all the characters in the string.
Example
ReverseString("abcdefb") returns "bfedcba".
ReverseString(input_col) returns "bfedcba".

Right(String, len): Returns the last (len) characters of the string. If len is less than 0 or greater than the length of String, the string remains unchanged.
Example
Right("92688", 3) returns a value of "688".
Right(input_col, 3) returns a value of "688".

StartsWith(String, Target, CaseInsensitive=1): Checks if a string starts with a particular string. Returns True if String starts with a particular string Target, else returns False.
Example
StartsWith('ABC123', 'ABC') returns True.
StartsWith('ABC123', 'abc') returns True.
StartsWith(input_col, 'abc', 0) returns False.


StripQuotes(String): Removes a matched set of quotation marks or apostrophes from the ends of the string.
Example
StripQuotes("Hello there") returns Hello there.
StripQuotes("'Hello there,' she said.") returns 'Hello there,' she said.
StripQuotes('"Hello there," she said.') returns "Hello there," she said.


Substring(String, start, length): Returns the substring of (String) starting at (start), stopping after (length), if provided.
Example
Substring("949-222-4356", 4, 8) returns "222-4356".
Substring("949-222-4356", 4, 6) returns "222-43".
Substring(input_col, 4) returns "substring depending on the column values.

TitleCase(String): Converts a string to title case.
Example
TitleCase("john smith") returns "John Smith".
TitleCase(input_col)


Math
+++++++++++++++

abs(Double):
Returns the absolute value of the given number.
Example:
abs(-5.6) returns 5.6.
abs(input_col) returns absolute values for input_col.

acos(Double):
Returns the arc cosine (inverse cosine) of the given angle in radians.
Example:
acos(0.5) returns approximately 1.047 (radians).
acos(input_col) returns the arc cosine of values in input_col.

asin(Double):
Returns the arc sine (inverse sine) of the given angle in radians.
Example:
asin(0.5) returns approximately 0.524 (radians).
asin(input_col) returns the arc sine of values in input_col.

atan(Double):
Returns the arc tangent (inverse tangent) of the given angle in radians.
Example:
atan(1.0) returns approximately 0.785 (radians).
atan(input_col) returns the arc tangent of values in input_col.

atan2(Double, Double):
Returns the angle (in radians) between the positive x-axis and the vector from the origin to the point (x, y).
Example:
atan2(1.0, 1.0) returns approximately 0.785 (radians).
atan2(input_col, 1.0) returns the angle between input_col and 1.0.

ceil(Double):
Returns the smallest integer that is greater than or equal to the given number.
Example:
ceil(4.3) returns 5.0.
ceil(input_col) returns the smallest integer greater than or equal to values in input_col.

cos(Double):
Returns the cosine of the given angle in radians.
Example:
cos(0.0) returns 1.0.
cos(input_col) returns the cosine of values in input_col.

cosh(Double):
Returns the hyperbolic cosine of the given number.
Example:
cosh(0.0) returns 1.0.
cosh(input_col) returns the hyperbolic cosine of values in input_col.

exp(Double):
Returns the Euler's number (e) raised to the power of the given number.
Example:
exp(1.0) returns approximately 2.718.
exp(input_col) returns the Euler's number raised to the power of values in input_col.

floor(Double):
Returns the largest integer that is less than or equal to the given number.
Example:
floor(4.9) returns 4.0.
floor(input_col) returns the largest integer less than or equal to values in input_col.

log(Double):
Returns the natural logarithm (base e) of the given number.
Example:
log(10.0) returns approximately 2.302.
log(input_col) returns the natural logarithm of values in input_col.

log10(Double):
Returns the base 10 logarithm of the given number.
Example:
log10(100.0) returns 2.0.
log10(input_col) returns the base 10 logarithm of values in input_col.

mod(Integer, Integer):
Returns the remainder when the first number is divided by the second number.
Example:
mod(10, 3) returns 1.
mod(input_col, 5) returns the remainder of input_col divided by 5.

pow(Double, Double):
Returns the first number raised to the power of the second number.
Example:
pow(2.0, 3.0) returns 8.0.
pow(input_col, 2.0) returns the values in input_col raised to the power of 2.0.

rand():
Returns a random floating-point number between 0.0 and 1.0 (exclusive).
Example:
rand() returns a random number like 0.728374.
rand() returns a random number between 0.0 and 1.0 for each row.

randInt(Integer):
Returns a random integer between 0 and the specified value (exclusive).
Example:
randInt(10) returns a random integer between 0 and 9.
randInt(100) returns a random integer between 0 and 99 for each row.

round(Double, Double):
Returns the given number rounded to the specified number of decimal places.
Example:
round(3.14159, 2) returns 3.14.
round(input_col, 2) returns the values in input_col rounded to 2 decimal places.

sin(Double):
Returns the sine of the given angle in radians.
Example:
sin(0.0) returns 0.0.
sin(input_col) returns the sine of values in input_col.

sinh(Double):
Returns the hyperbolic sine of the given number.
Example:
sinh(0.0) returns 0.0.
sinh(input_col) returns the hyperbolic sine of values in input_col.

sqrt(Double):
Returns the square root of the given number.
Example:
sqrt(16.0) returns 4.0.
sqrt(input_col) returns the square root of values in input_col.

tan(Double):
Returns the tangent of the given angle in radians.
Example:
tan(0.785) returns approximately 1.0.
tan(input_col) returns the tangent of values in input_col.

tanh(Double):
Returns the hyperbolic tangent of the given number.
Example:
tanh(0.0) returns 0.0.
tanh(input_col) returns the hyperbolic tangent of values in input_col.

Date/Time
+++++++++++++++
dateTimeAdd(String, Integer, String):
Adds the specified number of units to the given date and time in the provided format and returns the updated date and time as a string.
Example:
dateTimeAdd('2023-07-25 12:30:00', 2, 'hours') returns 2023-07-25 14:30:00.
dateTimeAdd(input_col, 2, 'hours')

dateTimeDay(String, Integer):
Returns the day of the month for the given date as an integer.
Example:
dateTimeDay('2023-07-25') returns 25.
dateTimeDay(input_col)

dateTimeDiff(String, String, String):
Calculates the difference between two dates in the provided format and returns the result in terms of the specified unit (e.g., days, months, years).
Example:
dateTimeDiff('2023-07-25', '2023-07-28', 'days') returns 3.
dateTimeDiff(input_col_1, input_col_2, 'days')

dateTimeFirstOfMonth():
Returns the first day of the current month as a string in the default format.
Example:
dateTimeFirstOfMonth() returns the first day of the current month, like 2023-07-01.

dateTimeFormat(String, String, String):
Converts the given date string from one format to another format and returns the updated date as a string.
Example:
dateTimeFormat('2023-07-25 12:30:00', 'yyyy-MM-dd HH:mm:ss', 'MM/dd/yyyy') returns 07/25/2023.
dateTimeFormat(input_col, 'yyyy-MM-dd HH:mm:ss', 'MM/dd/yyyy')

dateTimeHour(String, Integer):
Returns the hour of the day for the given date as an integer (24-hour format).
Example:
dateTimeHour('2023-07-25 15:45:00') returns 15.
dateTimeHour('2023-07-25 15:45:00') returns 15.

dateTimeLastOfMonth():
Returns the last day of the current month as a string in the default format.
Example:
dateTimeLastOfMonth() returns the last day of the current month, like 2023-07-31.

dateTimeMinutes(String, Integer):
Returns the minutes of the hour for the given date as an integer.
Example:
dateTimeMinutes('2023-07-25 15:45:00') returns 45.

dateTimeMonth(String, Integer):
Returns the month of the year for the given date as an integer.
Example:
dateTimeMonth('2023-07-25') returns 7.

dateTimeNow():
Returns the current date and time as a string in the default format.
Example:
dateTimeNow() returns the current date and time, like 2023-07-25 16:30:00.

dateTimeSeconds(String, Integer):
Returns the seconds of the minute for the given date as an integer.
Example:
dateTimeSeconds('2023-07-25 15:45:30') returns 30.

dateTimeStart():
Returns the current date with the time set to the beginning of the day (00:00:00) as a string in the default format.
Example:
dateTimeStart() returns the current date with the time set to 00:00:00, like 2023-07-25 00:00:00.

dateTimeToday():
Returns the current date as a string in the default format.
Example:
dateTimeToday() returns the current date, like 2023-07-25.

dateTimeToLocal(String, String):
Converts the given date string from UTC to the local time zone and returns the updated date as a string.
Example:
dateTimeToLocal('2023-07-25 12:00:00', 'yyyy-MM-dd HH:mm:ss') returns the converted local time.

dateTimeToUTC(String, String):
Converts the given date string from the local time zone to UTC and returns the updated date as a string.
Example:
dateTimeToUTC('2023-07-25 12:00:00', 'yyyy-MM-dd HH:mm:ss') returns the converted UTC time.

dateTimeTrim(String, String):
Trims the time part of the given date string according to the provided format and returns the updated date as a string.
Example:
dateTimeTrim('2023-07-25 12:30:00', 'yyyy-MM-dd') returns 2023-07-25.

dateTimeYear(String, Integer):
Returns the year of the given date as an integer.
Example:
dateTimeYear('2023-07-25') returns 2023.

Operators
+++++++++++++++
ADDITION(Double):
Returns the sum of two double values.
Example:

and(Boolean, Boolean):
Performs a logical AND operation between two boolean values and returns the result.
Example:
and(true, false) returns false.
and(input_col_1, input_col_2) returns the result of the AND operation between input_col and true.

or(Boolean, Boolean):
Performs a logical OR operation between two boolean values and returns the result.
Example:
or(true, false) returns true.
or(input_col_1, input_col_2) returns the result of the OR operation between input_col_1 and input_col_2.

not(Boolean):
Performs a logical NOT operation on a boolean value and returns the result.
Example:
not(true) returns false.
not(input_col) returns the negation of values in input_col.

equalTo(Object, Object):
Checks if two values are equal and returns a boolean result.
Example:
equalTo(10, 10) returns true.
equalTo(input_col_1, input_col_2)

greaterThan(Comparable, Comparable):
Checks if the first value is greater than the second value and returns a boolean result.
Example:
greaterThan(5, 3) returns true.
greaterThan(input_col_1, input_col_2)

greaterThanOrEqual(Comparable, Comparable):
Checks if the first value is greater than or equal to the second value and returns a boolean result.
Example:
greaterThanOrEqual(5, 5) returns true.
greaterThanOrEqual(input_col_1, input_col_2)

lessThan(Comparable, Comparable):
Checks if the first value is less than the second value and returns a boolean result.
Example:
lessThan(3, 5) returns true.
lessThan(input_col, input_col_2)

lessThanOrEqual(Comparable, Comparable):
Checks if the first value is less than or equal to the second value and returns a boolean result.
Example:
lessThanOrEqual(5, 5) returns true.
lessThanOrEqual(input_col, input_col_2)

notEqualTo(Object, Object):
Checks if two values are not equal and returns a boolean result.
Example:
notEqualTo(5, 10) returns true.
notEqualTo(input_col_1, input_col_2)

subtraction(Double, Double):
Returns the difference between two double values.
Example:
subtraction(10.0, 5.0) returns 5.0.
subtraction(input_col_1, input_col_2)
