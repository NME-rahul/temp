# GROUP BY

* it makes a logical set of same tuples that is specified in GROUP BY clause.
* These logical set are then used with aggregate function for eg. you groupby a employee table on the basis of departName and you use aggregate function avg on salary attribute then it will selct avg salary of employee in each departmenet.
* All attributes appeared in GROUPBY Clause must appear in SELECT clause.

      SELECT CustomerName, COUNT(CustomerName)
      FROM Customers
      GROUP BY CustomerID;

* The Above sql query produces syntax error, at least one group point of GROUP BY clause should be there in SELECT clause. NOTE the previos line if  for specifically MICROSOFT SQL.


* If you want to display any attribute in outptut then you it must appear in GROUP BY clause.


      SELECT SupplierName, COUNT(SupplierName), price
      FROM Book, Supplier
      GROUP BY SupplierName

  * the above query will produce error because a suppliername can have differnt price book(it may work in some versions of SQL but in general it will not, this type of query will produce multiple supplierName for each differenc price and that is not our Goal) so it is neccsaary that price attribute should also be in aggregate fucntion.

        SELECT SupplierName, COUNT(SupplierName), AVG(price)
        FROM Book, Supplier
        GROUP BY SupplierName
