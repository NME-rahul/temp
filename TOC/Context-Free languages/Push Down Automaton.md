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

A PDA is deterministc PDA IFF following 2 conditions satisfy:

**a**. $\forall_{q \in Q}$ & $\forall_{z \in \Gamma}$ if

$\delta(q, \epsilon, z)$ is non-empty then <br>
$\delta(q, a, z)$ must be empty $\forall_{a \in {\scriptstyle \sum}}$<br>
For any state and stack symbol if there exist NULL move then there must not exist TRUE move and if there exist True move then there must not exist NULL move.

**b**. There must be unique move for each transition
   
### 2. Non-deterministic Push down automata

$\delta : Q \times ( {\scriptstyle \sum} \cap \epsilon ) \times \Gamma \rightarrow$ subset of $(Q \times \Gamma^*)$
