# Sizeof Operatror

* return  the size of oeprand.
* It doesn't evlauate any expression written inside,  `sizeof(++i);` will not increment the value of i, but why? because sizeof operator is evalaute at compile time and 'i' must be evaluated at run-time.
* compiler replace(to which it evaluate) the sizeof operator with a constant value on compilation phase, but in case of variable size array it evlauates at run-time.
