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


1. Deterministic Push Down automata
2. Non-deterministic Push down automata
