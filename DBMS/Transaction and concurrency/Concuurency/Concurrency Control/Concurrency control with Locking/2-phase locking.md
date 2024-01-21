# 2 Phase Locking

A transcation is said to be follow 2-phase protocol if locking and unlocking is done on 2 phase.

1. **Growing**: New locks on data item may acquired but none can be released.
2. **Shrinking**: Existing locks may be released but no new locks can be acquired.
