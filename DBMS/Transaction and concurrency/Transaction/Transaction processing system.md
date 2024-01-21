# Transaction processing system

A transaction includes 2 basic operations

* Read(X)
* Write(X)

<p align="Center">
  <img src="https://github.com/NME-rahul/temp/assets/100432854/3f1b6eb0-d3f4-4a38-9400-dd5fcf65d0ba" />
</p>

1. **Active state**:
   * When the instruction of the transaction are running then the transaction is in active state.
   * It starts imddiatly after a transaction is executed.
   * Here, it can perform read/write operations.

2. **Partially commited**:
   * After completion of read/write operation the changes are made in main-memory or local buffer.

3. **Commit**:
   * In this state read/write values are permanently stored in the disk.

4. **Failed**:
   * when any instruction fails during read/write or making the transaction goes into the failed state.
   * Or failure during permanent(commit) change of data on database.

5. **Aborted State**:
   * When any transaction fails it goes into failed state and system rollbacks every efffect made by transaction and send it into Abort state.

6. **Terminate**:
   * If there is no rollback comes from commited state then the system is consistent and ready for new transaction processing.
