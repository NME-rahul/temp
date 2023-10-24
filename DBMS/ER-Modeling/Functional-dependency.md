$$\alpha->\beta$$


* If same value of alpha you get different values of beta then functional dependency is incorrect.
* If all values of alpha are different then functional dependency is correct.
* If all values of beta are same then functional dependency is correct.


#### 1
|X|Y|Z|
|---|---|---|
|1|4|2|
|1|5|3|
|1|6|3|
|3|2|2|

which is correct?

- [] XY -> Z && Z -> y

- [x] YZ -> X && Y -> Z

- [] YZ -> X && X -> Z

- [] XZ -> Y && Y -> Z


XZ means composit of X and Z
----

#### 2

|X|Y|Z|
|---|---|---|
|1|2|4|
|3|5|4|
|3|7|2|
|1|4|2|

which is correct?

- [] X -> Y && YZ -> X

- [] Z -> Y && ZX -> Y

- [x] Y -> Z && XY -> Z

- [] X -> Z && YZ -> X
