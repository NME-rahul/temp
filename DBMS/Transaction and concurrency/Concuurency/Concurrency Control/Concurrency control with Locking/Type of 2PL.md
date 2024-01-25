# Type of 2PL locks

1. Strict 2PL: Restric for commit before releasing exclusive lock.
2. Rigourous 2PL: Restric for commit before relaeasing any lock.
3. Conservative 2PL: Acquire all locks before executing transaction. starts from lock point now growing phase.

## Strict 2PL

Every Write operation should end with commit before other tranasaction performs read or write on same data item. Basically Exclusive lock should be released only after commit.

<div align="center">

  |$T_1$|
  |---|
  |Lock-X(x)|
  |W(x)|
  |R(x)|
  |.|
  |.|
  |.|
  |Commit|
  |unlock(x)|
</div>


## Rigorous 2PL

* Every lock should be released after even shared lock.
* Much strict then strict 2PL.

<div align="center">

  |$T_1$|
  |---|
  |Lock(x)|
  |W(x) or R(x)|
  |.|
  |.|
  |.|
  |Commit|
  |unlock(x)|
</div>

## Conservative 2PL

* Lock All the items before trnsaction begins execution, by predeclaring its read-set and write-set.
* It starts from lock point(now grwoing phase). transaction can not acquire any lock after it sarts executon.
* It waits until all locks acquired it required before execution.
* Conservative 2-PL is Deadlock free and but it does not ensure a Strict schedule

<div align="center">

  |$T_1$|
  |---|
  |Lock-S(x)|
  | Lock-X(y)|
  |Lock-S(z)|
  |R(x)|
  |W(y)|
  |R(z)|
  |.|
  |.|
  |.|
</div>
