# Linear Discriminant Analysis(LDA)

* It finds the projection to a line such that sample from different classes are well seprated.
* PCA finds the most accurate data representation in a linear dimension space by projecting data in the direction of maximum variance. However it is not useful for classification beacuse maximum variance can lead to unseprable data.

<p align="center>
  <img src="" height="" width="">
</p>

* $|\mu^{\sim}_2 - \mu^{\sim}_1|$ is a Measure of sepration.
  * The larger the value of L the better the expected sepration.

<p align="center>
  <img src="" height="" width="">
</p>

* but it is not always correct because larger $|\mu^{\sim}_2 - \mu^{\sim}_1|$ leads to poor sepration of data.
* Suppose we have two classes and a d dimensional samples $x1, x2, ..., xn.$
  * where $n1$ samples are coming from class-1 (C1).
  * and $n2$ samples are coming from class-2 (C2).

* Now if $xi$ be a data point then its projection on the line will be given by unit vector V as $V^T.x_i$.
* Let $\mu_1$ and $\mu_2$ be the means(centroid) of class C1 and C2 respectively before projection.
* If $\mu^{\sim}_1$ denote the centroid of samples of class C1 after projection then,
  
  $$\mu^{\sim}_1 = \frac{1}{n}\sum{V^T.x_i} = V^T(\frac{1}{n}\sum x_i) = V^T.\mu_1$$

similarily,

  $$\mu^{\sim}_2 = \frac{1}{n}\sum{V^T.x_i} = V^T(\frac{1}{n}\sum x_i) = V^T.\mu_2$$

* In LDA, we need normalize $|\mu_2^{\sim} - \mu_1^{\sim}|$ by variance/scatter.
* Let $y_i = V^T.x_i$ a the projection sample.
  * then,
    * scatter for sample of class C1 is
      $$S_1^{\sim} = \sum_{y_i \in c_1}[y_i - \mu_1^{\sim}]^2$$
    * similarily,
      $$S_2^{\sim} = \sum_{y_i \in c_2}[y_i - \mu_2^{\sim}]^2$$

* Thus, we need to project our data onto a line having direction V which maximizes.
  $$J(V) = \frac{(\mu_1^{\sim\} - \mu_2^{\sim\})^2}{S_1^{\sim\ 2} + S_2^{\sim\ 2}}$$

* If we find V which make $J(V)$ large, we are guarented that te classes are well seprated.
  $$J(V) = \frac{(\mu_1^{\sim\} - \mu_2^{\sim\})^2}{S_1^{\sim\ 2} + S_2^{\sim\ 2}}$$

* Define the seprate class scatter matrix S1 and S2 of classes C1 and C2.
