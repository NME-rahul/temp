# Semantic Analyzer

## Syntax-Directed Definition

A _Syntax-directed_ defnition is a context-free grammar together with attributes and rule. The syntax-directed translation is guided by the context free grammars.

If X is symbol and ```a``` is one of its attribute then we write X.a to denote the value of ```a```  at a partcular parse-tree node. Attributes may be of any kind: numbers, type, table, references, or strings.

### Inherited an Synthesized attributes

1. **Inherited attributes**: An attribute of non-terminal B is called Inherited if it is defined only in terms of it's parent or sibling or from itself.
<div align="center">
  A -> BC
  
  if B's attribute defined by A(parent) and C(right sibling).
  
  B has no left sibling
</div>

  $$E_p \rightarrow E \cdot T$$ { $$E_P = E.val \cdot T.val; T.val = E_p.val$$ }




2. **Synthesized attributes**: An attribute of non-terminal N is called Synthesized if it is defined by it's childeren or itseld.
<div align="center">
  A -> BC
  
  if A's attributes are defined by B(childeren of A) or C(childeren of A).

</div>

$$E \rightarrow E + T;$$ { $$E.val = E.val + T.val$$ }

  

## SDT type

|S.no.|S-attributed SDT|L-attributed SDT|
|---|---|---|
|1.|SDT uses only synthesized attribute|Uses both synthesized and Inherited attribute but Each inherited attribute is restricted to inherit either from parent or left sibling. <br><br>eg. $A -> XYZ$ {Y.s = A.s, Y.s = X.s, Y.s = Z.s}|
|2.|Sementic actions are placed at right end of production.<br><br> eg. $A->BCC$ { }<br><br> Also called postfix SDT.|Sementic action are placed anywhere on RHS <br><br> A -> { } BC <br>A -> D { } E <br>A -> FG { }|
|3.|Attributes are evaluated during bottom-up parsing.|Attributes are evaluated by traversing parse tree depth first, left to right.|


* If SDT is S-attribute then it is definitely L-attributed because L-attributed SDT uses S-attribute SDT's definition also.
