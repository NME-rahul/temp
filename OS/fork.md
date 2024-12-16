#  fork()

Fork system call is used for creating a new process, which is called child process. Which runs concurrently(with the help of kernel-level threads) with the process that makes fork() call.

* It takes no parameters and returns an integer value.
  * Negative Value: Creation of a child process was unsuccessful.
  * zero: returned to the newly created process.
  * Positive value: it is processID of newly created process and it is returned to the parent or caller.

* whenever the child process is created it does not start executing program from start but starts from the next instruction where it is created.

When a child is created, it gets a sperate address sapce in RAM and it clones entire address space of parent into it's own address space, but the logical address remains same i.e

process creaed by the fork() are executed concurrently by the help of threads
