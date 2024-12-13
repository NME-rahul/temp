# Mutual Exclusion
No two process must enter in critical section simultaneously.

Check: make an entry of any one process in critical section then try to make entry of one another process if you are able then no mutual exclusion else mutual exclusion satified.

# Progress
If every process get a chance to enter in critical section when it is free then there is Progress.

Check: if no process is in critical section and each process is able to enter(not simultaneously) in critical section then progress is there. We can say there should be no strict alteration in processes to enter in critical section.
if all processes are at entry of critical section then at least process can enter in citical section.

# Bounded waiting
If each and every process get a chance to enter in critical section and no process can bypass rest processes repeatedly then there is bounded waiting.

* IF any process executed the critical section and again able to enter in critical section there is no bounded waiting. Simply, we can say if other process are waiting in loop to enter in critical section then the process that executed critical recently should not by pass the waiting processes.
* There is one curious point that if due to deadlock recently executed process is not able to enter again in critical section then also bounded waiting satified.

* The essential feature of bounded waiting is to ensure no starvation, but is also possible?
  * genrally Yes, but there is a extreme cases that is deadlock, where not able to bypass waited process but still there is starvation.
  * Bounded waiting $\wedge$ no deadlock $\rightarrow$ no starvation
  * Bounded waiting $\wedge$ Progress $\rightarrow$ no staration
 
Check:
1. make an entry of any one process and busy wait rest processes if process that is in critical section comes out and again able to enter in critical section then there is no bouded waiting.
2. If there is only one semaphore is implemented for synchronization then there is no bounded waiting.


# Deadlock
IF every process stuck and show no process then there is a deadlock. If there is no deadlock then there is progress.

Check: try to make semaphore value $s=0$ so that every process stuck at wait() function.
