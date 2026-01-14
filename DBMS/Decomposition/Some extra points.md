* If there is no common attribute in between two relations then Natural-Join becomes cross product.
* A decomposition $R \rightarrow R_1$ and $R_2$ is lossless if and only if the common attribute is a superkey in at least one of $R_1$ and $R_2$
* When we can get the original information by joining the decomposed information then why we need depedency preserving?
  * Joining Lossless decomposed relations definitely gives us original relation(inforamation) but to perform any opeartion(insert, update) requires join(expensive operation). But, if decompostion is dependency preserving together with lossless then we need not to require join to enforce the functional dependency, thats why dependency preserving is desireable and not necessary.

<div align="center">
  <img width="400" height="300" alt="image" src="https://github.com/user-attachments/assets/338af57c-2c43-4c31-8535-ddd1b2896f8f" />
</div>



