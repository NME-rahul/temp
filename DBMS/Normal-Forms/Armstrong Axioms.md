# Armstrong Axioms

## Transitive dependency

$$A \rightarrow B$$

$$B \rightarrow C$$

<div align="center">
  
  then $$A \rightarrow C$$
</div>

* IF $A$ is prime-attribute and $C$ is prime-attribute then it is not transitive dependency.
* Here If $A$ is candidate-key and $C$ is prime-attribute attribute then it is not transitive dependecy because we can derive $C$ without $B$

<div align="center">

 $prime-attribute \rightarrow prime-attributes$
 
 Relation $R$ is in $3NF$

 $nonPrime-attribute \rightarrow nonPrime-attributes$

 Relation $R$ is in not $3NF$
</div>

* Because a candidate key can derive non-Prime and non-prime is deriving other non-prime that is transitive functional dependency.
