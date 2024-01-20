1. Atomicty
2. Consistency
3. Isolation
4. Durability

## Atmoicity

* A transaction is trated a single logical unit of work.
* All the operation within that unit must be either completed entirly or aborted/rollback.

## Consistency

* It is the result of concurrent execution of several transaction.
* In multiuser and distributed database where several transactions are likely to be executed cconcurrently.
* The data must consistent for every trasnaction tha using the same data.

## Isolation

* Data used by transactionn T1 cannot be used by other transaction T2 unitl T1 commits.

## Durability

* The ability to recover the data and reaches back to the consistent state in the event of failure.
* If a trnsaction reaches to the consistent state it's update cannot be lost even in event of system failure.
