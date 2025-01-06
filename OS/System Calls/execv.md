# exec

execv() replacess the current running process with the new process. It is used to run C program with another executable/batch progrm. it is defined under the `unistd.h` header file.

### It is a fmaily for functions: 
1. **[execv](https://www.qnx.com/developers/docs/6.5.0SP1.update/com.qnx.doc.neutrino_lib_ref/e/execv.html)**: It replacess the current say `a.c` program with explicitly mentioned program say `b.c` and overwrite the memory of `a.c` with itself and it never returns to the callee program because we overwrite the memory. whatever wrote after `execv` in `a.c` will never execute.
2. **execvp*** : Using this command, the created child process does not have to run the same program as the parent process does. The exec type system calls allow a process to run any program files, which include a binary executable or a shell script .

       execvp (const char *file, char *const argv[]);

file: points to the file name associated with the file being executed. 
argv:  is a null terminated array of character pointers.
Let us see a small example to show how to use execvp() function in C. We will have two .C files , EXEC.c and
