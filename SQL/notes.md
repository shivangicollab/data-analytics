SQL - Structured Query Language is used to query, manipulate, and transform data from a relational database

SELECT is used to select columns from the database with all the rows in it.


SELECT *                           //Selects all the rows from the database
FROM TABLE TABLENAME 


WHERE is used to filter out data based on some criteria.
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

