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
      

## pointer Arithmatic
* p is a pointer

**not allowed**

* p + p
* p * p
* p / p
* p * some integer
* p / some integer

**allowed** (here p is a pointer value stored that is a address)

* p - p  $\rightarrow \frac{p-p}{sizeof(data-type)}$ we can think it like, suppose your home address is $400$ and your friends address is $100$, and every home is of $100$ so how many addresses will be in between that is $\frac{400-100}{100} = \frac{300}{100}$

* p + some integer $\rightarrow p + (integer * sizeof(data-type))$
* p - some integer $\rightarrow p - (integer * sizeof(data-type))$

