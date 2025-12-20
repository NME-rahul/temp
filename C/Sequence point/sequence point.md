# Sequence point

* `;` semicolon is also called sequence point.
  * x = a++; after the semicolon a will increase or we side effect will take place sequence point.
<div></div>

    int a = 1;
    int y = a++ + a;

Here After + opeartor we don't know the value of $a$ We(compiler) don't whether it is incremented(i.e. a = 2) or still waiting to be incremented(i.e $a$ is $2$) `+` is not a sequence point.

* This kind xpression shows undefined behaviour or it is compiler dependent what value will they reflecte.

* Any expression in which same operand is modfied more then one time show this type of undefined behaviour.

Another example, 

    int a = 1;
    int y = a + fun(&a);
Here $a$ is modified(assume fun() modifies input) so we have undefined behaviour.

    int a = 1;
    int y = a + fun(a);

Here $a$ is not modified so we do not have undefined behaviour, but order of evaluation is still not defined here, stil we will not get any unefined behaviour and can evlauate $fun(x)$ first or $x$ first.

---

`;`, `if()`, `while()`, `switch()`, `?:`, `||`, `$$`, `for()` are sequence points

