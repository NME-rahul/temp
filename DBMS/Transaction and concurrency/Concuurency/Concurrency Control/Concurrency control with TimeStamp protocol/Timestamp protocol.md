# Timestamp protocol

Each transaction that comes in database to perform an operation, the DBMS assign it a unique timestamp of arrival. A younger(transaction that comes latest in database) transaction have higher value then older(transaction that is already in databbase) transaction.

The priorrity of older transaction to complete first is higher then younger transactions

By the help of timestap(unique), timestamp protocol makes transactions serializable like $T_1(older) -> T_2(younger)$.

## Rules

R_TS: Last transaction which performed read successfully.
W_TS: Last transaction which performed write successfully.

1. Transation $T_i$ isssues a Read(A) operation.
   * IF W_TS(A) > $TS(T_i)$
     * Rollback $T_i$
   * Otherwise
     * Execute Read(A) operation
     * Set R_TS(A) = max{R_TS(A), $TS(T_i)$}

2. Transation $T_i$ isssues a Write(A) operation
   * IF R_TS(A) > $TS(T_i)$
     * Rollback $T_i$
   * IF W_TS(A) > $TS(T_i)$
     * Rollback $T_i$
   * Otherwise
     * Execute WRITE(A) operation
     * Set W_TS(A) = $TS(T_i)$
    

* Apply this rule independetly on each data item of transactions.

**Eg.**

<p align="center">
  <img src="https://github.com/NME-rahul/temp/blob/main/Resources/Images/20240125_213936.jpg" />
</p>

<p align="center">
  <img src="https://github.com/NME-rahul/temp/blob/main/Resources/Images/20240125_213940.jpg" />
</p>

<p align="center">
  <img src="https://github.com/NME-rahul/temp/blob/main/Resources/Images/20240125_213948.jpg" />
</p>

<p align="center">
  <img src="https://github.com/NME-rahul/temp/blob/main/Resources/Images/20240125_214217.jpg" />
</p>


<p align="center">
  <img src="https://github.com/NME-rahul/temp/blob/main/Resources/Images/20240125_213952.jpg" />
</p>


<p align="center">
  <img src="https://github.com/NME-rahul/temp/blob/main/Resources/Images/20240125_214001.jpg" />
</p>


<p align="center">
  <img src="https://github.com/NME-rahul/temp/blob/main/Resources/Images/20240125_214004.jpg" />
</p>


<p align="center">
  <img src="https://github.com/NME-rahul/temp/blob/main/Resources/Images/20240125_214030.jpg" />
</p>

**Advantage**
* Ensures serializability.
* No deadlocks

**Disadvantage**
* Schedule may or may not be recoverable and may not even cascade-less.
