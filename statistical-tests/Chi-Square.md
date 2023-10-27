# Chi-Square test

A chi-square test is used to compare/association two statistical categorical data set.

## Chi-Square Goodness-of-fit test

Chi-Square Goodness-of-fit test  is used to determine whether an observed frequency distribution differs from a theoritical distribution, meas that whether the sample data is consistent with the hypothesized distribution.

**Null hypothesis:** Observed and theoritical value is not different.

**Alternate hypothesis:** Observed and theoritical value is different.

$$ X^2 = \sum{\frac{(Observed - Expeted)^2}{Expected}}$$

$$Expected = \frac{Row Total * Col Total}{GrandTotal}$$


Degree of freddom =  (number of rows - 1)*(number of columns)

Degree of freddom =  (number of categories - 1)


## Chi-Square test of independence

The chi-square test of independence is used to examine whether there is significant association between two categorical variables. It is used to determine whether the varibles are independent or whether there is relationship beween them.

**Null hypothesis:** variables are independent.

**Alternate hypothesis:** variables are not independent.


$$ X^2 = \sum{\frac{(Observed - Expeted)^2}{Expected}}$$

$$Expected = \frac{Row Total * Col Total}{GrandTotal}$$


Degree of freddom =  (number of rows - 1)*(number of columns)

Degree of freddom =  (number of categories - 1)

---

**Example:** procedure is same for both the tests only diference is the conclusion.

|Data|Candidate A|    Candidate B|    Candidate C|
|---|---|---|---|
|Male |       50 |           30     |        20|
|Female|      40 |           50     |        10|

* set Hypothesis.

  **H0** = There is no difference between Male and Female candidates.

  **H1** = There is difference between Male and Female candidates.

* Calculate the row total, coloum total For each and calculate grand total.

|Data|Candidate A|    Candidate B|    Candidate C| Column total|
|---|---|---|---|---|
|Male |       50 |           30|        20|      100|
|Female|      40 |           50|        10|      100|
|Row total|   90 |           80|        30|      Grand total = 200| 


* Calculate expected value for each coloumn.

|Data|Candidate A|    Candidate B|    Candidate C|
|---|---|---|---|
|Male |       $$\frac{100 * 90}{200} = 45$$ |           $$\frac{100 * 80}{200} = 40$$|        $$\frac{100 * 30}{200} = 15$$|
|Female|      $$\frac{100 * 90}{200} = 45$$ |           $$\frac{100 * 80}{200} = 40$$|        $$\frac{100 * 30}{200} = 15$$|

* Calculate chi-square value.
  
|Data|Candidate A|    Candidate B|    Candidate C|
|---|---|---|---|
|Male |       $$\frac{(50 - 45)^2}{45} = 0.55$$ |           $$\frac{(30 - 40)^2}{40} = 2.5$$|        $$\frac{(20 - 15)^2}{15} = 1.67$$|
|Female|      $$\frac{(40 - 45)^2}{45} = 0.55$$ |           $$\frac{(50 - 40)^2}{40} = 2.5$$|        $$frac{(10 - 15)^2}{15} = 1.67$$|

* Calculate sum of chi-square value.

  $$X^2 = 0.55 + 0.55 + 2.55 + 2.55 + 1.67 + 1.67 = 9.54$$

* Calculate degree of freedom.

  $$dof = (2 - 1) * (3 - 1) = 2$$

* Assume LOS(rejection area) as 5%(standard) or we can say 95% as acceptence area and find the value for it from chi-square distribution table. Critical value or we can say chi-square value at 5% rejection is 5.991.

> $$If (X^2_{calulated} < X^2_{crtical}) : accept$$
> $$Else: rject$$
