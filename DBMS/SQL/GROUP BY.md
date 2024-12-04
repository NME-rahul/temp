# GROUP BY

* it makes a logical set of same tuples that is specified in GROUP BY clause.
* These logical set are then used with aggregate function for eg. you groupby a employee table on the basis of departName and you use aggregate function avg on salary attribute then it will selct avg salary of employee in each departmenet.
* All attributes appeared in `SELECT` Clause must appear in `GROUP BY` clause.
  * but reverse is not True accroding to new standards, It is not necessary that all attributes used in `GROUP BY` clause must appear in `SELECT` clause.
  
* Whenver there is GROUP BY in sql query then there will be only one tuple in output table for the every group.

* If you want to display any attribute in outptut then it must also appear in GROUP BY clause and any extra attribute you want to select that is not ```GROUP BY``` clause then you must use those with some aggregate function.


      SELECT p.SupplierID, s.SupplierName, SUM(p.Price)
      FROM Products p, Supppliers s
      WHERE p.SupplierID = s.SupplierID
      GROUP BY p.SupplierID,  s.SupplierName

* In above query p.supplierID and s.SupplierName is in SELECT clause as well as in GROUP BY clause and extra attribute price is with the SUM aggregate function.


      SELECT SupplierName, COUNT(SupplierName), price
      FROM Book, Supplier
      GROUP BY SupplierName

  * the above query will produce error because a suppliername can have differnt price book(it may work in some versions of SQL but in general it will not, this type of query will produce multiple supplierName for each different price and that is not our Goal) so it is neccsaary that price attribute should also be in aggregate fucntion.

        SELECT SupplierName, COUNT(SupplierName), AVG(price)
        FROM Book, Supplier
        GROUP BY SupplierName
