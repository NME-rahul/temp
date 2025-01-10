# NULL values

* It is unkown value.
* Any comparision return truth value, `UNKOWN`
* It is keyword in sql.

* to see relation with NULL we have other operators like

to compare NULL with other: $= \\\ \rightarrow$ IS  NULL

### What is not a NUlL
* it is not Blank
* empty
* zero
* nothing
* missing value
* ignore able value
* garbage value
* optional value
* invalid
* void

# Summary

1. NULL & relational operator
   * No comparision allowed, return `unknown` hence it ignores and does not show in ouput.

<div align="center">
  
  |||AND (Truth Value)|
  |---|---|---|
  |FALSE|NULL|FALSE|
  |TRUE|NULL|FALSE|

  |||OR (Truth Value)|
  |---|---|---|
  |FALSE|NULL|FAlSE|
  |TRUE|NULL|TRUE|

</div>
  
2. NULL & arithmatic operators
   * No aritmatic operation allows simpley returns `NULL` and NULL will be in ouput.
  
3. NULL and aggregation function
   * they ignores the NULL value, except `COUNT(*)` (only when there is single column)
  
  
2. NULL & IN
   * We know `IN` requires only column in as subquery output that requires `SELECT` and it removes `NULL` values so in there is no chance of match
  

4. NULL & SOME
   * Simialr to IN --> =SOME

6. NULL & ALL
   * ALL will always return false if subquery contains atleast one NULL because `SELECT` in subquery will not return all records.
8. NULL & NOT IN
   * False, if subquery contains at least one NULL; NOT IN <----> <> ALL
10. NULL & IN BETWEEN
    * it will always reurn false if lower or higher or both values are NULL
12. NULL & ORDER BY
    * Treat NULL as smallest value
14. NULL & GROUP BY
    * treat NULL as equal to values and make a sperate group for it also.
15. If NULL appears in attribute then aggregate fucntion ignores them.
