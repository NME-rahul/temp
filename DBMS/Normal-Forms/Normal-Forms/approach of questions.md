* Check for BCNF
  * If fails, check for 3NF
    * If fails, check for 2NF
      * If fails, check for 1NF

---   

$$\alpha -> \beta$$

|$$\alpha$$|$$\beta$$|dependency|
|---|---|---|  
| P | NP| partial dependency|
| NP| NP|transitive dependency|
  
## To be in BCNF

* it is strictier then 3NF
* There should be no overlapping canidate-key, that means no two candidate-key must have commm attribute.
* If $AB$ and $BC$ are tewo candidate-key's in any relation than it is overlapping candidate-key's because $B$ is a common attribute in them.

NOTE: If there is only one candidate key or candidate-key with single attribute then relation is in BCNF because in both cases we can't have any overlaaping in key's.

* $X \rightarrow Y$
  * X must be a super-key

## To be in 3NF 
* 3NF only does not allow particular type of transitive dependency that is $X \rightarrow Y$ where $X$ and $Y$
  
$$X \rightarrow Y$$

* what should happen?
  * X is super-key or Y is prime

* what should not happen?
  * X is non-superkey and Y is non-prime

* If There is a transitive functional dependecny, then relation is not in 3NF.
* for 3NF A relation is transitvely dependent iff of non-prime attribute derives other non-prime.

$$Candidate-key$$ <br>$$(non-prime) \rightarrow (non-prime)$$

* let in relation $R(A, B, C, D)$ $AB$ is candidate key then

$$AB \rightarrow C$$  <br> $$C \rightarrow D$$

is a partial dependency.

* because candidate-key can derive any of the attribute and if any non-prime attribute derives a non-prime attribute then it becomes transitive dependcy.
* If D is prime-attribute then it is not a transitive dependency because it becomes trivial functional dependency.

what if C is prime and D is non-prime? then also it is allowed.

## To be in 2NF

* IF there is partial dependency then it is not in 2NF. If beta is partially dependent on alpha then it is a partialy dependency for example, AB is candidate key, and given functionl dependency is A -> D then D is partially dependent on the AB.
* Rule: No non-prime attribute must not partially(proper subset) dependent on candidate-key.

---

* The above condition should be followed by the all dependency in the relation.
