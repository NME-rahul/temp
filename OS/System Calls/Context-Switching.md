# Context Switching
TO achieve multitasking in the system OS needs to shedule mutiple process to CPU, it innvolves saving the context or state of current running process so it can be used to resume the process later and loading the context of new process.
### Processs PCB/ Context of CPU
* Process ID
* Program Counter
* GPR(General Purpose Register)
* List of devices
* Type
* Size
* Priority
* State
* List of files
* I/O status information

* What Happens During Context Switch from process P1 to P2?
  * P1 goes to kernel model and givs up CPU(due to timer interrupt or exit or [Sleep](https://github.com/NME-rahul/temp/blob/main/OS/Process%20Synchronization/Sleep%20and%20Wakeup.md))
  * P2 is another process that is ready to run.
  * P1 Switches to CPU schedular thread.
  * Shedular thread findd runnable process P2 and switches to it.
  * P2 returns from trap to user mode.

 * Process of switching from one process/thread to another
   * Save all register(CPU Context) on kernel stack of old process
   * Update Context structure pointer of old process to this saved context.
   * Switch from old kernel stack to new kernel stack.
   * Restore register state(CPU context) from new kernel stack, and resume new process.
