# C Peprocessor

1. File inclusion (#inlude)
2. Macro (#define)
3. Pragma (#pragma)

### 2. Macros

    #include<stdio.h>
    #define MACRO_TEMPLATE MACRO_DEFINITION;

Before compilation macrotemplate will be replaced by macro definition. It is a symbolic constant(no memory will be allocated for it) and can't change during program execution.

    #include<stdio.h>
    #define PRINT printf("Helllo");

    int main(int argc, char **argv){
      PRINT;
      return 0;
    }
**Advantages**

1. Program editing and typing becomes easy.


### MACRO as a function

      #include<stdio.h>
      #define SUM(x, y) (x)*y;
      #define PRINT(x) printf("%d ", x);
      int x = 10;

      int main(int argc, char **argv){
        static int x = 10, y = 9.9;
        x = x/SUM(x+2, y) // (x+2)*y
        PRINT(x)
        return 0;
      }

  **Advantages**
1. Reduce typing
2. Save time becuase we paste the macrosfunction definition but in normal function we transfer th econtrol to function.
