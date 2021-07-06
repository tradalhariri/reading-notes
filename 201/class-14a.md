# Transitions & Animations

* Transition : with transition you can alter the behaviour of an element when it changes from state to another.the transition has 4 properities in total 
  1. transition-property : determine on which element property the transition is applyied.
  2. transition-duration : determines how long the transition .
  3.  transition-timing-function : determines the behaviour of the transition for example will it begin fast and end slow or vice versa.
  4. transition-delay : determines how long will the transition being stalled before it begin.
   
<iframe height="300" style="width: 100%;" scrolling="no" title="Transition Delay" src="https://codepen.io/shayhowe/embed/naDEp?defaultTab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/shayhowe/pen/naDEp">
  Transition Delay</a> by Shay Howe (<a href="https://codepen.io/shayhowe">@shayhowe</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>


# Animations 

* To determin multiple points the element should transision we use the @keyframe followed by animation name.
* animation duration determines how long time the animation will take.

* animation-timing-function: determines the behaviour of the animation.

* animation-delay determines how long will the animation being stuck until it begins .

<iframe height="300" style="width: 100%;" scrolling="no" title="Animation" src="https://codepen.io/shayhowe/embed/fochl?defaultTab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/shayhowe/pen/fochl">
  Animation</a> by Shay Howe (<a href="https://codepen.io/shayhowe">@shayhowe</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

* Customizing Animations
  1. Animation Iteration : animation is repeated once by default if you want to repeate the animation you can use the property `animation-iteration-count`. the value of this property is eaither number or `infinite` keyword.
  2. Animation Direction : you can set the direction the animation will follow it by using `animation-direction` property.This property takes on of four values . 
      1. `normal` - which is the default.
      2. `reverse` - it works opposite the keyfram starting from 100% and ending at 0%;
      3. `alternate`  - make the animation go from 0% to 100 % then go back from 100% to 0%;
      4. `alternate-reverse` - it combines between `reverse and alternate`

<iframe height="300" style="width: 100%;" scrolling="no" title="Animation Direction" src="https://codepen.io/shayhowe/embed/xpigK?defaultTab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/shayhowe/pen/xpigK">
  Animation Direction</a> by Shay Howe (<a href="https://codepen.io/shayhowe">@shayhowe</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>




# Transforms 

* 2D Transforms : first we discuss the 2d transform on 2d plane which represents `X , Y` .

1. 2D Rotate : you can rotate element around its center by using rotate. and the positive value will rotate the element in the clockwise direction and negative value will do the opposite.
      


          
<iframe height="300" style="width: 100%;" scrolling="no" title="Rotate" src="https://codepen.io/shayhowe/embed/AKDIp?defaultTab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
See the Pen <a href="https://codepen.io/shayhowe/pen/AKDIp">
Rotate</a> by Shay Howe (<a href="https://codepen.io/shayhowe">@shayhowe</a>)
on <a href="https://codepen.io">CodePen</a>.
</iframe>

  2. 2D Scale : you can use scale value to make an element appearing smaller or bigger . the default is one and any value less than one will enlarge the element and any value above one will make it smaller. you can also scale either width or height using `scaleX` or `scaleY`

  <iframe height="300" style="width: 100%;" scrolling="no" title="Scale" src="https://codepen.io/shayhowe/embed/khtnm?defaultTab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/shayhowe/pen/khtnm">
  Scale</a> by Shay Howe (<a href="https://codepen.io/shayhowe">@shayhowe</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>


 3. 2D Translate : you can move an element into horizental , vertical or both directions using translate.

 <iframe height="300" style="width: 100%;" scrolling="no" title="Translate" src="https://codepen.io/shayhowe/embed/LqHwt?defaultTab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/shayhowe/pen/LqHwt">
  Translate</a> by Shay Howe (<a href="https://codepen.io/shayhowe">@shayhowe</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

 4. 2D Skew : it is used to distort the element either on horizentall , vertical or both axies.

 <iframe height="300" style="width: 100%;" scrolling="no" title="Skew" src="https://codepen.io/shayhowe/embed/GHwCK?defaultTab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/shayhowe/pen/GHwCK">
  Skew</a> by Shay Howe (<a href="https://codepen.io/shayhowe">@shayhowe</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>



* Transform Origin : used to change the default transform origin of the element which is at the center of element 50% of both directions.

<iframe height="300" style="width: 100%;" scrolling="no" title="Transform Origin" src="https://codepen.io/shayhowe/embed/uavIn?defaultTab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/shayhowe/pen/uavIn">
  Transform Origin</a> by Shay Howe (<a href="https://codepen.io/shayhowe">@shayhowe</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>

* Perspective : you can think of the perspective  as it is the point of viewer and it is important in the 3d tranformation. and the higher the value we assigned to it the more clear to see an element from all sides.

<iframe height="300" style="width: 100%;" scrolling="no" title="Perspective Depth Value" src="https://codepen.io/shayhowe/embed/ihjFA?defaultTab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/shayhowe/pen/ihjFA">
  Perspective Depth Value</a> by Shay Howe (<a href="https://codepen.io/shayhowe">@shayhowe</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>


----
[Transition & Animation](https://learn.shayhowe.com/advanced-html-css/transitions-animations/)

[Transforms](https://learn.shayhowe.com/advanced-html-css/css-transforms/)



