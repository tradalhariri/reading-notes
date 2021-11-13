# Linear Regressions

## What is Linear Regression?

* Linear Regression is a way for predicting continuous dependent variable outcome depends on independent variables. The simple form of linear regression is a line equation `y = c + b*x` where y is the dependent variable and x is the independent variable. In reality there are more than one independent variables that affect the prediction.
  
## How to Run Linear Regression in Python

* we will implement linear regression using Scikit-learn python module which contains functions for regression, classification,clustering, model selection and dimensionality reduction.
* we will use Boston Housing data set, the data set contains information about the housing values in suburbs of Boston
1. first we need to import the required packages
```python
%matplotlib inline
import numpy as np
import pandas as pd
import scipy.stats as stats
import matplotlib.pyplot as plt
import sklearn 
```
2. load data set from sklearn.
```python
from sklearn.datasets import load_boston
boston = load_boston()
```
3. `boston.keys()` return `dict_keys(['data', 'target', 'feature_names', 'DESCR', 'filename'])`
4. `boston.data.shape` return `(506, 13)`
5. `boston.feature_names` feature_names mean independent variables. last statement returns 
`array(['CRIM', 'ZN', 'INDUS', 'CHAS', 'NOX', 'RM', 'AGE', 'DIS', 'RAD','TAX', 'PTRATIO', 'B', 'LSTAT'], dtype='<U7')`
6. convert boston.data into a pandas data frame `bos = pd.DataFrame(boston.data)`
`bos.head()`

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Pandas-DataFrame.png)
7. make the columns names the feature names `bos.columns = boston.feature_names`

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/bos-columns.png)


8. add the target column values as `PRICE` column. `bos['PRICE'] = boston.target`
![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/RAD.png)

## Scikit Learn
1. we need to drop `PRICE` column from a data set and store the result in `X` dataset which is the independent variables.
`X = bos.drop('PRICE',axis = 1)`

2. `from sklearn.linear_model import LinearRegression`
`lm = LinearRegression()`
3. fit linear regression  `lm.fit(X, bos.PRICE)` 
4. construct a data frame that contains features and estimated coefficients `pd.DataFrame(zip(X.columns,lm.coef_),columns =['features','estimated coeffeciatnts'])`
![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/pd-data-frame.png)

5. here is a high correlation between RM and prices.
![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Relationship-between-RM-and-Price.png)
6. we then need to comare the prediction with the actual values.
```python
plt.scatter(bos.PRICE,lm.predict(X))
plt.xlabel("prices")
plt.ylabel("predicted")
plt.show()
```

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Prices-vs-predicted-prices.png)

there is an error when the price increasing.

7. In practice we dont fit the entire dataset . we always split it into training dataset and test dataset. Scikit learn provides a function called train_test_split to do this.

![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Xtrain-and-Xtest.png)
![](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Linear-reg.png)

then we calculate the mean square error on training and test datasets.

### References

[What is Linear Regression?](https://www.statisticssolutions.com/free-resources/directory-of-statistical-analyses/what-is-linear-regression/)
[How to run Linear regression in Python scikit-Learn](https://bigdata-madesimple.com/how-to-run-linear-regression-in-python-scikit-learn/)
