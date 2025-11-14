# Wild pointers

* A pointer that declared but not defined.
* Derefrencing this type of variable may cause undefined behaviour.
  * Derefrencing can throw grabage value.
  * Segmentation fault.
 
<div></div>

    int *p 
    printf("%d ", *p); //p is wild pointer
