# Chapter 4 - Links (pp.74-93)

* Links are useful when you need to navigate to other pages on your webite or when you need to navigate to other websites.
* we can also use links to navigate to specified part on the same page.
* we create linke using anchor tag `<a href="about.html">About Us</a>` . we add to `href` attribute absolute url or relative url or linked it to aspecific part on the page using `id` attribute
  
* Links are used to open email program to send an email to  specific email.
   `<a href="mailto:jon@example.org">Email Jon</a>`



# Chapter 15 - Layout (pp.358-404)
* The normal flow in the html page that each block element takes the full width of the window browser and each inline element takes the width of its content and allows other inline elements to be beside it.
* we can alter this normal flow by using the css propert called `display`
* `display` has four values
  1. `display:none;` which is a normal flow.
  2. `display:relative;` by making an element relative it will be relative to where it would have been in the normal flow. you can adjust the position by setting `top,right,left,bottom` in pixeles. for example if you have a paragraph tag and its display property is set to relative, then if I  set the `left:50px` it will be a gap between 50px away from its left edge whould have been in the normal flow.
  3. `display:absolute;` when you set an element to absolute then it will be ralative to containing element.so if you set a paragraph display to absolute and this paragraph inside a div then when you set for example the `right:50px;` then the right edge for the paragrapg goes away 50px; from the inner right edge of the containig div.
  4.  `display:fixed;` it is a form of absolute positioning. if you set the tag as fixed it then will be in the same place in the window so if the user scroll down or up it will be in the same place.

* we can also change the layout by using `float` property.if we set  a float propert for a tag to be left then any following element will be around the floated element.we can prevent any following element to be around a floated element by setting the `clear:both;` property.
* when designing  a website we can sit the width of that website as a fixed number of pixels or we can set a percentage.
* there are two  approches to design a website
  1. Fixed-Width Layouts: set the width of the entire page to a specific value.
  2. Liquid Layouts : the width is flexible and depends on how the the width of the browser is.


# Chapter 3 (first part) Functions, Methods, and Objects (pp.86-99 ONLY)

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


* Calling functions : 
to call a function we write the name of it with the indicated  parameters.


the function calling must be in the scope but the function declaration can be anywhere in program. 

```
console.log(square(5));
/* ... */
function square(n) { return n * n }
```

# Article - 6 Reasons for Pair Programming

* pair programming is methodology to increase the productivity of coding.
* How does pair programming work?
  in this methodology there are two developers first one is called driver who is responsible on writing the code and handl text editor files and version control. while the the second one is called teh navigator who is responsible on guid the driver and check the bug and thinking in the optimal solution but he dose not touch the keyboard.

 * Why pair program?
  1. Greater efficiency : when two developers focus on the same problem the will reach a solution faster than if there is a one developer.also the code that is written by pair programming takes less time when they decide to maintain later.
   
  2. Engaged collaboration : when you feel that someone depends on you to complete a task then you will do better than if you were alone. 
  3. Learning from fellow students : each developer has own approch in problem solving. when you working in pair programming you may expose other techniques to other developers.
  4. Social skills : pair programming improves not only social skills with others but also it improves the interpersonal  skills .
  5. Job interview readiness : pair programming is a better way to preparing the developer for the job interview as the employer can feel how the applicant can fit in  a team.
  6. Work environment readiness : many companies expect to training the fresh hired employees but the pair programming developer dose not need that.

 