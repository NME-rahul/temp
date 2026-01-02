
1. Halting problem.
2. Membership Problem.
#### 3. L = { $< M >$ | M is a TM and L(M) $= \sum^*$ }

Proof: This is non-trivial and monotone property so it is undecidable, but what about type of language? For this we have an procedure, lets see is it works or not.

    1. By using dovetailing, run the each M on w for one step then two step then three step and so on,
    2. If any Turing mahchine have complete language on alphabet the it will eventually accept all stings and halt
    3. and Turing machine whose language is not complete will never halt,

* Our procedure is able to identtify every member but not the non-member so it is Turing recognizable but not decideable.
  
---

1. Given DPDA and NFA, deciding Whether both accepting the same language or not, is decidable.
2. Given PDA and NFA, deciding Whether both accepting the same language or not, is undecidable.
