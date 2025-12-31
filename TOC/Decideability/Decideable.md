<img width="1108" height="420" alt="image" src="https://github.com/user-attachments/assets/1cf3fbe7-b1b4-40c0-907d-33c81d0428b9" />

<img width="841" height="221" alt="image" src="https://github.com/user-attachments/assets/6fccfbaa-6232-4bfc-8c49-013fbbf97d02" />



## Context-free Language

* Given PDA is if some property is decidable for some property then it is decideable for DPDA.

#### 1. Membership problem of CFL
* Memebership or accpetance $A_{PDA}$
* PRoblem: GIven (PDA/CFG)CFL and string w does $w \in L$
* Decideable

* **Algorithm**
  1.   Given CFG $G$ $\Rightarrow$ Convert in CNF, $G$ $\Rightarrow$ Check all derivation of in length $2|w|-1$
 
* WE know that LR(1) parsers can accept all DCFL so to check $w \in DCFL$ is also decidable.

#### 2. Emptiness Problem of CFL

* Problem: $L = ${$< M >$ | M is PDA; L(M) $= \phi$}
* **Algorithm**
  1.  Just find if we can reach to to any non-terminal symbol from start symbol.
 
* Decideable for given PDA $\rightarrow$ Decidable for DPDA

#### 3. Finitness problem of PDA

* Problem: $L = $ { $< M >$ | M is PDA and L(M) is finite}
* **Algorithm**
  1.  First remove all useless symbol and unit production and convert in CHomsky-normal form.
  2.  Create a reachability graph
  3.  IF graph has cycle then language is infinite else finite.
 
* Problem is decidable, and if we observe that $L = $ { $< M >$ | M is PDA and L(M) is infinite} is also decidable, exactly same algorithm will work for infinite CFL.


#### Undecidable problem of CFL

1. GIven CFG G1 and G2 if L(G1) $\cap$ L(G2) = $\phi$
2. GIven CFG G1 and G2 if L(G1) = L(G2)
3. GIven CFG G and L(G) = $\sum^*$
4. Given CFG G is ambiguous or given CFG G, L(G) is ambiguous.
