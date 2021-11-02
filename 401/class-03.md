# Reading and Writing Files in Python (Guide)

* The file is a set of bytes, these bytes used to store the data.
* each file is composed from three components:
  * Header : type of file , size and other metadat.
  * Data : content of the file.
  * EOF : character specify end of file.
* File path is a location path of the file which composed from the folder path, name of file and extension.
* Line ending is different from operating system to another . in Windows it is represented by `\r\n` and in unix by `\n`.
* To open a file in python you can use `open` method which return file object.
```python
file = open('dog_breeds.txt')
```
* TO close a file there are two ways;
  * use `try` and `finally`
  ```python
        reader = open('dog_breeds.txt')
        try:
            # Further file processing goes here
        finally:
            reader.close()
  ```
  * use `with` keyword
  ```python
  with open('dog_breeds.txt') as reader:
    # Further file processing goes here
  ```
* the `open` method takes a file path as argument and there is another argument which is `mode`.
* `mode` is used to specify what the purpose of opening the file.
  * `r` means open the file for reading.
  * `w` means open the file for writing.it is also overwrites it if there is data.
  * `rb`,`wb` open the file in binary mode.
* The type of file object returned by `open` method is either text file,buffered binary file or raw binary file.
* There are some useful method when open a file in reading mode.
    * read(size) size determines number of bytes to read from the file. if size not provided it will read entire file.
    * readline(size) size determines number of bytes to read from the line. if size not provided it will read entire line.
    * readlines() return a list of all lines
* Also there are some useful method when open a file in writing mode.
  * write(str) : which write string to file.
  * writelines(seq) : which writes sequence to file.

* To append to a file you can use `a` mode 
```python
   with open('dog_breeds.txt', 'a') as  a_writer:
        a_writer.write('\nBeagle')
```
-----
# Python Exceptions: An Introduction
* there are two types of errors in python syntax errors ans exception errors.
* syntax error occures when you write wrong statement.
* exception error occures when you do something wrong in your code but not in the syntax . for example dividing by zero.
* we can raise an exception if a specific condition met.
```python
    x = 10
    if x > 5:
        raise Exception('x should not exceed 5. The value of x was: {}'.format(x))
```
* the program then halts.
* we can also make an assertion error.
```python
        import sys
        assert ('linux' in sys.platform), "This code runs on Linux only."

        Traceback (most recent call last):
        File "<input>", line 2, in <module>
        AssertionError: This code runs on Linux only.
```
the above example throw AssertionError: in case the os was other than linux for example windows.
* we can handle exceptions to prevent program from crashing by using `try except`.
* the code inside `except` block run if there was any exception in `try` statement.
* we can use `else with try except` to excute some code if the try block pass.
* we can also use `finally` to execute some code regardless if exception occures or not.
![](https://files.realpython.com/media/try_except_else_finally.a7fac6c36c55.png)

## References 
[Reading and Writing Files in Python (Guide)](https://realpython.com/read-write-files-python/)

[Python Exceptions: An Introduction
](https://realpython.com/python-exceptions/)


