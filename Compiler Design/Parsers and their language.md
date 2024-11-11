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
* Bottom-up parser(Left-to-right scanning, Rightmost derivation in reverse with 0 lookahead).
* Language Acceepted: can parse context-free grammars that not require lookahead to make decisions. These grammars have fewer ambiguities and are simpler than those handled by more complex LR parsers.
* Grammar Restriction: can handle grammar with no lookahead, which limits the type of language constructs it can hadle.

### SLR(1) parse (simple LR)

* Bottom-up parser with 1 token of lookahead.
* LAnguage accepted: can hadle a broader range of context-free languages compared to LR(0). It use a single token of lookahead to resolve conflicts that LR(0) cannot.
* Grammar restriction: Grammar must be SLR(1) compatible, which mean it can handle conflicts using lookahead based on the follow sets of non-terminals.

### LR(1)
* Bottom-up parser with 1 token of lookahead.
* Language accepted: can parse almost any DCFG. it is more powerful than SLR(1) and can handle grammars with more complex constructs and fewer ambiguities.
* Grammarrestriction: Handles all grammars that LR(1) compatible, which may involve more states due to indvidual lookahead token for each production.
* A language with more intricate nesting or lookahead dependcies, like considition expression ```if-else``` constructs.

### LALR(1)
* Bottom-up parser with 1 token of lookahead.
* Language accepted: acceptes context-free languages that are a compromise between SLR(1) and LR(1). LAALR(1) combines the states of LR(1) parser to reduce the number of states while reatining most of parsing pwoer of LR(1).
* Grammar restriction: Less pwoerfull than LR(1) but more efficient, as it reduces the size of the parsing table.

<div align="center">
 
|Parser Type|	Languages Accepted|	Automaton Used|
|---|---|---|
|LL(1)|	Simple context-free languages|	Predictive PDA (top-down)|
|LR(0)|	Subset of context-free languages|	Deterministic PDA (bottom-up)|
|SLR(1)|	Broader context-free languages|	Deterministic PDA (with follow sets)|
|LR(1)|	Most deterministic context-free|	Deterministic PDA (with lookahead)|
|LALR(1)|	Practical subset of context-free|	Deterministic PDA (merged states)|
</div>
