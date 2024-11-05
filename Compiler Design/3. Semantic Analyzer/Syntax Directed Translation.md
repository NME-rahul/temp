# Semantic Analyzer

## Syntax-Directed Definition

A _Syntax-directed_ defnition is a context-free grammar together with attributes and rule.

### Inherited an Synthesized attributes

1. **Inherited attributes**: An attribute of non-terminal is called Inherited if it is inherited from it's parent or sibling or both.
<div align="center">
  A -> BC
  
  if B's inherited attribute will be dependent on A(parent) and C(right sibling).
  
  B has no left sibling
</div>

  $$E_p \rightarrow E \cdot T$$ { $$E_P = E.val \cdot T.val; T.val = E_p.val$$ }




2. **Synthesized attributes**: An attribute of non-terminal is called Synthesized if it is inherited from it's childeren.
<div align="center">
  A -> BC
  
  if A's inherited attribute will be dependent on B(childeren of A) and C(childeren of A).

</div>

$$E \rightarrow E + T;$$ { $$E.val = E.val + T.val$$ }

  

## SDT type

|S.no.|S-attributed SDT|L-attributed SDT|
|---|---|---|
|1.|SDT uses only synthesized attribute|Uses both synthesized and Inherited attribute but Each inherited attribute is restricted to inherit either from parent or left sibling. <br><br>eg. $A -> XYZ$ {Y.s = A.s, Y.s = X.s, Y.s = Z.s}|
|2.|Sementic actions are placed at right end of production.<br><br> eg. $A->BCC$ { }<br><br> Also called postfix SDT.|Sementic action are placed anywhere on RHS <br><br> A -> { } BC <br>A -> D { } E <br>A -> FG { }|
|3.|Attributes are evaluated during bottom-up parsing.|Attributes are evaluated by traversing parse tree depth first, left to right.|


* If SDT is S-attribute then it is definitely L-attributed because L-attributed SDT uses S-attribute SDT's definition also.
