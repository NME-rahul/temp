# ALL

* it returns TRUE when the condition evaluates to true for all the tuples that are in table.
* It acts like a universal quantifier. 

* it matches every tuple of outer query with each tuple of inner query table iteration-by-iteration and because it acts like a universal quantifier so if all tuple of inner query table matches then it returns TRUE otherwise FALSE.
* What if inner query table is empty?
  * It will always returns TRUE.
  * because we know universal quantifer returns TRUE for empty sets because there is no tuple to make FALSE.

<div></div>

      SELECT supplierID
      FROM Suppliers
      WHERE price > ALL(SELECT AVG(price) FROM
                        FROM Suppliers, Products
                        AND Suppliers.supplierID = Products.supplierID
                        GROUP BY productName);

* The above query returns suplierID of all suppllier who supplies **all the products** higher then average price suppplied by all the suppliers. 


# ANY

* it returns true when the condition evaluates to true for at least one tuple that are in table.
* It acts like a existential quantifier.

* it matches every tuple of outer query with each tuple of inner query table iteration-by-iteration and because it acts like a existential quantifier so if any tuple of inner query table matches then it returns TRUE and FALSE if all doesnot matches.
* What if inner query table is empty?
  * It will always returns FALSE.
  * because we know existentia quantifer returns FALSE for empty sets because there is not tuple to make TRUE.

<div></div>

    SELECT supplierID
      FROM Suppliers
      WHERE price > ANY(SELECT AVG(price) FROM
                        FROM Suppliers, Products
                        AND Suppliers.supplierID = Products.supplierID
                        GROUP BY productName);

* The above query returns suplierID of all suppllier who supplies **at least one** products higher then average price suppplied by all the suppliers. 
