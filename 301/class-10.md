
# Understanding the JavaScript Call Stack

## What is a ‘call’?
The call is the invocation of a function.
## How many ‘calls’ can happen at once?
only one call can happen at once.
## What does LIFO mean?
LIFO stands for Last In First Out which means the when we call a function that depends on other functions we stack them by the order they were invoked and then execute them in the call stack from top to bottom and free the memory allocated for them after they have been poped out from the call stack.
## Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.

![](https://i.ytimg.com/vi/2ZH_1d8TYVg/maxresdefault.jpg)

## What causes a Stack Overflow?


The stack overflow happens when the size of stacked functions exceeds the size of the call stack. One of the primary reasons for that is using *recursion* `(calling the function inside itself )` without exit point.

------------

# JavaScript error messages

## What is a ‘refrence error’?
The reference error occures when you attempt to access a variable which was not declared yet. 
## What is a ‘syntax error’?
syntax error occures when you break the rules of the programming languages. for example if you pass invalid json object to `JSON.parse` you will end up with syntax error.

## What is a ‘range error’?
Range error occures when you try to mutate the lenght of an array for example. you try to put its length to 0 but by mistake you putted it -1 then the range error message will show.
## What is a ‘tyep error’?

type error is the most frequent error in javascript and occures when you try to access property of undefined type of variable.

```javascript
var foo = {}
foo.bar // undefined
foo.bar.baz // Uncaught TypeError: Cannot read property 'baz' of undefined
```
## What is a breakpoint?

The breakpoint is a point you choose it to  referes to a specific line in your code . By doing this you can debug your code and see the results until this point .

## What does the word ‘debugger’ do in your code?

if we write `debugger` in a specific line in the code then it will create a breakpoint for this line.




## Things I want to know more about.

I want to know more about what the following line means in the references we read  :

`In Asynchronous JavaScript, we have a callback function, an event loop, and a task queue`


### References



[Understanding the JavaScript Call Stack](https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4/)

[JavaScript error messages](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)