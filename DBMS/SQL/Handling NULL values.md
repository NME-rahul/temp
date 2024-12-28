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

1. NULL & relationa operator
   * No comparision allowed, return `unknown`
2. NULL & arithmatic operators
   * No aritmatic operation allows simpley returns NULL
3. NULL and aggregation function
   * they ignores the NULL value, except `COUNT(*)`
2. NULL & IN
   * it doesnot match with value which is NULL
4. NULL & SOME
   * Simialr to IN --> =SOME
6. NULL & ALL
   * ALL will always return false if subquery contains atleast one NUlL
8. NULL & NOT IN
   * False, if subquery contains at least one NULL; NOT IN <----> <> ALL
10. NULL & IN BETWEEN
    * it will always reurn false if lower or higher or both values are NULL
12. NULL & ORDER BY
    * Treat NULL as smalles value
14. NULL & GROUP BY
    * treat NULL as equal to values and make a sperate group for it also.
15. If NULL appears in attribute then aggregate fucntion ignores them.
