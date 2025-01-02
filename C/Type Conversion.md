
<div align="center">
  <img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/Implicit-Type-Conversion-in-c.png">
</div>

## Implicit type conversion
* It is also called type promotion because it prmotes all the variable's type to largest possible data type in the expression.
* The variable in above(in hierarchy as shown in diagram) data type can be typecaseted implictly in the data type that are low in hierarachy by the compiler this is done because compiler takes care that no information should be loosed while type casting.
* Whenever we we perform operation between two different data type of operands then compiler will automatically type cast the operand that has smaller data type on larger size data type.

      int x = 3;
      float y = 5;
      then during x + y operation x will be typecaseted to float(not the actual variable) that takes greate size.

---

    unsigned int x = -2; // the compiler will store 2's complement of -2 and will treat that as usigned integer
    signed int y = 3;
    if(x > y) //this condition will evaluates to TRUE because -2 will be stored in 2s complement form that is (1110)2=14 and it is larger then 5


---

assume the `int` size is 1 Byte and 

unsigned range: $2^{n} - 1$
2's complement range: $-2^{n-1}$  to $2^{n-1} -1$


    unsigned int x = -128; //according the range we can store -128 in 1 byte but in but unsigned can store upto 255; will store as (10000000)2
    signed int y = 127; //
    if(x > y) //this condition will evaluates to TRUE because -2 will be stored in 2s complement form that is (10000000)2=+128


## Explicit conversion
* In this type of conversion programmer can convert the data type of any variable in their choice.


      (type)expression

* uncareful conversion can result in data loss because during converting larger data type in smaller can make truncate the data.

