# Sequence point

* A sequence point defines point where side effects of previous evaluation is guranteed.
* `;` semicolon is also called sequence point.
  * x = a++; after the semicolon a will increase or we side effect will take place sequence point.
<div></div>

    int a = 1;
    int y = a++ + a;

Here After + opeartor we don't know the value of $a$ We(compiler) don't whether it is incremented(i.e. a = 2) or still waiting to be incremented(i.e $a$ is $2$) because `+` is not a sequence point. BUt if there is a sequence point between them like `&&` then it will work.

* So xpression shows undefined behaviour if value is modfied multiple time before sequence point or it is compiler dependent what value will they reflect.

Another example, 

    int a = 1;
    int y = a + fun(&a);
Here $a$ is modified(assume fun() modifies input) so we have undefined behaviour.

    int a = 1;
    int y = a + fun(a);

Here $a$ is not modified so we do not have undefined behaviour, but order of evaluation is still not defined here, stil we will not get any unefined behaviour and can evlauate $fun(x)$ first or $x$ first.

---

`;`, `if()`, `while()`, `switch()`, `?:`, `||`, `$$`, `for()` are sequence points

