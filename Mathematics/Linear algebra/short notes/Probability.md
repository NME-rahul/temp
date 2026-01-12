# Probability

### Axioms

1. $P(A) \geq 0$
2. $P(S) = 1$
3. if $A \cap B = \phi$ then $P(A \cup B) = P(A) + P(B)$

### Inclusion And Exclusion principle

1. $P(A \cup B) = P(A) + P(B) - P(A \cap B)$
2. $P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - p(B \cap c) + P(A \cap B \cap C)$

## Conditional Probability.md
* Probabilty of event $A$ given event $B$
* Probabilty of happening an event given some condition.

Baye's theorem: 

$$P(A | B) = \frac{ P(A \cap B) } {P(B)}$$


### Axioms
1. $P(A | B) \geq 0$
2. $P(S | B) = 1$
3. $P(A_1 \cup A_2 | B) = P(A_1 | B) + P(A_2 | B)$ Where $A_1, A_2$ are mutually exclusive and exhaustive and $A_1, A_2$ are on $B$
   * Marginalization : $B = B \cap 1 = B \cap S = B \cap (A_1 \cup A_2) = ( B \cap A_1 ) \cup ( B \cap A_2 )$, this can be extended for $n$ variables.
     <div align="center">
       <img width="380" height="190" alt="image" src="https://github.com/user-attachments/assets/97a9e4d9-5622-4105-bec3-b45babb4055b" />
     </div> 

**Rules:**

* $P(A \cap B) = P(A).P(B | A) = P(B \cap A)$
* $P(A \cap B) = P(B).P(A | B)$
* $P(A \cap B \cap C) = P(A).P(B | A).P(C | A \cap B)$ --> Factorization or chain rule

---

<img width="1211" height="693" alt="image" src="https://github.com/user-attachments/assets/63a46ca6-d7a0-42cb-8961-8bb43b1f63a2" />



# Random Variable

* It is a function that maps sample space on real line.

$$f:2^{\Omega} \rightarrow [0,1]$$
