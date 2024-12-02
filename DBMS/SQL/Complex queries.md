# Complex queries with FROM clause

      SELECT s1, MAX(p1)
      FROM(
          SELECT Sname, MAX(Price)
          FROM Supplier
          GROUP BY Sname
          AS Sup(s1, p1)
      );

* We can have SELECT in FROM clause, and it called complex queries.
* the subquery is selecting the maximum price book supplied by each suppliers, then outer query is selcting maximum price from them, so overall query is finding "the maximm price book supplied by any supplier".


# Complex queries with WITH clause

    WITH Supp_MAX(price1)
    AS
    SELECT MAX(Price)
    FROM Supplier
    
    SELECT Sname
    FROM Supplier, Supp_MAX
    WHERE price = price1;

* Above quer is first creating table named Supp_MAX with only one attribute "price1" ans selecting rows from Supplier table but SELECT clause is only selecting maximum price book supplied by any supplier so, table Supp_MAX will have only one row of maximum price book. Aggregate functionreturn only single tuple so output have only one row showing max price.
* after that we're joining Supp_MAX table with Supplier table and matching on price, because now we're matching so output can have multiple rows, suppose max price is 500 and two different supplier supplies with same price then we can have multiple rows in output table.
