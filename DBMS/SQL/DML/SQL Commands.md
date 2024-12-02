![](https://static.javatpoint.com/dbms/images/dbms-sql-command.png)

### SELECT command

SELECT statement is used to query or retrieve information maentioned from specified columns. it doesn't remove duplicates from data.

    SELECT {column1, column2,...} FROM {table_name};


#### DISTINCT

Returns only distinct results. it remove duplicates.

    SELECT DISTINCT {column1, column2,...} FROM {table_name};


#### WHERE

* Introduces condition with SELECT command, It is used to retrieve data with some condition like in specific range etc.
  
    SELECT {column1, column2,...} FROM {table_name} WHERE {conditions};

you can use one or more condition with **AND** **OR** operator.

Conditional operators:
* =(equal)
    SELECT * FROM customers WHERE customer_name = 'Neelam';
* <> or !=(not equal)
    SELECT * FROM customer WHERE customer_name <> 'Neelam';
* *>*(greater then)
    SELECT * FROM customer WHERE customer_id > 13;
* *<*(less then)
    SELECT * FROM customers WHERE customer_id < 13;
* *>=*(greate then equal)
    SELECT * FROM customer WHERE customer_id >= 13;
* *<=*(less then equal)
    SELECT * FROM customer WHERE customer_id <= 13;
* BETWEEN(between in range)
    SELECT * FROM Customer WHERE customer_id BETWEEN 13 and 47;
* LIKE(search for pattern)
    SELECT * FROM customer WHERE customer_name LIKE 'N%';

Wildcards:
* _ (single character patterns)
    * '_a' starts with any chracter and ends with a, such as ea, ba, ca, ta etc.
    * 'a_b' starts with a and ends with b. such as acb, abb, avb, apb etc.
    
* % (any number of character patterns)
  * '%a' starts with any and ends with 'a', such as 'ba', 'ma', 'latika', etc.
  * 'a%' starts with 'a' and ends with any such as 'arvind', 'aayush', 'aman', 'abhishek' etc.
  * '%a%' start and ends with any but a should come in between, such as 'Neelam', 'Rahul', etc.
   
* [] (use as OR operator with characters)
  * '[oa]%' starts either 'a' or 'o' and ends with any.
  * '[a-f]%' starts with any single chrachters from 'a' to 'f' and ends with any.
  * '%[an]%' strats and ends with any but either 'a' or 'n' should come in  betw.een.
  * '[_a]%' Select all records where the second letter of the City is an "a".
  * '[!an]%' select all recors where it should not starts with 'a' or 'n'.


### INSERT INTO

This statement is used to insert new rows into a table. if you are inserting values in all the columns then you need not to specify column name. It always insert a whole row or set of rows and canot insert a single cell.

    INSERT INTO {table_name} VALUES ('value1', 'value2', ..., 'valueN');

    INSERT INTO {table_name} ('column1', 'column5', 'column8') VALUES ('value1', 'value5', 'value8')

### UPDATE

This statement is used to modify the data in a table. it can update only one cell or set of cells at at a time.

    UPDATE {table_name} SET {column_name} = {some_value};

    UPDATE {table_name} SET {column_name} = {some_value} WHERE {condition};


### DELETE

This statment is used to delete rows from a table. The WHERE is used to delete row with specific condition otherwise all the rows will delete. It always delete rows or set of rows not any signle cell.

Deleting every will not delete realtion, it will remain as it is.

    DELETE FROM {table_name} WHERE {condition};


    DELETE FROM Borrow
    WHERE CardNo IN(
                    SELECT CardNo From User
                    WHERE name = "ABC"
    );

### cartesian product

The cartesian product of tow set is the set of all ordered pairs of element.

s1: {1, 2, 3} s2: {4, 5}

s1xs2: {(1,4), (1,5), (2,4), (2,5), (3,4}, (3,5)}

    SELECT * FROM {table1} {table2}...;


### Ordering tuple

It lists the tuples in alphabatical order.

    SELECT * FROM {table_name} WHERE {condition} ORDERBY {column_name} [ASC, DESC];


### join

Join is used to get data from two or more tables which appear as single table after joining.
* INNER JOIN
* OUTER JOIN
  * LEFT OUTER JOIN
  * RIGHT OUTER JOIN
  * FULL OUTER JOIN 
