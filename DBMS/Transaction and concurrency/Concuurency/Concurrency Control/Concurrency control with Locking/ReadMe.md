# Locks

Locks guarntess that no two transactions can use same data item at same time.


## Locks Granularity

It baascially indicates the level of locking.

1. **Database Level**: In a database level lock, the entire database is locked, this level of locking is useful for batch processing not and suitable for online multiuser DBMSs.

2. **Table Level**: In a table-level lock, the entire table is locked, preventing access to use of any row of table.

3. **Page level**: In a page-level lock, the DBMS locks the entire disk page. transactions can use the same table but not the same segment of table.

4. **Row Level**: It is less restrictive, it allows concurrent transactions to access different rows of table.

5. **Field Level**: It allows concurrent transactions to access the same row but with different fields/attributes/columns.
