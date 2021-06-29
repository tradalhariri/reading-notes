# Chapter 15 - Layout

* The normal flow in the html page that each block element takes the full width of the window browser and each inline element takes the width of its content and allows other inline elements to be beside it.
* we can alter this normal flow by using the css propert called `display`
* `display` has four values
  1. `display:none;` which is a normal flow.
  2. `display:relative;` by making an element relative it will be relative to where it would have been in the normal flow. you can adjust the position by setting `top,right,left,bottom` in pixeles. for example if you have a paragraph tag and its display property is set to relative, then if I  set the `left:50px` it will be a gap between 50px away from its left edge whould have been in the normal flow.
  3. `display:absolute;` when you set an element to absolute then it will be ralative to containing element.so if you set a paragraph display to absolute and this paragraph inside a div then when you set for example the `right:50px;` then the right edge for the paragrapg goes away 50px; from the inner right edge of the containig div.
  4. `display:fixed;` it is a form of absolute positioning. if you set the tag as fixed it then will be in the same place in the window so if the user scroll down or up it will be in the same place.

* we can also change the layout by using `float` property.if we set  a float propert for a tag to be left then any following element will be around the floated element.we can prevent any following element to be around a floated element by setting the `clear:both;` property.
* when designing  a website we can sit the width of that website as a fixed number of pixels or we can set a percentage.
* there are two  approches to design a website
  1. Fixed-Width Layouts: set the width of the entire page to a specific value.
  2. Liquid Layouts : the width is flexible and depends on how the the width of the browser is.