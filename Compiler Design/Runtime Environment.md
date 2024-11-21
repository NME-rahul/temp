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
* Basically whenever a function call occures then a new activation record is created.

<p align="center">
 <img width="365" alt="Screenshot 2024-11-21 at 11 25 30 AM" src="https://github.com/user-attachments/assets/cb20f660-08d9-4e3c-83f0-a3d5a4098652">
</p>

**Typical activation record contains**
1. Temporary values, such as those created from the evaluation of expressions and those temporaries cannot be held in registers.
2. Local data belonging to called procedure.
3. return address
4. Control link, points to the preceding activation from where current is called.
5. Access link, keeps the extra information to locate the data needed in nested function, for eg, in below program $x$ is defined in preocedure1 but is used in procedure2 and to ensure the correct definition the proceure2 keeps extra information called access link, it helps to look into the nested procedure until it found defnition of undindeined local variables.
   
       def procedure1:
         x = 4;
         def procedure2:
           x = x + 1;
           return x;
         preocdure2()
         return;

* Acees link is only for nested function defnition not for seprate function like below.
  
      def procdure1:
        x = 4;
        preocdure2()
         return;
      def procedure2:
        x = x + 1;
        return x;
         


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

---

Dangling reference: A dangling refernce is pointer or reference that points to a memory address that is already deallocated or released.
