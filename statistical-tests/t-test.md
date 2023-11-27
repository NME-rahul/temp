# T-test / Student's t-tes

A statistical test used to compares the mea of two different groups. It compares the average values of two data sets and determines if they came from the same population.

* The Student's t-test is used when the sample size is less than  30.

**Example**:

A drug manufacturer tests a new medicine, the drug is given to one group of patients and a placebo to another group. After the drug trial, the members of the placebo group reported an increase in average life expectancy of three years, while the members of the group who are prescribed the new drug reported an increase in average life expectancy of four years.

Initial observation indicates that the drug is working. However, it is also possible that the observation may be due to chance. A t-test can be used to determine if the results are correct and applicable to the entire population.


**There two types of test**

1. One sample t-test
2. Independent two sample t-test
3. uneuqal-variance t-test

## 1. One sample t-test

$$t = \frac{\bar x - \mu}{ \frac{\sigma}{\sqrt{n}} }$$

* μ: mean of the population
* x: mean of the sample
* σ: vaariance of the sample
* n: sample size


## 2. Independent two sample t-test

Paired/Dependent t-test is used when two variable/features are denpendent on each other or have simialar measure units. This method also applies to cases where the samples are related or have matching characteristics, like a comparative analysis involving children, parents, or siblings.

$$t = \frac{\bar x_1 - \bar x_2}{ S^2 \sqrt{ \frac{1}{n_1} + \frac{1}{n_2} }}$$

$$S^2 = \frac{n_1\sigma_1 + n_2\sigma_2}{n_1 + n_2 - 2}$$

* x_1, x_2: mean of sample set1 and set2
* σ1, σ2: variance of sample set1 and set2
* S^2: estimator of common variance
* n1, n2: sampe size of sample set1 and set2
* n_1 + n_2 - 2: degree of freedom.

## 3. uneuqal-variance t-test

$$t = \frac{\bar x_1 - \bar x_2}{ \sqrt{ \frac{\sigma_1}{n_1} + \frac{\sigma_2}{n_2} } }$$

* x_1, x_2: mean of sample set1 and set2
* σ1, σ2: variance of sample set1 and set2
* n1, n2: sampe size of sample set1 and set2

