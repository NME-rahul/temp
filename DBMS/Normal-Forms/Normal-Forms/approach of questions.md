* Check for BCNF
  * If fails, check for 3NF
    * If fails, check for 2NF
      * If fails, check for 1NF
  
# To be in BCNF

If whenever a non-trvial functional dependency $X \rightarrow Y$ in R, then $X$ is super-key.

* it is strictier then 3NF
* There should be no overlapping canidate-key, that means no two candidate-key must have common attribute.
  * If $AB$ and $BC$ are two candidate-key's in any relation than it is overlapping candidate-key's because $B$ is a common attribute in them.
 

* what makes a relation in 3NF but not in BCNF?
  * in $X \rightarrow Y$, $X$ is not super-key but $Y$ is a prime.
 
if we have more then 1 candidate-key then their super-key must have overlapping candidate 

NOTE: If there is only one candidate key or candidate-key with single attribute then relation is in BCNF because in both cases we can't have any overlaaping in key's.

# To be in 3NF 

No non-prime attribute is transtively dependent on any candidate-key. $\exists$ non-superkey $\rightarrow$ prime. remember this definition and any modification could violate condition of 2NF.

**violation of 3NF**
  * non-super key $\rightarrow$ non-prime
  
1. non-primes(non-superkey) $\rightarrow$ non-prime
  * candidate-key can determine any attribute so, candidate-key $\rightarrow$ non-prime $\rightarrow$ non-prime

* is non-prime $\rightarrow$ prime, transitive functional depdnecy?
  * it is not even possible because if any $A$ non-prime attribute derives prime attribute $X$ then it automatically becomes prime attribute because prime attribute is part of some key $XY$ and if any part $X$ of that key is determined by some another attribute $A$ then we can put make $AY$ also a candidate-key so $A$ automatically becomes prime attribute.
 
* prime $\rightarrow$ prime is not transitive functional dependency because it is trivial FD.

2. proper-subset of candidatekey(non-superkey) $\rightarrow$ non-prime
   * it is also violation of 2NF, that's why to be in 3NF it must be in 2NF
  
3. prime + non-prime(not superkey) $\rightarrow$ non-prime


**NOTE:** $X \rightarrow Y$, then $X$ is either super-key or $Y$ is prime attribute.
          Non-superkey $\rightarrow$ proper-subset of key; opposite is not true

# To be in 2NF
Every non-prime attribute is fully dependent on every candidate-key.

**violation of 2NF**
  * proper subset of candidate-key  $\rightarrow$ non-prime

What is the meaning of proper subset?
* It means it should only be the proper subset of any candidate-key not combination of prime of 2 or more candidate-keys and combination of prime and no-prime.

Note: proper subset of candidate-key  $\rightarrow$ non-prime, is cause of partial depnedncy but itself not a partial dependency rather candidate-key $\rightarrow$ non-prime will become partial dependency.


**Partial Dependency that are allowed***
1. super-key $\rightarrow$ non-prime
2. candidate-key $\rightarrow$ non-prime

* if candidate-key is of singleton attribute then it is also in 2NF because then we can not have partial dependency.

---

* The above condition should be followed by the all dependency in the relation.
