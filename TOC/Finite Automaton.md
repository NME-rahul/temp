# Determinstic Finite Automaton

* It is mathematical Function of 5 tuples

$$F(Q, \textstyle \sum, \delta, F, q_0)$$

* $Q$: Finite no-empty set of states.
* $\displaystyle \sum$: Finte non-empty set of input symbols
* $\delta$: Production Rule: $\delta: Q \times \textstyle \sum \rightarrow Q $
* $F$: set of Final states(it can be empty). $F \subseteq Q$
* $q_0$: inital state. $q_0 \in Q$

## Finite Automaton

* If any NFA have $n$ states then it can accept at most string of length $n-1$. if it is accepting string $>=n$ then the FA must a have a loop by the pigeonhole principle.
* if DFA have accepts finite language and have $n$ states then why it can not accept string of length $n-1$?
  * We know, in DFA each state must have outgoing edge for every input symbol, if we create a DFA of $n$ states then where will be the outoging edge's of last state will go? because it can not go to other state otherwise it will make a loop hence making language infinite, so we must use one state for trap so that outgoing going edge of last or any state can go there, hence we remain $n-1$ states and according to piegonhole principle we can accept only string of lengrh $n-2$. [Example Here!](https://gateoverflow.in/376536/classes-test-series-2025-theory-computation-topic-question?show=377234#c377234)
* Arden's Theorem: It works on both NFA and DFA without any conversion.

## Clouser propeties of regular languages
