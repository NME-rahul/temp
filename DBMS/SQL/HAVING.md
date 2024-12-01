## HAVING $\equiv$ WHERE after GROUP BY

* ```HAVING``` function is added in SQL because ```WHERE``` cannot be used after GROUP BY.
  * Whenever you want to apply GROUP BY with some condition, HAVING is used and HAVING must be used with some aggregate function because GROUP BY works on sets that have single identfier(HAVING condindtion must compare with single tuple that will only come by aggregate fucntion).
* It can be used with attribute alias like SELECT avg(salary) s FROM Emmployee GROUP BY DeptName HAVING AVG(s) > 40000;

      SELECT column_name(s)
      FROM table_name
      WHERE condition
      GROUP BY column_name(s)
      HAVING condition
      ORDER BY column_name(s);


## Diference between HAVING and GROUP BY

<div align="center">

 ||WHERE|HAVING|
 |---|---|-----|
 |1.| It is used to impose condition on rows of table|It is use to impose condition on set of rows|
 |2.|It is use before GROUP BY clause| It is used after GROUP BY clause|
 |3.|It cannnot contain aggregate function|It can contain aggregate functtion|
</div>
