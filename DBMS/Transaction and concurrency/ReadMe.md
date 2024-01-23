# Transaction

* A transaction is a logical unit of work.
* It involves a sequence of several operations like begin, read/write and commit.
* A transaction is kept in main-memory unitl the trnsaction is commit, after commit the updates are wriiten into the disk to ensure recovery from any crashes.
* All parts of trnsaction must be complete to ensure data integrity.

# Concurrency

* The cordination between simultaneous execution of transactions in a multiprocessing environment.
