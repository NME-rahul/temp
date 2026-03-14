# New Process Creation in Unix.md

<div align="center">
  <img src="https://i.sstatic.net/5MdOR.png" />
</div>


1. Whenever we hit `./a.out` on the shell, the parent processes(shell) creates an child processes(near identical copy of itself).
2. Then child process executes(replaces itself) provided sources code with `exec()` system call.
3. The parent process wait until child process terminates(replacing itself with provided source code).
