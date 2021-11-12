# Data Analysis

## What is Jupyter Lab 

* JupyterLab is a next-generation web-based user interface for Project Jupyter.
* JupyterLab enables you to work with text editors , jupyter notebookes ,terminal and moste common formats.
* text editor in jupyter includes identation and highlighting.
* you can create terminal for your code.
* full support for all systems shells.
* all image formats are supported.
* pdf,html5,tex,json,csv all these formats are supported.
* Jupyter notebook is a new way to work with code and data together.
* Jupyter has two modes:
  1. command : you can navigate and change your framework of your notebook easily
  2. edit : to edit your cells.

* you can switch your cells to write either code or markdown.
  

## Numpy Tutorial 
* Numpy is a python package used commonly in data analysis.
* By using Numpy, you can speed up your work.
* Numpy 2-Dimensional Arrays : you can think of it as list of lists.
* you can create a numpy array from existing list by:
  1. `import numpy as np` `npy_arr = np.array([[1,2],[3,4]])`
  2. `empty_array = np.zeros((3,4))` to create empty array of zeroes.
  3. `np.random.rand(3,4)` to create numpy array of random numbers.the resulting array of rank 2.
* you can read a file using genfromtxt method . `wines = np.genfromtxt("winequality-red.csv", delimiter=";", skip_header=1)`
* the index start from zero as the lists in python.
* you can slicing numpy arrays using colon `:` 
* you can assign value to specific index `wines[1,5] = 10`
* you can also overwrites entire column `wines[:,10] = 50`
`The above code overwrites all the values in the eleventh column with 50.`
* you may encounter numpy arrays with dimensions above 3 you can think of them as list of lists of lists of lists
* numpy can store elements of single data type and those types differ  from those in python becaus numpy was written in `C` language.
* there is an automatic mapping between python and numpy data types.
* you can do math operations on numpy arrays.
  1. `wines[:,11] + 10` add 10 to every element in column 12
  2. you can add array to itself `wines[:,11] + wines[:,11]`
* math operation are done on arrays with same length. if not the same length numpy performs broadcasting to try match up elements by comparing the last dimention in two arrays.
*  you can compare numpy array with values `wines[:,11] > 5` it return numpy of boolean `array([False, False, False, ..., True, False, True], dtype=bool)`


## References
[What is Jupyter Lab](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html)
[NumPy Tutorial: Data Analysis with Python](https://www.dataquest.io/blog/numpy-tutorial-python/)







