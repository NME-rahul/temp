# Pumping Lemma

* According to Pumping Lemma, If any FA has $n$ states and sting accepted by FA is $>=n$ then $\exists$ a loop in FA that is accessed while accepting that string.
* If L is infinte regular(because finte languages are trivially regular) language, then we can split the string $w \in L$ as $xyz$ such that,
1. $|y| >= 1$
2. $|xy| >= p$
3. $w = xy^iz\in L;$  $\forall_{i >= 0}$

* $|y| >= 1$ y is the content of loop, it necessary that $y$ is greater then equal to because taking it 0 meaning we are not accesing loop.
* $|xy| >= p$ , P is pumping length and while taking string $w$ from $L$ it is necessary that you must take a string that have atleast one symbol of loop.

* can $|x| = 0$ ? Yes, for eg. $(a + b)^*$ take, $w = a$
  * then here $|x| = 0$ and $a^i \in L$; $\forall_{i>=0}$
 
* Can $|z| = 0$?, Yes
