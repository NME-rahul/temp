# Deadlock Prevention

This Stratergy invloves designing a system that violates one of four necssary conditions required for occurance of deadlock.

## 1. Mutual Exclusion
* To violate this condition, all the system resources must be such that they can be used in a sharable mode.
* In a system, there are always some resources which mutally exclusive by nature.
* So, this condition can not be violated.

## 2. Hold and wait
* This can be violated in the following ways-

### Appraoch-1

* A Process has to first request for all the resources it requires for execution,
* once it has acquired all the resources, only then it can start its execution.
* This appraoch ensres that the process does not hold some resources and wait for other resources.

**Drawbacks**

* It is less efficient.
* It is not implementable since it is not possible to predict in advance which resources will be required during execution.

### Appraoch-2

* A process is allowed to acquire the resources it desires at the current moment.
* After acquiring the resources, it start its execution.
* Now before making any new request, it has to complsuorily release all the resourcess that it holds currently.
* This appraoch is efficient and implementable.

### Appraoch-3

* A timer is set after the prcess acquires any resource..
* After the timer expires, a process has to compulsorily release the resource.

## 3. No-preemption

* This condition can be violated by forceful preemption.
* Consider a process is holding some resources and requesting other resources that can not be immidialtly allocated to it.
* Then, by forcefully preempting the current held resources, the condition can be violated.
* A process is allowed to forcefully preempt the reosurces posssessed by some other process only if-
  * It is a high prriority process or a system process.
  * The victim process is in the waiting state.


## 4. Circular Wait
* not Allows the the process to wait for resources in cyclic manner.

### Approach 1
* A natural number is assigned to every resource.
* Each process is allowed to request for the resources either in only increasng or only decreasing order of the reources number.
* In case increasing order is followed, if a process requires a lesser number number, then it must release all the resources having larger number and  vice versa.
* This approach is most practical approach and implementable.
* However, this approach may cause starvation but will never lead to deadlock.



