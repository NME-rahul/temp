* Check for BCNF
  * If fails, check for 3NF
    * If fails, check for 2NF
      * If fails, then it's a 1NF

---   

$$\alpha -> \beta$$

|$$\alpha$$|$$\beta$$|dependency|
|---|---|---|  
| P | NP| partial dependency|
| NP| NP|trasitive dependency|
  
#### To be in BCNF

* If alpha is a candidate-key or super-key then it is in BCNF, otherwise not.

#### To be in 3NF

* If alpha is a candidate-key or super-key then it is in BCNF, otherwise not.
* If above condition fails check, whether beta is a prime-key or there is transitive functional dependecny if yes, then relation is not in 3NF.

#### To be in 2NF

* IF there is partial dependency then it is not in 2NF. If beta is partially dependent on alpha then it is a partialy dependency for example, AB is candidate key, and given functionl dependency is A -> D then D is partially dependent on the AB.
* Here, A is the prime-key beacuse it's a part of candidate-key.

---

* The above condition should be followed by the all dependency in the relation.
