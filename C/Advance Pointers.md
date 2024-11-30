* Data type of pointers in C is always a unsigned(maybe long or short depends on architecture) pointer.

### int : 4 bytes
### char : 1 byte
### float : 4 byte
### double : 8 byte


      int x = 5; //address: 100
      float *p = &x; //address: 200
      printf("%d", *200);

* if i know the pointer address and i want to derefence the value at address will it do?
  * no, because compiler dont whether the address is of float, int, char or any other data type so it will not able to undesrstand upto how what address we have data stores in x. this infortation is given by the data type of pointer and 200 have no such type of information.

* will storing of address of integer type in flaot type pointer work?
  * Yes, because address are of same size and any data type pointer can store any data type's address but it will produce worng value because after applying drefrencing pointer the compiler return value in addres equal to 8yte which is equal to float that is also the type of pointer.
      
