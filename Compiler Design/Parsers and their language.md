# Parsers

* Any parser have 4 things
  * Stack
  * Symbol table
  * Algorithm
  * Deterministic Push Down automata

# Parsers and lnaguage accepted by them

### LL(1) Parser
* Top-down parser(left-to-right scanning, leftmostt derivation with 1 tokeen lookahead).
* Language Accepted: DDeterministic context-free language. Thes language must non-left recursuve and non-ambiguous.
* Grammar must be LL(1) compatible, meaning no left recursion, no common prefix and no ambiguity
* First and Follow set must not overlap for any production.

### LR(0)
* Bottom-up parser(Left-to-right scanning, Rightmost derivation in reverse with 0 lookahead)
