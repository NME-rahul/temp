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
