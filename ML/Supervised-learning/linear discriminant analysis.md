# Linear Discriminant Analysis(LDA)

* It is a tool for classification and dimesnionality reduction.
* LDA projects data from a D-dimensional feature space to D' dimesnion space (D > D').
* It maximize the variability between the class and reduce the variability within the class.

* It finds the projection to a line such that sample from different classes are well seprated.

### Assumptions

* It assumes that the data is distributed normally.
* Each of the classes has identical covariance matrices.


## Derivation
<p align="center>
  <img src="" height="" width="">
</p>

* $|\tilde{\mu_2} - \tilde{\mu_1}|$ is a Measure of sepration.
  * The larger the value of measure the better the expected sepration.

<p align="center>
  <img src="" height="" width="">
</p>

* but it is not always correct because larger $|\tilde{\mu_2} - \tilde{\mu_1}|$ may leads to poor sepration of data.
* Suppose we have two classes and a d-dimensional samples $x1, x2, ..., xn.$
  * where $n1$ samples are coming from class-1 (C1).
  * and $n2$ samples are coming from class-2 (C2).

* Now if $xi$ be a data point then its projection on the line will be given by unit vector $V$ as $V^T.x_i$, here $V$ is a vector matrix.
* Let $\mu_1$ and $\mu_2$ be the means(centroid) of class C1 and C2 respectively before projection.
* If $\tilde{\mu_1}$ denote the centroid of samples of class C1 after projection then,
  
  $$\tilde{\mu_1} = \frac{1}{n}\sum{V^T.x_i} = V^T(\frac{1}{n}\sum x_i) = V^T.\mu_1$$

similarily,

  $$\tilde{\mu_2} = \frac{1}{n}\sum{V^T.x_i} = V^T(\frac{1}{n}\sum x_i) = V^T.\mu_2$$

* In LDA, we need normalized $|\mu_2^{\sim} - \mu_1^{\sim}|$ that can be achieve by variance/scatter.
* Let $y_i = V^T.x_i$ a the projection sample.
  * then,
    * scatter for sample of class C1 is
      $$\tilde{S_1^2} = \sum_{y_i \in c_1}[y_i - \mu_1^{\sim}]^2$$
    * similarily,
      $$\tilde{S_2^2} = \sum_{y_i \in c_2}[y_i - \mu_2^{\sim}]^2$$

* Thus, we need to project our data onto a line having direction V which maximizes.
  $$J(V) = \frac{(\tilde{\mu_1} - \tilde{\mu_2})^2}{\tilde{S_1^2} + \tilde{S_2^2}}$$
  * Here, $(\tilde{\mu_1} - \tilde{\mu_2})^2$ is the between class scatter.
  * and, $\tilde{S_1^2} + \tilde{S_2^2}$ is within class scatter scatter.

* If we find V which make $J(V)$ large, we are guarented that te classes are well seprated.
  $$J(V) = \frac{(\tilde{\mu_1} - \tilde{\mu_2})^2}{\tilde{S_1^2} + \tilde{S_2^2}}$$

* Define the seprate class scatter matrix S1 and S2 of classes C1 and C2.
  $$S_1 = \frac{1}{n-1} \sum_{x_i \in c_1} (x_i - \mu_1)^T (x_i - \mu_1)$$
  $$S_2 = \frac{1}{n-1} \sum_{x_i \in c_2} (x_i - \mu_2)^T (x_i - \mu_2)$$

* Now define **within class scatter matrix**(measure spread around mean in each class).
  $$S_w = S_1 + S_2$$
  * we know, $\tilde{S_1^2} = V^T S_1 V$ and $\tilde{S_2^2} = V^T S_2 V$ and we require $\tilde{S_1^2} + \tilde{S_2^2}$
    $$\tilde{S_1^2} + \tilde{S_2^2} = V^T(S_1 + S_2)V = V^T S_w V$$

* Define **between the class scatter matrix**(measure distance between the mean of classes)
  $$S_B = (\mu_1 - \mu_2)^2 = (\mu_1 - \mu_2)(\mu_1 - \mu_2)^T$$

  * we know, $(\tilde{\mu_1} - \tilde{\mu_2})^2 = (V^T\mu_1 - V^T\mu_2)^2 = V.V^T(\mu_1 - \mu_2)(\mu_1 - \mu_2)^T = V^T S_B V$

* we require $max_V, J(V) = \frac{(\tilde{\mu_1^2} - \tilde{\mu_1^2})}{\tilde{S_1^2} + \tilde{\mu_2^2}}$

  $$\frac{\partial J(V)}{\partial V} = 0 => S_BV - \frac{V^TS_BV(S_BV)}{V^TS_WV} = 0$$

* assume $\lambda = \frac{V^T S_B V}{V^T S_W V}$
  $$=> S_BV - \lambda S_W V = 0$$
  $$=> S_BV = S_W(\lambda V)$$
  $$=> S_W^{-1} S_BV = \lambda V$$
  $$=> M V = \lambda V => A.V = \lambda V$$

* here, $M = S_W^{-1}S_B $
* here, $V$ is non-zero eigen vector and $\lambda$ is eigen value
* But $S_BX$ points in the same direction as $\mu_1 - \mu_2$
* $S_B X = (\mu_1 - \mu_2)(\mu_1 - \mu_2)^TX$
* $V = S_W^{-1}(\mu_1 - \mu_2)$

---

eg.

<p align="center>
  <img src="https://private-user-images.githubusercontent.com/100432854/294693238-dd8919eb-4024-4c9d-bd23-d11a2d219c36.jpg" height="" width="">
</p>


<p align="center>
  <img src="https://private-user-images.githubusercontent.com/100432854/294693257-c1e03d2c-a5d4-449f-a038-a65eb57767c1.jpg" height="" width="">
</p>


<p align="center>
  <img src="https://private-user-images.githubusercontent.com/100432854/294693263-480eac3d-f001-4eff-a365-d5fb83cbc7e6.jpg" height="" width="">
</p>

