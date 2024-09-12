#  Passing parameters


1. Call by value
2. call by reference
3. call by name
4. call by need

### Call-by-Name
* call by Name is a lazy evaluation stratergy where the argument expression is not evaluated when the function called. instead expression is substituted into functions's body and only evaluated when it is actually used.

* No immediate evaluation.
* Repeated evalaution: if the argument is used multiple time within the function, it will be re-evaluated each time.

      void fun(int a, int b){
        a = a + b; // it will put here the expression as; a = 5 + 7/3 + 2;
        b = a * b // b = 5 * 7/3 + 2;
      }
      int main(){
        fun(5, 7/3+2) //it will not evaluated here, it is passed as it is 
        return 0;
      }

### Call be need

* it is the ectension of Call by Name, it is also not evaluate the expression where it is called by when the first it is evaluated it is stored in the cache and reuse whenever in function body the argument is used.

* No immediate evaluation
* No Repeated evalaution


      void fun(int a, int b){
        a = a + b; // it will put here the expression as; a = 5 + 7/3 + 2;
        b = a * b // b = 5 * 4
      }
      int main(){
        fun(5, 7/3+2) //it will not evaluated here, it is passed as it is 
        return 0;
      }



  
  
