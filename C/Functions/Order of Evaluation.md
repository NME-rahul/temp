# Order of Evaluation

* In C, Order of evaulation functions is not specified, it is completely compiler dependent.


1. **Function arguments**: How function will evaluate given as arguments is not specified.

       printf(" %d , %d ", f1(), f2());

* There is no fixed rule which function will be evaluate first.

2. **Function as operands**: Expression are generally evaluated from left-to-right but there is no fixed rule, the rule in generally defined the order of subexrpression to be evalauted based on the operator's precedence,

       int x =  a - b * c;
   
* we're defining only the  order of subexppression `a-(b*c)` so $b*c$ will be evaluated first but which will be read firt $b$ or $c$ this is not defined, smiliarily

      int x = f1() - f2() * f3()

* Now we haved defined that subexpression `f2() * f3()` will be evalauted first but which function in subexpression, `f2()` or `f3()`? Yes, it is not defined here.

---

<img width="884" height="461" alt="image" src="https://github.com/user-attachments/assets/06359afc-b425-4ea2-bbe9-65383b1d9e13" />
<img width="8847" height="496" alt="image" src="https://github.com/user-attachments/assets/5f719e3b-92f1-4178-8af4-7e2c49e80b69" />

