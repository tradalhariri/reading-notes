# List Comprehensions in Python


* Using list comprehension in python make your code more elegent and readable.
* It is a consice way for building lists.
* It is composed from three components:
  - The expresion on each item that would be appeare in the new list.
  - The item itself
  - The Iterable 
  - `new_list = [expression for member in iterable]`

* for example if you want to create a list using for loop you may need several lines of code to do that.
```python
  # create a list using a for loop
squares = []

for x in range(10):
    # raise x to the power of 2
    squares.append(x**2)

print(squares)
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
* you can acheive the same results with list comprehension:
```python
# create a list using list comprehension
squares = [x**2 for x in range(10)]

print(squares)
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

* list comprehension help you creating lists by applying some methods on each item.
* For instance we can create custom list from string
```python
# a list of the names of popular authors
authors = ["Ernest Hemingway","Langston Hughes","Frank Herbert","Toni Morrison",
    "Emily Dickson","Stephen King"]

# create an acronym from the first letter of the author's names
letters = [ name[0] for name in authors ]
print(letters)
['E', 'L', 'F', 'T', 'E', 'S']

```

* we can use filter on each item
```python
even_numbers = [ x for x in range(1,20) if x % 2 == 0]


[2, 4, 6, 8, 10, 12, 14, 16, 18]
```
* we can use our own cutom function in list comprehension 
```python
# list comprehension with functions
# create a function that returns a number doubled
def double(x):
    return x*2

nums = [double(x) for x in range(1,10)]
print(nums)
[2, 4, 6, 8, 10, 12, 14, 16, 18]

```

## References 
[List Comprehensions in Python](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)


