# Chapter 3 - Lists

HTML provide us with three types of lists.

* Ordered List
  
  To insert ordered list into your html file use `ol` tag and each item in the list should be surrounded by li `tag`.

    ```html
    <ol>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
    </ol>
    ```


* Unordered List
  
    To insert unordered list into your html file use `ul` tag and each item in the list should be surrounded by li `tag`.

    ```html
    <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
    </ul>
    ```

* Definition List
  
    To insert definition list into your html file use `dl` and between the opening `<dl>` tag and closing tag `</dl>`  insert `<dt>` which it is used to insert definition term and below of each `<dt>` you can insert `<dd>` tag which is used to insert definition.

    ```html
    <dl>
    <dt>Sashimi</dt>
    <dd>Sliced raw fish that is served with
    condiments such as shredded daikon radish or
    ginger root, wasabi and soy sauce</dd>
    <dt>Scale</dt>
    <dd>A device used to accurately measure the
    weight of ingredients</dd>
    <dd>A technique by which the scales are removed
    from the skin of a fish</dd>
    <dt>Scamorze</dt>
    <dt>Scamorzo</dt>
    <dd>An Italian cheese usually made from whole
    cow's milk (although it was traditionally made
    from buffalo milk)</dd>
    </dl>
    ```
# Chapter 13 - Boxes

Using css we can control the display of any tag . as we know each tag by default resides in a box with 0 px width.

* we can adjust the dimensions of the box by changing the height and width of that box using css.
  
* we can also control the dimentions of the box when the browser window shrink or stretch by using `min-width, max-width`
  
* if we use `min-height, max-height` to adjust the height of box we maybe make the appearing of the box look messy. to avoid that we can use the `overflow` property which takes two values `hidden` or `scroll`.
  
* we use margin to insert gaps between tow boxes on the page. and the margin is added to the width of the box.
* we use padding to add space between border of the box and its content.
* The border of the box by default has 0 pixel. we can change that by setting border width 
* there is a shorthand property for the border
  `border: 3px dotted red;` 
  1. 3px is the border width .
  2. dotted is the border style.
  3. red is the border color.
  

  


* To center a box inside another we give the inner box a width and set the left and right margins to auto.
* there are four values for display propert
  1. display:inline; which convert block element to inline element
  2. display:block; which convert inline element to block element
  3. display:inline-block; which makes the element as a block where we can change its width and as inline where it dose not block elements from being beside it.
  4. display:none; the element disappears.


* The difference between the `visibility:hidden;` and `display:none` is the first will make the box hidden but it will keep its space but the second will make the box hidden with its space.
  


# Chapter 2 - Basic JavaScript Instructions (pp.70-73)

* USING QUOTES INSIDE A STRING 
  1. String can be inside single quotation marks '' or double quotation marks "". If we want to add quotation marks inside string we need to use opposite inside and outside.
  2. we can also use backslash to escape the quotation marks.
   

* USING A VARIABLE TO STORE A BOOLEAN 
  The boolean value takes true or false .we always use the boolean variables in conditional statements so this data type is important.

* SHORTHAND FOR CREATING VARIABLES
  we can create variables in javascript in more than one way.
  1. we can first declare variables in one line and then we can assigne them a value in seperate lines.
  2. we can declare each variable and assigne it a value in the same line.
  3. we can declare and assigne a values to two variables in the same line.
* we can change the value of the variable in any place of script after we declared it.
  


## Chapter 4 - Decisions and Loops from switch statements on (pp.162-182)

* Switch Statement
  
  we can use switch statement to check variable against many possible outcomes . switch statement is faster then many if statements because when the case matches it will finsh the execution of the switch block while in many if statements the intereptor will check every if statement.

* TYPE COERCION & WEAK TYPING
  the javascript is a weak typing language because it convert unexpected data type to complete the operator

    ```js
    ('1' > 0).
    ```

     here the one is treated as a number and the statement is evaluated to true and this known as type coercion.
 

