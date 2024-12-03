    int x[5] = {1, 2, 3, 4, 5};

* an array variable is a constant(doesnt change) pointer to first element of array.
* Declaration:
  * x[2] <--> *(x + 2) <---> *(2 + x) <---> 2[x]
  * x + 2; it is an address of third element of array
  * variable x does not have address of itself but itself x is first element. whereas when we declare array of pointer the pointer itself have an address and that contans the address of first of element of array.

* `*x++` Because of precedence, ++ will perform first and  x is constant pointer to an array sp incrementing it will produce an error
*  `(*x)++` it first dereference the pointer and the increment the value ie. 1 because it is post increment.
*  `*++x` similairy will produce an error because of incrementing constant value


    int fun(int *p){
     printf("%d", *++p); //print: 2 why? because now p is not a consant pointer but an normal integer pointer having address of an array and incrementing it by 1 p will point to next address of array
     printf("%d", *p++); //print: 2 why? because it is a post increment so it will increment to next address but take effect after print
   }
   int main(){
     int x[3] = {1, 2, 3};
     printf("%d", *x);     //print: 1
     printf("%d", *++x);  //will produce an error because we're increenting constant variable
     printf("%d", *x++);  //will produce an error because we're increenting constant variable

     fun(x);
   }
