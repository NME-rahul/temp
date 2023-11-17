* Select the prediction function.
* Select the cost function.
* Update the coefficients of the function.

# Simple Regression

* Select the prediction function.
   $$\hat{y} = a_1x_1 + a_2x_2 + a_3x_3 + ... + a_kx_k + b$$
  
  where,
  
  a: trainable parameter(weights)
  
  b: trainable parameter(bias)


* Select the cost function.
  $$error = \frac{1}{n}\sum{(y_i - \hat{y_i})^2}$$
  $$error = \frac{1}{n} \sum{(Y_i - (a_1x_1 + a_2x_2 + a_3x_3 + ... + a_kx_k + b))^2}$$

  * to update the trainable parameters you need to partial differentiate the error function with respect to the corresponding coefficient.

  $$\frac{\partial error}{\partial a_1} = \frac{1}{n} \sum{ 2* (y_i - (a_1x_1 + a_2x_2 + a_3x_3 + b)) * (-x_1) }$$
  $$\frac{\partial error}{\partial a_2} = \frac{1}{n} \sum{ 2* (y_i - (a_1x_1 + a_2x_2 + a_3x_3 + b)) * (-x_2) }$$
  $$\frac{\partial error}{\partial a_3} = \frac{1}{n} \sum{ 2* (y_i - (a_1x_1 + a_2x_2 + a_3x_3 + b)) * (-x_3) }$$
  $$\frac{\partial error}{\partial b} = \frac{1}{n} \sum{ 2* (y_i - (a_1x_1 + a_2x_2 + a_3x_3 + b)) * (-1) }$$


* Update the parameter.
  $$a_{1,new} = a_{1,old} - \alpha * \frac{\partial error}{\partial a_1}$$
  $$a_{2,new} = a_{2,old} - \alpha * \frac{\partial error}{\partial a_2}$$
  $$a_{3,new} = a_{3,old} - \alpha * \frac{\partial error}{\partial a_3}$$
  $$b_{new} = b_{old} - \alpha * \frac{\partial error}{\partial b}$$


# Logistic Regression

   $$z = \hat{y} = a_1x_1 + a_2x_2 + a_3x_3 + ... + a_kx_k + b$$

   $$P(z) = \frac{1}{1 + \exp{-z}}$$

* p(z) is used to scale the value between 0 and 1 so that we can perform binary classification.

* select the cost function, log-loss is used for the binary classification.

  $$j = -\frac{1}{n} \sum{P(\hat{y_i})^{\hat{y_i}}*(1 - P(\hat{y_i}))^{(1 - \hat{y_i})}}$$
  
  $$\log{j} = -\frac{1}{n} \sum{ \log{[ P(\hat{y_i})^{y_i}*(1 - P(\hat{y_i}))^{(1 - \hat{y_i})}]} } $$

  $$J = -\frac{1}{n} \sum{ y_i\log{[ P(\hat{y_i})] + (1 - \hat{y_i})\log[(1 - P(\hat{y_i}))]} }$$

|Cost function|prediction|
|---|---|
| $$- \log{ P( \hat{y_i} ) }$$ | y = 1|
|$$- \log{ (1 - P( \hat{y_i} ) ) }$$|  y = 0|

  

