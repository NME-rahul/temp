# Kernel Vs User

* According to a OS developer a computer user is dumbe and has no knowledge of computer, divdation between user and kernel marks the boundary where a normal user can play.
* dividation of kernel space and user space is necessaary to provide security, efficiency and stability.
* Kernel maintains the disk scheduling, process sheduling, IO management, memory management, etc.
* Whereas userspace is provides the service of the user.


* users can get the service of by system calls.

### 
* Mainly there are two types of kernels
  1. Monolithic: In this architecture entire operating system(All service of OS) runns in the kernel space. for example Linux, DOS
  2. Microkernel: Moves as many services as possible out of the kernel into user space. This can cause performace overhead due to increased inter-process communication.
  3. Hybrid: Combines aspect of both, running some services in user space and performance-critical services in kernel space for a balance of speed and stability. exaples Windows NT, macOS.
