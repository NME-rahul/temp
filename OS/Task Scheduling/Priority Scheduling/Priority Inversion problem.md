# Priority Inversion problem

Let there are two processes $P_1$ and $P_2$. $P_1$ has higher prioirty then $P_2$.  $P_1$ and  $P_2$ shares common variabel thus require synchronization.

Considere follwing Scenarios

1. $P_2$ Is runnning is not running in it's Critical Section, $P_1$ does not wants to run in Critical Section, $P_1$ Comes and pre-empts the $P_2$ and takes control over when $P_1$ completes it releases all controls and now  $P_2$ can resume it's execution.
2. $P_2$ Is runnning is running in it's Critical Section, $P_1$ does not wants to run in Critical Section, $P_1$ Comes and pre-empts the $P_2$ and takes control over when $P_1$ completes it releases all controls and now  $P_2$ can resume it's execution.
3. $P_2$ Is runnning is running in it's Critical Section, $P_1$ wants to run in Critical Section, Now $P_1$ has to wait until $P_2$ is running on Critical Section.

* Even $P_1$ has priority then $P_2$, still $P_1$ has to wait.

Suppose an another process $P_3$ comes have higher priority then $P_2$ but not $P_1$ it doesn't shares the Shared Variable but conidere the following scenario

1. $P_2$ Is runnning is running in it's Critical Section, $P_1$ wants to run in Critical Section, $P_3$ comes and preempts the $P_2$ and starts running when $P_3$ completes $P_2$ resume its execution and when $P_2$ completes and $P_1$  can start execution.

We can see that even $P_1$ have higher prioity then $P_2$ and $P_3$ still $P_1$ has to wait for execution, here the priority is inverted. This oftenly happens in Priority Scheduling.
