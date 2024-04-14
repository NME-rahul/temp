# Sleep and Wakeup

## Overview

As we have seen, busy waiting can be wasteful. Processes waiting to enter their critical sections waste processor time checking to see if they can proceed. When process are denied to access to their critical sections the os blocks the process. Two primitive, Sleep and Wakeup calls, are used to implement blocking to ensure multual exclusion.

### How do Sleep and Wakeup work?

* When a process is not permitted to access to it's critical section, it uses a system call knwon as **Sleep**, which causes the process to block. The process will not be scheduled to run agian, utnil another process uses the **Wakeup** system call. In most cases, **Wakeup** is called by a process when it leaves its critical section.
