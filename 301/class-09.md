# Functional Programming Concepts

## What is functional programming?
Functional programming is a programming structure that protects the mutable data from changing and avoids changing the state.
## What is a pure function and how do we know if something is a pure function?
* The pure function always return the same value to the same parameters.
* It does not cause any observable side effects . It means the pure function can not alter other parts of the system for example it will unable to change the global object or parameteres passed by reference.
## What are the benefits of a pure function?
The most important benefit from pure function is the testing becomes easier since we can expect what the returned value from specific parameters.
## What is immutability?
The immutability in the functional programming is to make the mutable objects immutable for example instead of using for loop we can use recursive concept.
## What is Referential transparency?
Referential transparency in simple word is pure functions + immutable data;


# Node JS Tutorial for Beginners #6 - Modules and require()

## What is a module?
module is a javascript file that has its own code. We break the whole code into modules to make it easy to refactor the code so every module has its own functionality.
## What does the word ‘require’ do?

require exists on the global object of the node so we can call it inside other modules. It allows to bring other modules inside the current. 

## How do we bring another module into the file the we are working in?
We can  write `require('name of the module')` inside the file we working in.
## What do we have to do to make a module available?

To make the module available we must export it. To do that in the end line of the module we write

`module.exports = what we want to export`


## Things I want to know more about.
I want to learn more about functional programming.


### References

[Functional Programming Concepts](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)

[Node JS Tutorial for Beginners #6 - Modules and require()](https://www.youtube.com/watch?v=xHLd36QoS4k)