## IN(is element of) $\equiv$ = Some

    .... WEHRE column IN (1, 2, 3, 4)

    .....WHERE column = 1 OR column = 2 OR column = 3 OR column = 4;


* It is shortend form of `OR`.
* It matches the every outer query table tuples with every tuple of subquery(inner query) table.
* matches every row of outer query with every row of inner query whether it found match or not it keeps go on.
  * if inner query has 6 records and outer query have 10 records then total matches will be 60.
* Inner query must return only one column that will only be matched by only columns of outer query.
* It requires matching point(let SupplierID).
* Took more time obviosuly.

      SELECT SupplierName FROM Supplier WHERE SupplierID IN (SELECT SupplierID FROM Product WHERE ProductName = "Computer");

      SELECT SupplierName FROM Supplier WHERE SupplierID = SOME (SELECT SupplierID FROM Product WHERE ProductName = "Computer");


## EXISTS
* it does not matches the tuple directly but Inner query matches the every tuple of outer query table with inner query table.
* EXISTS returns TRUE or FALSE. TRUE if result of inner query is empty or FALSE if inner query result is non-empty.
* When WHERE condition becomes FALSE then result does not contain the corresponding tuple of that iteration.
* Inner query stops finding tuples when it found a single matching tuple because it makes table non-mepty and we'll get TRUE.
* How matching is done?
  * matching is done with the help of nesting.
* Because we are considering empty table as FAlSE and non-empty as TRUE so we can select any number attributes in inner query table.
* It takes less time.

      SELECT SupplierName
      FROM Supplier S
      WHERE
      EXISTS (SELECT SupplierID FROM Product P WHERE ProductName = "Computer" and P.SupplierID = S.SupplierID);

[Practice here!](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_exists)
