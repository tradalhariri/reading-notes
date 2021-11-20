# Data Science Primer


 ![](https://elitedatascience.com/wp-content/uploads/2018/05/What-Goes-Into-a-Successful-Model.jpg)
 
## chapter 1 

* Machine learning dosnt mean algorithms.

* Machine learning is a comprehensive approach to solving problems...

* Machine learning is the practice of teaching computers how to learn patterns from data, often for making decisions or predictions.

* For true machine learning, the computer must be able to learn patterns that it's not explicitly programmed to identify.

`Model` - a set of patterns learned from data.

`Algorithm` - a specific ML process used to train a model.

`Training data` - the dataset from which the algorithm learns the model.

`Test data` - a new dataset for reliably evaluating model performance.

`Features` - Variables (columns) in the dataset used to train the model.

`Target variable` - A specific variable you're trying to predict.

`Observations` - Data points (rows) in the dataset.

### Machine Learning Tasks
* In applied machine learning, you should first pick the right machine learning task for the job.

* A task is a specific objective for your algorithms.

* Algorithms can be swapped in and out, as long as you pick the right task.

* In fact, you should always try multiple algorithms because you most likely won't know which one will perform best for your dataset.
* The two most common categories of tasks are supervised learning (data labeled) and unsupervised learning(unlabeled data)

## chapter 2
* exploratory data analysis is an approach of analyzing data sets to summarize their main characteristics, often using visualization methods.


* The purpose of exploratory analysis is to "get to know" the dataset.
*  Doing exploratory data analysis so upfront will make the rest of the project much smoother, in 3 main ways:

* You’ll gain valuable hints for Data Cleaning (which can make or break your models).

* You’ll think of ideas for Feature Engineering (which can take your models from good to great).

* You’ll get a "feel" for the dataset, which will help you communicate results and deliver greater impact.

## chapter 3
* Data cleaning is the process of fixing or removing incorrect, corrupted, incorrectly formatted, duplicate, or incomplete data abservations within a dataset.
  
* It involves : 
  - Remove Unwanted observations
  - Fix Structural Errors
  - Filter Unwanted Outliers
  - Handle Missing Data

## chapter 4
* Feature engineering means creating new features from existing ones.
* data scientist do feature engineering to improve model performance.
* there are several heuristics
  * Create Interaction Features
  > The first of these heuristics is checking to see if you can create any interaction features that make sense. These are combinations of two or more features
  * Combine Sparse Classes - sparse classes (in categorical features) are those that have very few total observations.
  * Add Dummy Variables - Most machine learning algorithms cannot directly handle categorical features. Specifically, they cannot handle text values so we create dummy variable for those.
  * Remove Unused Features : remove unused or redundant features from the dataset.





 
## chapter 5
* simple linear regression suffers from two major flaws:

1. It's prone to overfit with many input features.
2. It cannot easily express non-linear relationships.

* Regularization is artificially penalizing model coefficients to prevent overriten.

* in this chapter we will discuss 5 effective machine learning algorithms for regression :
  - Lasso regression - Practically, this leads to coefficients that can be exactly 0
  - Ridge regression - Practically, this leads to smaller coefficients, but it doesn't force them to 0.
  - Elastic-Net - Elastic-Net penalizes a mix of both absolute and squared size.
  - Random forest - Random forests train a large number of "strong" decision trees and combine their predictions through bagging.
  - Boosted tree - Boosted trees train a sequence of "weak", constrained decision trees and combine their predictions through boosting.

## chapter 6
- split the dataset to train and test data sets.
- > Comparing test vs. training performance allows us to avoid overfitting... If the model performs very well on the training data but poorly on the test data, then it’s overfit.
- What are Hyperparameters?  The key distinction is that model parameters can be learned directly from the training data while hyperparameters cannot.
- What is Cross-Validation?  Cross-validation is a method for getting a reliable estimate of model performance using only your training data.
- the most common way to perform cross-validation is 10-fold cross-validation.
- > These are the steps for 10-fold cross-validation: 
  1. Split your data into 10 equal parts, or "folds".
  2. Train your model on 9 folds (e.g. the first 9 folds).
  3. Evaluate it on the 1 remaining "hold-out" fold.
  4. Perform steps (2) and (3) 10 times, each time holding out a different fold.
  5. Average the performance across all 10 hold-out folds.

- Fit and Tune Models : we need to  perform the entire cross-validation loop detailed above on each set of hyperparameter values we'd like to try.
```
  For each algorithm (i.e. regularized regression, random forest, etc.):
  For each set of hyperparameter values to try:
    Perform cross-validation using the training set.
    Calculate cross-validated score.
```
- Then, we'll pick the best set of hyperparameters within each algorithm.
```
For each algorithm:
  Keep the set of hyperparameter values with best cross-validated score.
  Re-train the algorithm on the entire training set (without cross-validation).
```
- Select Winning Model
> For regression tasks, we recommend Mean Squared Error (MSE) or Mean Absolute Error (MAE). (Lower values are better)
For classification tasks, we recommend Area Under ROC Curve (AUROC). (Higher values are better)
- The process is very straightforward:

1. For each of your models, make predictions on your test set.
2. Calculate performance metrics using those predictions and the "ground truth" target variable from the test set.

### References
[Data Science Primer](https://elitedatascience.com/primer)