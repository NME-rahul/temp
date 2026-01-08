# CRC
* $R(x) = S(x) + e(x)$

We should choose $G(x)$ such that it can not divide $e(x)$, for example if $e(x) = x^5$ and $G(x) = x^3$ then $G(x)$ can divide $e(x)$ so we can not detect the error because we got remainder as $0$, that's why if error is of order $d$ like $e(x) = x^d + x^{d-1} + ... + 1$ then $G(x)$ must be at least of order $d$.

## Guidelines to Choose $G(x)$
1. It must have at least 2 terms

### To detect all Odd Errors
1. To detect all Odd error $G(x)$ must be factor of $(x + 1)$

### To detect double errors
1. To detect error $e(x)$ having pattern like $e(x) = x^i + x^j$,

   $$e(x) = x^i(1 + x^{j-i})$$
   
3. $G(x)$ must not divide $1 + x^{j-i}$

### To detect all burst error of length b or less $( <=b)$
1. The G(x) must have degree at least $b$ to detect all burst error of degree $<=b$


Note: $G(x)$ are always detemine on the basis of error pattern occur in message
---
eg. Lete we have error with pattern $x^3 + x^2 + 1$ what should be $G(x)$ ?

we have odd number of terms so it must not be the factor of $x+1$. so we can choose $G(x) = x^3 + 1$
