# Classes and Objects
* The class is a template or blueprint for creating objects.
* The class define the whole structure of how the objects will be.
* from class we can generate objects as many as we want.
* each object store its own variables and functions.
* the function represnts the behaviour of the object.
* This a simple example of how we can define class in python and how we can create multiple instances from it.
```python
class MyClass:
    variable = "blah"

    def function(self):
        print("This is a message inside the class.")

myobjectx = MyClass()
myobjecty = MyClass()

myobjecty.variable = "yackity"

# Then print out both values
print(myobjectx.variable)
print(myobjecty.variable)
```

# Thinking Recursively in Python

* You may encounter some problems and feel it is so hard to solve, but if you can convert it to sub problems that each sub problem is the same as the big one but with smaller dimention then you can think to solve this problem recursively.
* For instances if we took the factorial problem as an example. we will notice that the factorial for any number can be represent with an equation of the factorial of previous one.
* `n! = n x (n−1) x (n−2) x (n−3) ⋅⋅⋅⋅ x 3 x 2 x 1`
* `n! = n x (n−1)!`
* to solve a problem recursively we must choose the base condition or base case that prevent the function calling itself infinity.
* 
```python
    def factorial_recursive(n):
        # Base case: 1! = 1
        if n == 1:
            return 1

        # Recursive case: n! = n * (n-1)!
        else:
            return n * factorial_recursive(n-1)
```

* in the above example the base case is when the number reach one.
### Maintaining State


* during the execution of recursive functions each call has its own execution context so we can either :
   * maintain the state globally
   * or in each execution context
* this an example to maintain the state in each execution call context. the example compute the summation from 1 to 10.
* 
```python
def sum_recursive(current_number, accumulated_sum):
    # Base case
    # Return the final state
    if current_number == 11:
        return accumulated_sum

    # Recursive case
    # Thread the state through the recursive call
    else:
        return sum_recursive(current_number + 1, accumulated_sum + current_number)
```
*  ![](https://robocrop.realpython.net/?url=https%3A//files.realpython.com/media/state_3.3e8a68c4fde5.png&w=1293&sig=365778ead2c38e2a10b95f53f3fc2f0f2e2bbce0)
  ----
### Recursive Data Structures in Python

* we can call data structure is recursive if it can be formed from smaller parts of itself.
* the list is recursive data structure since it can be formed from raw elements.
* other examples of recursive data structures ar dictionary and set in python.

# Python Testing with pytest: Fixtures and Coverage

* You can write a test function and decorate it with `@pytest.fixture` and used it as a data for the function you want to test.
* Fixture has many benefits. you can set it up to be available inside the module so it will reduce the compution or connection databases.
* Coverage is a measure of the unit test. it cover all the test cases.

## References 
[ Thinking Recursively in Python](https://realpython.com/python-thinking-recursively/)

[Classes and Objects](https://www.learnpython.org/en/Classes_and_Objects)

[Python Testing with pytest: Fixtures and Coverage](https://www.linuxjournal.com/content/python-testing-pytest-fixtures-and-coverage)