SQL - Structured Query Language is used to query, manipulate, and transform data from a relational database

**SELECT** is used to select columns from the database with all the rows in it.


SELECT *                          //Selects all the rows from the database
FROM TABLE TABLENAME 


**WHERE** is used to filter out data based on some criteria.
Conditions can have
- operators like <=,>=,==,!=,<,>
- BETWEEN … AND …          Example - col_name BETWEEN 1.5 AND 10.5
- NOT BETWEEN .. AND..     Example - col_name NOT BETWEEN 1 AND 10
- IN                       Example - col_name IN (2, 4, 6)
- NOT IN                   Example - col_name NOT IN (1, 3, 5)


Operator	     Condition	                                                                                                          Example
=	            Case sensitive exact string comparison (notice the single equals)	                                                    col_name = "abc"
!= or <>	    Case sensitive exact string inequality comparison	                                                                    col_name != "abcd"
LIKE	        Case insensitive exact string comparison	                                                                            col_name LIKE "ABC"
NOT LIKE	    Case insensitive exact string inequality comparison	                                                                  col_name NOT LIKE "ABCD"
%	            Used anywhere in a string to match a sequence of zero or more characters (only with LIKE or NOT LIKE)	                col_name LIKE "%AT%" (matches "AT", "ATTIC", "CAT" or even "BATS")
_	            Used anywhere in a string to match a single character (only with LIKE or NOT LIKE)	                                  col_name LIKE "AN_ (matches "AND", but not "AN")
IN (…)	      String exists in a list	                                                                                              col_name IN ("A", "B", "C")
NOT IN (…)	  String does not exist in a list	                                                                                      col_name NOT IN ("D", "E", "F")


**DISTINCT** used to remove duplicates

**ORDER BY** column ASC/DESC - used to sort data alphabetically in aescending or descending order
LIMIT AND OFFSET : LIMIT will reduce the number of rows to return, and the optional OFFSET will specify where to begin counting the number rows from.


**INNER JOIN** - matches rows from the first table and the second table which have the same key
Example - SELECT column, another_table_column, …
          FROM mytable
          INNER JOIN another_table 
             ON mytable.id = another_table.id
          WHERE condition(s)
          ORDER BY column, … ASC/DESC
          LIMIT num_limit OFFSET num_offset;

EXAMPLE - SELECT column, another_column, …
          FROM mytable
          INNER/LEFT/RIGHT/FULL JOIN another_table 
              ON mytable.id = another_table.matching_id
          WHERE condition(s)
          ORDER BY column, … ASC/DESC
          LIMIT num_limit OFFSET num_offset;



**AGGREGATE FUNCTION** - SUM,COUNT, MIN MAX
EXAMPLE - SELECT AGG_FUNC(column_or_expression) AS aggregate_description, …
          FROM mytable
          WHERE constraint_expression
          GROUP BY column;


**QUERY ORDER OF EXECUTION**
1- FROM and JOINs
2- WHERE
3- GROUP BY
4- HAVING
5- SELECT
6- DISTINCT  //OPTIONAL
7- ORER BY
8- LIMIT OFFSET


**************************** **DML COMMANDS** ************************************


**INSERTING ROWS**
INSERT INTO mytable
(column, another_column, …)          //OPTIONAL
VALUES (value_or_expr, another_value_or_expr, …),
      (value_or_expr_2, another_value_or_expr_2, …),
      …;

**UPDATING ROWS**
UPDATE mytable
SET column = value_or_expr, 
    other_column = another_value_or_expr, 
    …
WHERE condition;

**DELETING ROWS**
DELETE FROM mytable
WHERE condition;

_IT IS RECOMMENDED TO run the constraint in a SELECT query first to ensure that you are removing the right rows_

**CREATE TABLE**
CREATE TABLE IF NOT EXISTS mytable (
    column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value,
    …
);

**ADDING COLUMNS**
ALTER TABLE mytable
ADD column DataType OptionalTableConstraint 
    DEFAULT default_value;


**DELETING COLUMN**
ALTER TABLE mytable
DROP column_to_be_deleted;

















