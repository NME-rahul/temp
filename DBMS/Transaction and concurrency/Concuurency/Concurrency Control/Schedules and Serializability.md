# Schedule

The Order in which operations of multiple transactions appears for execution is called Schedule.

## Types of Schedule

<p align="center">
  <img src="https://github.com/NME-rahul/temp/assets/100432854/4cbf23d6-365c-4858-8b85-c0c60944697d" />
</p>

1. **Serial Schedule**:
   * All the transactions exceutes serially one after another.
   * When one transaction is execute, no other transaction is allowd to execute.
   * **Characteristics**:
     * Consistent
     * Recoverable
     * Cascadeless
     * Strict

1. **Serial Schedule**:
   * Multiple transactions executes concurrently.
   * Operations of all the transactions are interleaved with each other.
   * **Characteristics**: may not always.
     * Consistent
     * Recoverable
     * Cascadeless
     * Strict
