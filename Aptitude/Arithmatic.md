# Divisibility Rules

* For $2$ if last digit is divisible by 2 then it is divisble by 2 or all even numbers are divisible by 2, but why?
  * See any numbers $abc$ can be written as $a * 10^2 + b * 10 + c$
  * BY definition we already know that every even numbers is divisble by $2$, $10$ is divisible by $2$ so every number( $a * 10^2$, $b*10$) is divisble by $2$, we only need to care about $c$ if $c$ is divisble by $2$ then $abc$ is divisble by $2$.
 
* For $3$ if sum of the digits is divisble by $3$ then number is divisble by $3$.
  * Take the same example $abcd$, this can be written as $a * 10^3 + b * 10^2 + c * 10 + d$, Take mod of $(a * 10^3 + b * 10^2 + c * 10 + d) % 3$ if $=0$ then divisble otherwise not
  * $(a * (999 + 1)) % 3 + (b * (99 + 1)) % 3 + (c * (9 + 1)) % 3 + d % 3$
  * $(a * 1 )% 3 + (b * 1)% 3 + (c * 1) % 3 + d % 3$
  * $(a + b + c + d) % 3$
  * The same proof is applicable for $9$ and both have same divisbility rule


Source: https://brilliant.org/wiki/proof-of-divisibility-rules/
