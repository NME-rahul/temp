## HAVING

* ```HAVING``` function is added in SQL because ```WHERE``` cannot be used with aggregation function.
  * ```WHERE``` only include condition of single value like salary > 40000.
* It can be used with attribute alias like SELECT avg(salary) s FROM Emmployee GROUP BY DeptName HAVING AVG(s) > 40000;

      SELECT column_name(s)
      FROM table_name
      WHERE condition
      GROUP BY column_name(s)
      HAVING condition
      ORDER BY column_name(s);
