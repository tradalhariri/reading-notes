# Chapter 7 Forms (p.144-175)

* Using the form tag we can collect information from visitors.
* How form works :
  1. the visitor enters his information in the form and then click submit.
  2. the server receive tha control form names and value ,proccess  and stores them in the database.
  3. the server may sends the webpage based on the form data.
* Form Structure : the form controls exists in the form tag and the form tag must have action attribute.the value of action is the url of the page in server to process the information. the methode attribute may have one of two values post or get. the difference between them is using get the information is appended to the url and in the post the information is not sent with the url.get is not secure because imagine that someone sends the password in the url. 
* Form Controls : 
  1. `<type input="text">`  to allow the user enter text.
  2. `<type input="password">`  to allow user enter password and it appears as small discs.
  3. `<textarea>` to allow user to enter multi line text.
  4. `<type input="radio">` to allow user to choose one of multiple choices.
  5. `<type input="checkbox">` to allow user to choose multiple of multiple choices.
  6. `<select>` to allow user drop down menu and select one of the items.
  7. `<input type="file">` to allow user upload a file from his device.
  8. `<input type="submit">` to allow user to submit the form.


# Chapter 14 Lists, Tables & Forms (pp.330-357)

* we will discuss various css rules to change the style of list ,table and form
  1. `list-style-type` to change the type of the  list item marker.
  2. `list-style-image` to change the marker to an image.
  3. `list-style-position` to set the marker inside the text we assigne `inside` to the `list-style-position`  and the default is `outside`.

* Table Properties : 
  1. `width` to set a width of the table.
  2. `padding` to set padding between cell and its content.
  3. `text-transform` to convert the heading to upercase.
  4. `border-top, border-bottom` to set a border above and below heading.
  5. `empty-cells` if we have an empty cell in the table we can use this rule to either show the border or not.


* Styling Forms :
  1. Styling Text Inputs :
     1. `font-size` to set the size of text input.
     2. `color` to set a color to the text input.
     3. `background-color` to set a background color of the text input.
     4. `border` to set a border around the text input.
     5. `border-radius` to control the corners of the text input.
  2. Styling Submit Button :
        1. `color` to change the  color of the button.
        2. `text shadow` to show the button text as 3d button.
        3. `background-color` to change the background color of the button.
   
# Chapter 6: Events  (pp.243-292)

we can make our website reponds to a certain event or responds to an event that triggers the window.
for example we can responds to load page event or click key event on the keyboard or on mouse hover around element and etc ....
we will use event listener because it is the best approach for handling the events.


```js
target.addEventListener(type, listener, useCapture);
```
the first parametr is the type of event for example `keydown` or `keyup` .
the second is a named function and it should not taken a prameters.
to solve this we can use anonymus function.
the third parameter is usually set to false .

the flow of event is important because it will determine which element will trigger first the child or the parent or the document node .

```js
var elUsername = document .getElementByid('username') ;
var elMsg = document .getElementByid('feedback') ;
II Get username input
II Get feedback element
function checkUsername(minlength) { 
if (elUsername.value.length < minlength) 

elMsg . textContent = 'Username must be ' + minlength + ' characters or more';
} else { 
}

elUsername. addEventListener( 'blur ' , function() {
checkUsername (S);
}, false) ;
```
   
