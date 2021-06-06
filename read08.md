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

# Loops and iteration : 
  we use the loop to do a task several times. without the loops the code might be longer.

* for statement :
the for statment is used when we know how many iterations the task require.

example : 
```
for (i = 0; i < 5; i++) {
  console.log("hi");
}
```

the above example will start from i = 0 then check the condition 'is i < 5' if yes enter the loop and execute the statments then Incrementm i by 1 and repeate the previous senarion until the condition becomes false.

* do...while statement : 
 
 The general syntax of it is 

```
 do
  statement
while (condition);

```

it ensures that the statement is executed once atleast before checking the condition .


```
let i = 0;
do {
  i += 1;
  console.log(i);
} while (i < 5);


```

* while statement : the general syntax is 

```
while (condition)
  statement

```  

the while statement dose not execute the statement untill check the condition to be true.

the difference between the while statement and the do...while statement is in do...while statement there is atleast one itaration that must be executed before checking the condition.


```
let n = 0;
let x = 0;
while (n < 3) {
  n++;
  x += n;
}

```

first iteration : n = 1 and x = 1
second iteration: n = 2 and x = 3
third iteration: n = 3 and x = 6

## References :


1. [Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)

2. [Loops and iteration](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)
