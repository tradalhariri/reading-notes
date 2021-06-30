# Ch.10  Error Handling & Debugging

* Order Of Execution : if value of any statement depends on another function the statement  stacks that function on the top of it and it now in the waiting phase and if that function depends on another one the second function it will stacked on the top of previous function and when the current function finshes it is removed from the stack and so on until the statement gets the value.
  

![Order Of Execution](https://i.ibb.co/MMLLC6F/one.png)
![Order Of Execution](https://i.ibb.co/vLT58s0/two.png)

* Hoisting : you may have seen a calling of a function before it is declared or a  value assigned to a variable before it is declared too. This is known hoisting in javascript . it takes all variables and function to the top of script and create them.
  
* when there is any error in an javascript statement the interpreter stops and throw an exception.
* the interpreter generates many types of error objects. these error objects can help the developers to determin the error. examples of these objects is Error,ReferenceError and SyntaxError.

* How to deal with errors 
you can deal with errors using the two following ways
  1. DEBUG THE SCRIPT TO FIX ERRORS : you can use a modern web browser dev tools to help you from where the error comes.
  2. HANDLE ERRORS GRACEFULLY : some error maybe come from third part and their server was down so you can handle these types of error using `try, catch, finally` statements.

* you can also use break points in the browser at any line to check the values of the variables in this line.
  
![Break Points](https://i.ibb.co/g3VPHdY/three.png)


