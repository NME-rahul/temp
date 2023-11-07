# Principal Component Analysis

PCA is a dimensionality reduction method, by transforming a large set of variables into a smaller one that still contains most of the inofrmation in the large set.

Reucing the number of variables of a data set naturally comes at the expense of accuracy, but the trick in dimensionality reduction s to trade a little accuracy for simplicity. Because samller datasets are easier the explore and visualize and train faster on ML algorithms.

It accomplish this by transforming the data into a new coordinate system where the axes are the principal component which are liear combinations of the original variables.


The first principal has the the highesst variance possible and each succeseeding component have the lower variance then their before component.

### Procedure

1. Standerdize the data
   $$X = \frac{x - \mu}{\sigma}$$

2. Find the Covariance matrix
   $$C = \frac{1}{N} X^{T}X$$
   
    | X | Y | Z | ... | K |
    |---|---|---|-----|---|
    | $$Cov(X,X)$$ | $$Cov(X,Y)$$ | $$Cov(X,Z)$$ | ... | $$Cov(X,K)$$ |
    | $$Cov(Y,X)$$ | $$Cov(Y,Y)$$ | $$Cov(Y,Z)$$ | ... | $$Cov(X,K)$$ |
    | $$Cov(Z,X)$$ | $$Cov(Z,Y)$$ | $$Cov(Z,Z)$$ | ... | $$Cov(Z,K)$$ |
    | . | . | . | . | . |
    | $$Cov(K,X)$$ | $$Cov(K,Y)$$ | $$Cov(K,Z)$$ | ... | $$Cov(K,K)$$ |

3. Find the eigne values and eigen vectors.
   $$A\overrightarrow X = \lambda \overrightarrow X$$
   <p style="color:"blue"">here X: eignevector and \lamda: eignevalue</p>
   
  $$(A - \lambda I) \overrightarrow X = 0$$

4. Create the feature vector to decide which principal component to keep.

   
