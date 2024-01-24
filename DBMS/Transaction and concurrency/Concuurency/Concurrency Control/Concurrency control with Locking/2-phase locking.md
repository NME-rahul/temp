# 2 Phase Locking

A transcation is said to be follow 2-phase protocol if locking and unlocking is done on 2 phase.

1. **Growing**: New locks on data item may acquired but none can be released.
2. **Shrinking**: Existing locks may be released but no new locks can be acquired.

* 2PL ensures the serializability by the help of lock point.

**Lock Point**: Point at which growing phase end, ie. point at which transaction acquires it's last lock.

<p align="center">
  <img src="" />
</p>

**Note**: upgrading of locks from shared to exclusive is allowd in growing phase but not in shrinking phase.


## Problems with 2PL
* Casecade rollback
* Starvation
* Deadlock

### Casecade rollback


### Starvation

<div align="center">

||$T_1$|$T_2$|$T_3$|$T_4$|
|---|----|----|---|---|
|1.|W(x)||||
|2.|||W(x)||
|3.||W(y)|||
|4.||||R(x)|
|5.||||R(y)|
|6.||||R(z)|

</div>

* $T_4$ will suffer from starvation beacuse it require lock.

### Deadlock

<div align="center">

||$T_1$|$T_2$|
|---|----|----|
|1.|Lock-x(x)||
|2.|W(x)||
|3.||Lock-x(y)|
|4.||W(y)|
|5.||Lock-s(x)|
|6.||R(x)|
|7.|Lock-s(y)|.|
|9.|R(y)|.|
||.|.|
||.|.|
||.|.|

</div>

* Both $T_1$ and $T_2$ have exclusive lock of x ad y data item respectively but wants to acquire shared lock on y and x data item respetively for read operation. 
  


