# Runtime Environment

### Symbol Table

* Symbol table, though not part of code generateed by the compiler but helps in compilation process.
* Phase like lexical analysis and syntax analysis produces the symbol while other phases use it's content.
* Depending upon the scope rules of the language symbol table need to e orgnaized in various different manners.
* Data structure commonly used fr symbol tables are linear table, ordered list, tree, hash table etc.

## What is Runtime Environment?

a. Three main segment of a program
  * code
  * Static and global variables
  * Local variables and arguments

b. Memory is required for each of these entities
  * Generate Code: Text for procedures and programs.
  * Data Objects:
    * Global variables/constants: Space known at compile time.
    * Local variables: space known at compile time.
    * **Dynamically created variables:** Space from heap is allocated in response of memory request.
 * **Stack**: To keep track of preocedures activations.
<p align="center">
 <img height="300px" width="400px" src="https://github.com/user-attachments/assets/115b90a6-f052-4c1a-a429-97e41df3dfbe" />
</p>


## Acitvation record

* An ativation record is contiguous block of storage that manages information required by a single exceution of procedure.
* When you enter a procedure, you allocate an activation record on stack memory and when you exit that procedure, you de-allocate it.
* Basically whenever a function cal occures then a new activation record is created.

**Typical activation record contains**
1. Parameter passed to the procedure
2. Bokeeping information(where to return again), including return values.
3. Space for local variables.
4. Space for compiler generated local variables to hold subexpression values.

* Depending upon lamnguages activation record can be created in the stack or heap area. In c language activation records are stores in the runtime-stack.

**Creation of activation record in stack area**
eg, C, Pascal, Java

* As when a procedure is incoked, coreesponding activation record is puhsed onto the stack.
* On return entry is poped out.

Note: Large locall array are created in the stack part of programs/process so it is advised to create large arrays in global area so that it can take place area in static part of process because at each procedure it will create a new array and causes stack overflow conditions.

## Process registers

* Used to store temprory, local variables, global variables and some special information.

1. Program Counter: Points to the statement to be executed next.
2. Stack Pointer: Points to the top of stack.
3. Frame pointer: Points to the current activation record.
4. Argument Pointer: Points to the area of the activation record reserved for arguments.

## Activation record creation 

<div align="center">
 <table>
  <tr><th>At a Call</th><th>At a return</th>
  <tr>
   <td>

   ||Caller|Callee|
   |---|-------|---------|
   |1.|Allocate Baic Frame|Save Callee-saved registers, state|
   |2.|Store parameters|Extend frame for locals|
   |3.|Store return value|Intialize Locals|
   |4.|Save caller-saved registers|Fall through code|
   |5.|Store self frame pointer||
   |6.|Set Frame pointer for child||
   |7.|Jump to child||
   </td>


   <td>

   ||Caller|Callee|
   |---|-------|---------|
   |1.|Copy return value|Store return value|
   |2.|Deallocate basic Frame|Restore callee-saved regsiter state|
   |3.|Restore callee-saved register|unextend frame |
   |4.||Restore parents frame pointer|
   |5.||Jump to return Address|
   </td>
  </tr>
 </table>

 ## Garbage Collection
 
Grabage Collection is the process of memory mangement used in programng and runtime environment to reclaim memory that is no longer in use by the program. This helps prevent memory leaks and improves efficiency of memory usage, ensuing that the program has more active data then the dead data.

<br>

**What is Memory leaks?**

Memory leaks occur when a program does not release memory that is no longer in use, which can lead to inefficient usage, and ultimately applicaion failure due to exhaustion of available memory.
</div>

<br>

**How does grabse collection works?**

It follows these steps:
1. Tracking object referncecs: The garbage collector keeps track of all refernces to ojects in meory to identify which objects are still in use and which are not.
2. Identifying Unrachable objects: It identifes ibjects that are no longer reachable from the program.(eg,. Objects that are no longer refenced by any ariable or other objects.)
3. Reclaiming Memory: The Garbage collector reclaims the memory occupied by thes unreachable objects, making it avialable for future use.

#### Popular Algorithms of automatic garbage collection
1. Reference Counting
2. Mark-and-sweap

* manually garbage collection is done by the programmars using free() function, it is so heptic in larger programs.
