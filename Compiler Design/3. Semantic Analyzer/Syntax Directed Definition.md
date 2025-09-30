# Syntax-Directed Definition

* A syntax-directed definition is a context-free grammar with attributes and semantic rules to evaluate the attributes.
  * Attributes may be of any type: numbers, strings, pointers to structure.
  * Attributes are associated with nodes in the parse tree, and each occurance of a grammar symbol is associated with grammar rules.

* Attribute grammars are SDDs with no side effects, meaning it does not affect the grmmmar rules or power of accepting language it just help to track context-seneitve information via attributes.

* Every symbol $X \in V$ is asscociated with a set of atttributes(eg. X.a and X.b)

<div align="ceneter"><img width="296" height="133" alt="Screenshot 2025-09-30 at 3 55 43 PM" src="https://github.com/user-attachments/assets/3002faa1-6892-4c84-a5f1-b8ff769c4c93" />
<img width="453" height="177" alt="Screenshot 2025-09-30 at 3 56 17 PM" src="https://github.com/user-attachments/assets/4abd934b-bcf6-4ba4-a88e-f39c1bf96bf7" />
</div> 

* Start symbol cannot have inherited aattribtes.
  * Why? strart symbol have no parent and siblings so it can not bring any information them to itself.

* Terminals can have only syntheised attributes and no inherited attributes.
  * Why? Terminals are the the direct tokens from the inut string, and terminals can not depend on the information how tokens are interpreted that is supplied by the parent or may be sibling.
