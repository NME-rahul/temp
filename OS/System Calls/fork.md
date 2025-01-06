#  fork()

Fork system call is used for creating a new process, which is called child process. Which runs concurrently(with the help of kernel-level threads) with the process that makes fork() call.


<div align="center">
 <img width="1129" alt="Screenshot 2025-01-06 at 4 18 02 PM" src="https://github.com/user-attachments/assets/baebb8c4-8ccd-4473-abb6-974f6007b314" />
</div>

* It takes no parameters and returns an integer value.
  * Negative Value: Creation of a child process was unsuccessful.
  * zero: returned to the newly created process.
  * Positive value: it is processID of newly created process and it is returned to the parent or caller.

* whenever the child process is created it does not start executing program from start but starts from the next instruction where it is created.

When a process is forked the OS makes exact clone of the forked process, and child process get a different physical address sapce in MM but their virtual address space remains same. in some implementation, initialy process can have same physical address space but as soon as any thread tries to modifies the content they cloned to differnet physical address space, still their virtual address space remain same.

process creaed by the fork() are executed concurrently by the help of threads, their is no particular what thread will run first child or parent.

