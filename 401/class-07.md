## Python Scope

* There are four scopes in python: 
  * Local all names declared inside a function will be accessed from its local scope.
  * Enclosed : this the case when you define function inside another, then the names in the outer function scope will be accessed from inner function local scope .
  * Global : all names you defined in the top of the module are accessible from any part from code.
  * Built in : `This scope contains names such as keywords, functions, exceptions, and other attributes that are built into Python`

### global statement
* when you access a global name from a local scope you cant update it unless you declare it as `global` . it assumed it as a local variable.
```python
var = 100  # A global variable
def increment():
    var = var + 1  # Try to update a global variable

increment()
UnboundLocalError: local variable 'var' referenced before assignment
```


***You can also use a global statement to create lazy global names by declaring them inside a function. Take a look at the following code:***
```python
def create_lazy_name():
    global lazy  # Create a global name, lazy
    lazy = 100
    return lazy

create_lazy_name()
100
lazy  # The name is now available in the 
global scope
100
```
### The nonlocal Statement
* when you access a enclosed name from a inner local scope you cant update it unless you declare it as `nonlocal` inside the inner function.

```python
def func():
    var = 100  # A nonlocal variable
    def nested():
        nonlocal var  # Declare var as nonlocal
        var += 100

    nested()
    print(var)

func()
```


* if we try to use `nonlocal` in the global scope it will throw error


`nonlocal my_var  # Try to use nonlocal in the global scope`
  `File "<stdin>", line 1`

* we cant use `nonlocal` to create lazy variables.



![example](https://www.askpython.com/wp-content/uploads/2019/08/python-variable-scope-example-1024x912.png)