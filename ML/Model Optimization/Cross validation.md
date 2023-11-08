# Cross -Validation
* Cross Validation is a technique used in machine learning to evaluate the performance of a model on unseen data. It involves dividing the available data into mulitiple subset, using one of them as a validation set and rest for training set.
* finally results from each steps are averaged to produce a more robust estimate of the model's performance.
* The purpose of cross-validation is prevent overfitting, which occurs when a model is trained too well on the training data and perform poorly on new data.

### Leave-One-Out Cross-Validation(LOOCV)
* It is a special case of cross validation.
* In this technique, every data point of dataset is used for training except 1 that is used for the validation. for example if dataset have n samples then n-1 will be used for training and 1 for validation.

1. advantages
2. Disadvantages


### K-Fold
* The procedure has a single parameter called K that refers to the number of split of data.
1. shuffle the dataset randomly.
2. split the dataset into k parts
3. for k times,
   * select K-1 random subset as a training set and a validation set.
5. Evaulaute the model performace on validaion set.
6. Average the performance metric over k iteration to obtain the overall performance of the model.


k=10 is best value for every type of variance, the appropriate k value is choosed the bases of variance of data.


# Nested Cross-Validation

Neted cross-validation is technique use for model selection and hyperparameter tuning.

* in nested cross-validation we have double loop, an outer loop serving as k-folds validation loop to split the data into training and validation set, inner loop serves for selection of model's hyperparameter.

1. **Outer loop(Model evaluation)**: The dataset is divides into k subset, for each interation
   * One subset is used as the validation set.
   * The remaining k-1 subsets are used as the training set.
   * The model is trainied on the training set and evaluated on the validation set.

2. **Outer loop(Model selection and hyperparameter tuning)**: within each iteration of the outer loop, the training set is further divided into k subset, For each iteration of inner loop:
   * One subset is used as the validation set.
   * The remaining k-1 subset are used as the training set of model selection and hyperparameter tuning.
   * Difference models with various hyperparameter configuration are trainied and evaluated on the validation set.
   * The best performing model and it's asscoiated hyperparameters are selected.

----
  
In a simple way the outer loop serves as a k-fold method and inner loop is used to selects the best hyperparameters  for each k-fold

let we have a list of hyperparameters

|learning_rate|Dense_layers|droput_rate|activation|kerenl_size|
|---|---|---|---|---|
|0.1|[1024, 512, 256]|0.1|'relu'|(3,3)|
|0.1|[256, 128, 64]|0.2|'sigmoid'|(1,1)|
|0.1|[1024, 256, 32]|0.4|'leaky_relu'|(5,5)|
|0.1|[512, 1024, 512]|0.3|'relu'|(7,7)|

* For eack, K outer loops
  * By using k-fold method split dataset into k-1 training set and 1 validation set.
    * for each above split, (inner loop)
      * select one row of hyperparametres and train the model on above splited dataset.
