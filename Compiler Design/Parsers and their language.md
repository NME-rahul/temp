# Parsers

* Any parser have 4 things
  * Stack
  * Symbol table
  * Algorithm
  * Deterministic Push Down automata

# Parsers and lnaguage accepted by them

### LL(1) Parser
* Top-down parser(left-to-right scanning, leftmostt derivation with 1 tokeen lookahead).
* Language Accepted: Subset of context-free language. only those CFLs that can be parsed in a top-down manner.
* Grammar must be LL(1) compatible, meaning no left recursion, no common prefix and no ambiguity
* First and Follow set must not overlap for any production.

### LR(0)
* Bottom-up parser(Left-to-right scanning, Rightmost derivation in reverse with 0 lookahead).
* Language Acceepted: recognizes border range of context-free grammars then LL(1). These grammars have fewer ambiguities.
* Grammar Restriction: can handle grammar with no lookahead, which limits the type of language constructs it can hadle.

### SLR(1) parse (simple LR)

* Bottom-up parser with 1 token of lookahead.
* Language accepted: Subset of LL(1) and LR(0). It use a single token of lookahead to resolve conflicts that LR(0) cannot.
* Grammar restriction: Grammar must be SLR(1) compatible, which mean it can handle conflicts using lookahead based on the follow sets of non-terminals.

### LR(1)
* Bottom-up parser with 1 token of lookahead.
* Language accepted: all DCFLS. it is more powerful than SLR(1) and can handle grammars with more complex constructs and fewer ambiguities.
* Grammarrestriction: Handles all grammars that LR(1) compatible, which may involve more states due to indvidual lookahead token for each production.
* A language with more intricate nesting or lookahead dependcies, like considition expression ```if-else``` constructs.

### LALR(1)
* Bottom-up parser with 1 token of lookahead.
* Language accepted: Subset of LR(1). LAALR(1) combines the states of LR(1) parser to reduce the number of states while reatining most of parsing pwoer of LR(1).
* Grammar restriction: Less pwoerfull than LR(1) but more efficient, as it reduces the size of the parsing table.
* It provides tradeof betwwen efficeincy and language accepted by it. It similar to LR(1) but optimized for table size by merging.

<div align="center">
 
|Parser Type|	Languages Accepted|	Automaton Used|
|---|---|---|
|LL(1)|Subset of context-free language	|	Predictive PDA (top-down)|
|LR(0)|Border subset then LL(1)|	Deterministic PDA (bottom-up)|
|SLR(1)|Subset of LL(1) and LR(0)|	Deterministic PDA (with follow sets)|
|LR(1)|All DCFLS|	Deterministic PDA (with lookahead)|
|LALR(1)|Subset of LR(1)|	Deterministic PDA (merged states)|
</div>

### Important points

Regular set == Regular languages

if grammar is LL(1) then it must be unambiguous, not left recursivem and left factored

$unambiguous \rightarrow non-left-recursive \\\ \land \\\ left-factored$

Regular grammars can anbiguous.

Regular can have a common prefix or left recursion.

so, every regular grammar is not LL(1).

But Every regular language has at least one right linear grammar which is LL(1).

Every DCFL is LR(1) but need not be LL(1)

Every regular language is DCFL.

So, every regular language has LR(1) grammar.

if grammar is LL(1) and not containing epsilon then it is SLR(1).

Every LL(1) does not generate regular language but every LL(1) generated DCFL.

LL(1) always deterministc unambiguous CFB

