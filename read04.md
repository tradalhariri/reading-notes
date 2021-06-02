# What is CSS?
 css is stands for Cascading Style Sheets.Its the inspiration of the webpage.
# CSS syntax
 if we want to style any tag in css for example we need the h1 to be red we write:
` h1 {color: red;}` 

# How To Add CSS

 there are three ways to add css to webpage :
 * inline css
 we add css rule inside the tags of html
```
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
</html>
```
 * internal css
 we add css in htmlpage inside the head tag

 <!DOCTYPE html>
```
<html>
<head>
<style>
body {
  background-color: linen;
}

h1 {
  color: maroon;
  margin-left: 40px;
}
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

* external css
 we write css rules in a sparate file and link it to html file inside the head tage.

 `<link rel="stylesheet" href="mystyle.css">`


 # CSS color Property

 color property applies the color to text.

The color property specifies the color of text.
 example :

 `body {color: #92a8d1;}`
  `body {color: rgb(201, 76, 76);}`

  we can use hexadecimal mode or rgb mode for color.