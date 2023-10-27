Bias-Variance tradeoff descibes the relationship between a model's complexity and accuracy on unseen data.

![](https://www.cs.cornell.edu/courses/cs4780/2018fa/lectures/images/bias_variance/bullseye.png)

![](https://scott.fortmann-roe.com/docs/docs/BiasVariance/biasvariance.png)

## High variance
Variance refers to the model's sensitivity to fluctuation in the training data. A high-variance model is overly flexible, often capturing noise and random fluctation in the training data, which can lead to overfiting.

$$\sigma^2 = \frac{1}{N}\sum{x_i^2} - \bar{X}$$

In the first look, the cause of the poor performance is high variance

**Symptoms**
* Training error is much lowe then test error.
* Training error is lower then e.
* Test error is above e.

**Remidies**
* Add more training data.
* Reduce model complexity, complex models are prone to high variance.
* Use Bagging.


## High Bias

Bias refers to the error introduced by approximating a real-world problem with simplified model. High-bias model is typically less flexible, making it more likely to underfit the training data, leading to a sigificant error between the model's predicton and the actual data.

$$ bias = \frac{\sum{predicted} - avg(predicted)}{N}$$

N: number of predicted values

Unlike the first look, second look indicates high bias: the model being used is not robust enough to produce an accurate prediction.

**Symptoms**
* Training error is higher then e.

**Remidies**
* Use more complex model.
* Add features.
* Use Boosting
