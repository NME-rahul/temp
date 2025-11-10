# extern keyword

* This kyword tell the compiler that the varible is declared and defined elesewhere and should be linked to current compilation unit.
* Declare variable eleswhere and define at other place in same source code.
* Majorly use for Global declaration.

      #include <stdio.h>
  
      int x = 43;
      int main(int argc, char **argv){
        extern int x;
        {
          printf("%d", x);
        }
        return 0;
      }

      output: 43

---

      #include <stdio.h>
  
      int x = 43;
      int main(int argc, char **argv){
        int x = 10;
        extern int x;
        {
          printf("%d", x);
        }
        return 0;
      }

      output: error: an extern follwed by non-extern

---

      #include <stdio.h>
      int x = 43;
      int main(int argc, char **argv){
        extern int x;
        {
          int x = 10
          printf("%d", x);
        }
        return 0;
      }

      output: 10

---

      #include <stdio.h>
      int x = 43;
      int main(int argc, char **argv){
        extern int x;
        {
          int x = 10;
          {
            printf("%d", x);
          }
          printf(" %d", x);
        }
        return 0;
      }

      output: 10 10

* Declaration of extern with identifier x, if any changes made in block will affect the variable x until new declartion is made for the variable x within same code block.

---

      #include <stdio.h>
      int x = 43;
      int main(int argc, char **argv){
        extern int x;
        {
          int x = 10;
          {
            printf("%d", x);
          }
          int x = 19;
          printf(" %d", x);
        }
        return 0;
      }

      output: error: redefintion of variable x is not possible

---

      #include <stdio.h>
      int x = 43;
      int main(int argc, char **argv){
        extern int x;
        {
          int x = 10;
          {
            printf("%d", x);
          }
          int x = 19;
          {
            printf(" %d", x);
          }
        }
        return 0;
      }

      output: error: redefintion of variable x is not possible

* We can only redefine the the same global varible 1 time again will lead to error;

---

      #include <stdio.h>
      int x = 43;
      int main(int argc, char **argv){
        extern int x;
        {
          int x = 10;
          {
            printf("%d", x);
          }
        }
        printf("%d", x);
        return 0;
      }

      output: 10 43
