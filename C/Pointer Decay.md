# Decay of an array variable into pointer variable

* An array variable decays int pointer variale when it is used in the following secnarios.
  * Subscripting: `*(arr + i)` or `a[i]`
  * Passing to function: `fun(arr)` $\rightarrow$ `int fun(int *arr)` or `int fun(int arr[])`
  * Arithmatic: `arr + x`
  * Relational operators: `a == &a[0]` valid
