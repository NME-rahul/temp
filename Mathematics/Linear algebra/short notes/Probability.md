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


## Distributions

### 1. Discrete uniform R.V.

* It states that each outcome of experiment have same probbility, i.e. if an experiment have n outcomes then probability of each outcomes will be $1/n$.

$$P(x) = \frac{1}{b - a + 1} \\\ or \\\ \frac{1}{n}$$

* Mean : $\frac{a + b}{2}$
* Variance: $\frac{n^2 - 1}{12}$


### 1. Continuous uniform R.V.

<div align="center">
  <img width="603" height="173" alt="image" src="https://github.com/user-attachments/assets/e51dbe5b-361d-4114-b9e8-442c55cadbd3" />
  <img width="467" height="232" alt="image" src="https://github.com/user-attachments/assets/f074b1e2-37bf-464f-9d0c-79ee94ad86c1" />
</div>

* Mean : $\frac{(a+b)}{2}$
* Variance: $\frac{(b-a)^2}{12}$
