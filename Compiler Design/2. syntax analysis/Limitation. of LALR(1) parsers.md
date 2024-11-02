# LALR(1)

## Limitations of LALR(1) parsers

### 1. Handling of Ambiguous Grammars
LALR(1) can not direclty parse the ambiguous grammar and requires grammar modification by specifing precendence and associativity.
  * Arithmetic expressions without clearly defined operator precedence.
  * ```If-else``` statement wihout scoping.

### 2. Limitations in Lookahead
LALR(1) parsers relies only of lookahead for reducing, that limit their ability gain more context.

### 3. Shift-Reduce and Reduce-Reduce conflict

**Reduce-Reduce**: when the final state have multiple production rules with common look-ahead's then parser can not decide which production has to reduce.
**Shift-Reduce**: When the any state have final LR(1) items and a shift move with coomon lookahed then also parser can not decide whether to shift or reduce.

