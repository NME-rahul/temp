# 2 Phase Locking

A transcation is said to be follow 2-phase protocol if locking and unlocking is done on 2 phase.

1. **Growing**: New locks on data item may acquired but none can be released.
2. **Shrinking**: Existing locks may be released but no new locks can be acquired.

* 2PL ensures the serializability by the help of lock point.

**Lock Point**: Point at which growing phase end, ie. point at which transaction acquires it's last lock.

**Note**: upgrading of locks from shared to exclusive is allowd in growing phase but not in shrinking phase.


## Problems with 2PL
Casecade rollback
deadlock and starvation
