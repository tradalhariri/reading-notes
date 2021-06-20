# Expressions and operators

In JavaScript there are three types of operators:
* Binary Operator : Binary Operator needs two operands one before operator and another after operator.

```
for example :
(3+4)   3 is first operand and 4 is second operand.
```

*  Unary operator : There is single operand either before the operator or after it.
```
For example, x++ or ++x.
```

* Ternary operator : It is a conditional but it 
is written in one line.

```
var status = (score >= 90) ? 'pass' : 'fail';

```
 Let us discuss the various types of JavaScript Operators.

 1.  Assignment operators. It assigns value or variable after the assign operand to the variable before assign operand.


 `x = y assigns the value of y to x.`

 there are also compound assignment operators as the following table shows some of tehm.

 | Name      | Shorthand operator	 | Meaning     |
| :---        |    :----:   |          ---: |
| Addition assignment      | x += y       | x = x + y   |
| Exponentiation assignment   | x **= y        | x = x ** y      |
| Bitwise AND assignment   | x &= y      | x = x & y      |

2. Comparison operators : The operator compares its operands and return true or false based based whether the condition is true or not.

the following table lists some of the common Comparison Operators .

 | Operator      | Description | Meaning     |
| :---        |    :----:   |          ---: |
| Equal (==)      | Returns true if the operands are equal      | if(3 == '3') statment will return true |
| Greater than (>)   | 	Returns true if the left operand is greater than the right operand.       | "12" > 2 will return true     |
| Less than or equal (<=)  | Returns true if the left operand is less than or equal to the right operand.      | 3 <= 5  will return true     |

3. Arithmetic operators : It takes numerical values and return a value.


  Examples of these operators are addition (+), subtraction (-), multiplication (*), and division (/) ,Remainder (%),Exponentiation operator (**) and Increment (++).

  4. Bitwise operators : It treats its operands as 32 binary bits then perform the operation but it returns the expectd value as number.

  ```
  Bitwise AND operator :	a & b	Returns a one in each bit position for which the corresponding bits of both operands are ones.
  ```

  5. Logical operators : When the Logical operators used with non boolean values they may return non boolean value otherwise they will return a boolean value.
```
var a1 =  true && true;     // t && t returns true
var a2 =  true && false;    // t && f returns false
var a3 = false && true;     // f && t returns false
var a4 = false && (3 == 4); // f && f returns false
var a5 = 'Cat' && 'Dog';    // t && t returns Dog because the first operand is not false. the empty string can be considerd as false.
var a6 = false && 'Cat';    // f && t returns false
var a7 = 'Cat' && false;    // t && f returns false
```

6. String operators : the  concatenation operator (+) is used to concatenate two or more string to form a single string .

```

var mystring = 'alpha';
mystring += 'bet'; // evaluates to "alphabet" and assigns this value to mystring.
   
```

7. Comma operator : It evaluate its two operands and return the second operand.

```
x = (2, 3);

console.log(x);
// expected output: 3
```

8. Unary operators : 
* delete : delete the property of the object.
 `delete object.property;`

 * typeof : return the type of anything.

 ```
var myFun = new Function('5 + 2');
var shape = 'round';
var size = 1;
var foo = ['Apple', 'Mango', 'Orange'];
var today = new Date();
```

9. Relational operators : 

* in : to check if the property inside the object.

```
'PI' in Math;          // returns true
var myString = new String('coral');
'length' in myString;  // returns true
```

* instanceof : 
 
 returns true if the specified object is of the specified object type.

```
 var theDay = new Date(1995, 12, 17);
if (theDay instanceof Date) {
  // statements to execute
}
```


# Functions 
function is a block of code that perform a task or some calculations.
* Defining functions : to declare a function we write 
a `function` keyword follwed by the name of the function and its parameters and then the curly braces that contains the statements of the function.
```
function myFunc(theObject) {
  theObject.make = 'Toyota';
}



var mycar = {make: 'Honda', model: 'Accord', year: 1998};
var x, y;

x = mycar.make; // x gets the value "Honda"

myFunc(mycar);
y = mycar.make; // y gets the value "Toyota"
                // (the make property was changed by the function)
```
* Function expressions : 
we can create a function withot a name (anonymous function)
```
const square = function(number) { return number * number }
var x = square(4) // x gets the value 16
```

we can use the anonymous function as a parameter of another function.

```
function map(f, a) {
  let result = []; // Create a new Array
  let i; // Declare variable
  for (i = 0; i != a.length; i++)
    result[i] = f(a[i]);
  return result;
}
const f = function(x) {
   return x * x * x;
}
let numbers = [0, 1, 2, 5, 10];
let cube = map(f,numbers);
console.log(cube);
```

* Calling functions : 
to call a function we write the name of it with the indicated  parameters.


the function calling must be in the scope but the function declaration can be anywhere in program. 

```
console.log(square(5));
/* ... */
function square(n) { return n * n }
```

if the function is declared as function expression the above code not work 
```
console.log(square)    // square is hoisted with an initial value undefined.
console.log(square(5)) // Uncaught TypeError: square is not a function
const square = function(n) {
  return n * n;
}
```

* Function scope : 
the function can access to any variables declared in global scope in addition to the variables inside its scope and if we declare a function inside another then the function can access to its parent variables 

```
// The following variables are defined in the global scope
var num1 = 20,
    num2 = 3,
    name = 'Chamakh';

// This function is defined in the global scope
function multiply() {
  return num1 * num2;
}

multiply(); // Returns 60

// A nested function example
function getScore() {
  var num1 = 2,
      num2 = 3;

  function add() {
    return name + ' scored ' + (num1 + num2);
  }

  return add();
}

getScore(); // Returns "Chamakh scored 5"
```
* Scope and the function stack : we can call the function inside itself by using one of the following ways :

1. The function's name
2. arguments.callee
3. An in-scope variable that refers to the function

```
    var foo = function bar() {
      // statements go here
    }
```
Within the function body, the following are all equivalent:

bar()
arguments.callee()
foo()


calling the function inside itself is known a recursion and it needs to a condition to stop calling itself infinity.

* Nested functions and closures :

we can define function inside another function.

The inner function can be accessed only from statements in the outer function.
 the inner function can use the arguments and variables of the outer function, while the outer function cannot use the arguments and variables of the inner function

* Multiply-nested functions : 
we can have mor than two levels of nested functions.

 scope chaining is refer  that the lowest function level can access its all parents levels.

```
    function A(x) {
      function B(y) {
        function C(z) {
          console.log(x + y + z);
        }
        C(3);
      }
      B(2);
    }
    A(1); // logs 6 (1 + 2 + 3)
```

# Control flow :

control flow is the order of the statments that the computer will  execute them in that order.

In the general the code start running from first line to the last line. if there are a conditional statments or loops the code flow may change.

If there is a validate form in a webpage and the user missed a required field then the form is warning him to fill in the missed field. so the code will change its normal flow(line by line).

```

    if (field==empty) {
        promptUser();
    } else {
        submitForm();
    }
```

## References :
1. [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)

2. [Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)

3. [Control flow](https://developer.mozilla.org/en-US/docs/Glossary/Control_flow)

4. [JavaScript Functions W3school](https://www.w3schools.com/js/js_functions.asp)

5. [JavaScript Operators W3school](https://www.w3schools.com/js/js_operators.asp)





