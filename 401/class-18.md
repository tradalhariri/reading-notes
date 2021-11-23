## Python Regular Expression Tutorial

* Regular Expressions, often shortened as regex, are a sequence of characters used to check whether a pattern exists in a given text (string) or not.
* used in search engines,text editors, check email validation , passwords and more.


### Regular Expressions in Python

* In Python, regular expressions are supported by the `re` module.


* `import re`

* there are several functions inside `re` module that can help you to find pattern in python.

## Basic Patterns: Ordinary Characters
* ordinary characters represent themselves . they dont add any special meaning to pattern.
* Examples are 'A', 'a', 'X', '5'.


```python

pattern = r"Cookie"
sequence = "Cookie"
if re.match(pattern, sequence):
    print("Match!")
else: print("Not a match!")

```
`Match!`
## Wild Card Characters: Special Characters
* characteres  have a special meaning when used in a regular expression.
* A period. Matches any single character except the newline character.
```python
re.search(r'Co.k.e', 'Cookie').group()
'Cookie'
``` 
*  A caret. Matches the start of the string.
```python
re.search(r'^Eat', "Eat cake!").group()

## However, the code below will not give the same result. Try it for yourself:
# re.search(r'^eat', "Let's eat cake!").group()
'Eat'
```
* $ - Matches the end of string.
```python
re.search(r'cake$', "Cake! Let's eat cake").group()

## The next search will return the NONE value, try it:
# re.search(r'cake$', "Let's get some cake on our way home!").group()
'cake'
```

* `[abc]` - Matches a or b or c.
* `[a-zA-Z0-9] `- Matches any letter from (a to z) or (A to Z) or (0 to 9).
* `\w` - Lowercase 'w'. Matches any single letter, digit, or underscore.
* `\W` - Uppercase 'W'. Matches any character not part of \w (lowercase w).

```python 
print("Lowercase w:", re.search(r'Co\wk\we', 'Cookie').group())

## Matches any character except single letter, digit or underscore
print("Uppercase W:", re.search(r'C\Wke', 'C@ke').group())

## Uppercase W won't match single letter, digit
print("Uppercase W won't match, and return:", re.search(r'Co\Wk\We', 'Cookie'))
Lowercase w: Cookie
Uppercase W: C@ke
Uppercase W won't match, and return: None
```
* `\s` - Lowercase 's'. Matches a single whitespace character like: space, newline, tab, return.
* `\S` - Uppercase 'S'. Matches any character not part of \s (lowercase s).

* `\d` - Lowercase d. Matches decimal digit 0-9.
* `\D` - Uppercase d. Matches any character that is not a decimal digit.
## Repetitions


* `+`  Checks if the preceding character appears one or more times starting from that position
* `*`  Checks if the preceding character appears zero or more times starting from that position.
* `?` - Checks if the preceding character appears exactly zero or one time starting from that position.

## Grouping in Regular Expressions
* The group feature of regular expression allows you to pick up parts of the matching text. Parts of a regular expression pattern bounded by parenthesis () are called groups
```python
statement = 'Please contact us at: support@datacamp.com'
match = re.search(r'([\w\.-]+)@([\w\.-]+)', statement)
if statement:
  print("Email address:", match.group()) # The whole matched text
  print("Username:", match.group(1)) # The username (group 1)
  print("Host:", match.group(2)) # The host (group 2)
Email address: support@datacamp.com
Username: support
Host: datacamp.com
```

## Greedy vs. Non-Greedy Matching
* When a special character matches as much of the search sequence (string) as possible, it is said to be a "Greedy Match". It is the normal behavior of a regular expression, but sometimes this behavior is not desired:

```python

heading  = r'<h1>TITLE</h1>'
re.match(r'<.*>', heading).group()
'<h1>TITLE</h1>'
```
* However, if you only wanted to match the first `<h1>` tag, you could have used the greedy qualifier *? that matches as little text as possible.
```python
heading  = r'<h1>TITLE</h1>'
re.match(r'<.*?>', heading).group()
'<h1>'
```
## Summary table
![](https://miro.medium.com/max/1400/1*9rlD7grrXfk301gCa7XSMw.png)

# shutil — High-level File Operations

## Copying Files

copyfile() copies the contents of the source to the destination and raises IOError if it does not have permission to write to the destination file.

Example:


>import glob
import shutil
print('BEFORE:', glob.glob('shutil_copyfile.*'))
shutil.copyfile('shutil_copyfile.py', 'shutil_copyfile.py.copy')
print('AFTER:', glob.glob('shutil_copyfile.*'))

## Archives

* Python’s standard library includes many modules for managing archive files such as tarfile and zipfile. There are also several higher-level functions for creating and extracting archives in shutil. get_archive_formats() returns a sequence of names and descriptions for formats supported on the current system.

>import shutil
for format, description in shutil.get_archive_formats():
    print('{:<5}: {}'.format(format, description))

### References
[Regex ](https://www.datacamp.com/community/tutorials/python-regular-expression-tutorial)
[Shutil](https://pymotw.com/3/shutil/)