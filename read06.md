# JavaScript

JavaScript (JS) is a lightweight and interpreted programming language.It is known as a scripting language for Web pages.

It is  dynamic language and support OOP (Object Oriented Programming).

The standard for JavaScript is the ECMAScript.

JavaScript is different from Java.

# Input Output in plain JavaScript
The following is example of how to use the javscript for input from user and output on the webpage.

In the end of body tag we can write javascript.
We can reach any element in javascript by usin DOM (Document Object Model).
```
<html>
<head>
  <title>Hello World</title>
</head>
<body>
 
First name: <input id="first_name">
Last name: <input id="last_name">
<button id="say">Say hi!</button>
 
<hr>
<div id="result"></div>
 
<script>
function say_hi() {
    var fname = document.getElementById('first_name').value;
    var lname = document.getElementById('last_name').value;
 
    var html = 'Hello <b>' + fname + '</b> ' + lname;
 
    document.getElementById('result').innerHTML = html;
}
 
document.getElementById('say').addEventListener('click', say_hi);
</script>
 
</body>
</html>

```

# JavaScript Variables

we declare javascript variable by using var keyword.

```
var carName = "Volvo";
var carName;

```
in the above example javascript is allow to a variable to save previous value even it is declared again,
So the output for carName is still Volvo not `undefined`.

