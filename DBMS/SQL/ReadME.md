* Subqueries are always solved first.

* in SQL we have 3 truth values
  1. TRUE
  2. FALSE
  3. UNKNOWN : it is return by any logical comprision with NULL value.
 
* On logical comprision tuple returning `UNKNOWN` truth value does not select by a SQL qeury.

**Trick:-**<br>
Assume <br>
1. Truth $\equiv$ 1
2. False $\equiv$ 0
3. UNKNOWN $\equiv$ $\frac{1}{2}$

       not(Truth Value X) = 1 - Truth Value X 

* SQL works on multiset however pure relations are mathematical concept that works on set i.e. a relation concept in RDBMS can not have duplicate(also `NULL`) tuple but Tables of SQL can have.

---

* Arithmatic operation with `NULL` values give `NULL`.
* Aggregate function returns `NULL` on empty table except `COUNT(column_name)` and `COUNT(*)`
