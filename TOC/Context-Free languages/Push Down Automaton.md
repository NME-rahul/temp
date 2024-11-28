# Push Down Automatoa

It has 7 tuples

$$ M = (Q, \Gamma, F, \delta, q_0, {\scriptstyle \sum}, Z_0)$$

* $Q$ : Finite Non-empty set of states.
* $\Gamma$ : Finite Set of stack symbols.
* $F$ : Finite set of final states.(can be empty)
* $\delta$ : transition rules; $\delta: Q \times ( { \scriptstyle \sum } \cap \epsilon) \rightarrow  Q \times  \Gamma^*$
* $q_0$ : initial state
* $Z_0$ : initial stack symbol; $Z_0 \in \Gamma$
* $\sum$ : Non-empty finite set of input symbols
---

* $\delta: Q \times \Gamma \times {\scriptstyle \sum} \rightarrow Q \times \Gamma^*$ ---> True Move
* $\delta: Q \times \Gamma \times \epsilon \rightarrow Q \times \Gamma^*$ ---> NULL move


### 1. Deterministic Push Down automata

Dead configurtaion is allowed in DPDA. DPDA is a partial function.

A PDA is deterministc PDA IFF following 2 conditions satisfy:

**a**. $\forall_{q \in Q}$ & $\forall_{z \in \Gamma}$ if

$\delta(q, \epsilon, z)$ is non-empty then <br>
$\delta(q, a, z)$ must be empty $\forall_{a \in {\scriptstyle \sum}}$<br>
For any state and stack symbol if there exist NULL move then there must not exist TRUE move and if there exist True move then there must not exist NULL move.

**b**. There must be unique move for each transition
   
### 2. Non-deterministic Push down automata

PDA is a total function that means it follows all the rules of a function.

<div align="center">
   
$\delta : Q \times ( {\scriptstyle \sum} \cap \epsilon ) \times \Gamma \rightarrow$ subset of $(Q \times \Gamma^*)$
   <br>or<br>
$\delta : Q \times ( {\scriptstyle \sum} \cap \epsilon ) \times \Gamma \rightarrow 2^{(Q \times \Gamma)}$
</div>

---
#### Acceptence condition
1. Accept by final state: starting from initial state after reading entire string PDA is at one of final state then string is accepted.
2. Accept by NULL : staring from initial state after reading entire string stack is empty(not even starting symbol of z) then string is accpeted.

---

* By default PDA means NDPDA, and DPDA is a special case of NDPDA.
* Every DPDA is NDPDA but opposite is not True.
* NDPDA is more powerful then DPDA, that means NDPDA can accept larger class of language then DPDA.
* Every DPDA has equivalanet NDPDA but opposite is not True.
* A language is CFL iff there exist a NDPDA.


