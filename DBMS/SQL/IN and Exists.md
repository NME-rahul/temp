## IN(is element of) $\equiv$ = Some
* It matches the outer query with inner subquery.
* matches every row of outer query with every row of inner query whether it found match or not it keeps go on.
  * if inner query has 6 records and outer query have 10 records then total matches will be 60.
* Inner query must return only one column that will only be matched by only columns of outer query.
* It requires matching point(SupplierID).
* Took more time obviosuly.

      SELECT SupplierName FROM Supplier WHERE SupplierID IN (SELECT SupplierID FROM Product WHERE ProductName = "Computer");

      SELECT SupplierName FROM Supplier WHERE SupplierID = SOME (SELECT SupplierID FROM Product WHERE ProductName = "Computer");


## EXISTS
* It also matches outer query with inner query rows but it stops when it founds one matching record of outer query and not matches for that same record again.
* Not neccesassry that inner query must return only one column.
* It does not require any match point.
* It takes less time.

      SELECT SupplierName FROM Supplier S WHERE EXISTS (SELECT SupplierID FROM Product P WHERE ProductName = "Computer" and P.SupplierID = S.SupplierID);


[Practice here!](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_exists)
