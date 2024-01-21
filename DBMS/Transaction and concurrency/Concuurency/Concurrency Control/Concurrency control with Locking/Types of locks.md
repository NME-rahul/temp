# Types of Locks

1. Binary Lock
2. Shared/Exclusive Lock

### Binary Locks

* It has two states.
  * Locked(1)
  * Unlocked(0)

* If an object, that is database, table, page, or row is locked by a transaction, then no other transactions can use that data item.
* It is too restrictive to get optimal concurrency.
* It does not provides locks to two transactions at the same time even if both wants to read.

### Shared/Exclusive

* It has 3 stages.
  * Unlocked
  * Shared
  * Exclusive
  
* Nature of shared and exclusive locks.
  * Shared: less restrictive, can be provide to multiple transaction at a time whenever every transaction wants to read data item.
  * Exclusing: much restrictive, only provides to a single transaction at a time whenever transaction wants to write on data item.

* Exclusive lock is provide when their is potential conflict exists.
