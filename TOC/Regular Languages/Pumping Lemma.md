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

**Note:** The minimum pumping length must be equal to $n$(where is the number of states in FA) when every state have only self loop.

* let $n$ be the number of states in minimal DFA and $n_1$ be the number of states that are the part of any loop, then minimum pumping length will be $n - n_1 - trapState(1)$
* Similary we can say that if $n_1$ be the number states in minimal DFA that are no part of any loop(state itself may have self loop), then minimum pumping length will be equal $n_1 - trapState(1)$
