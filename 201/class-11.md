# Chapter 16 - Images -(pp.406-427)

* controlling the size of images in CSS : the best practice is to define the sizes of all images inside your website small , medium , larg in sperated classes and use these classes in the `img` tag ....
  
    ```css
    img.large {
    width: 500px;
    height: 500px;}
    img.medium {
    width: 250px;
    height: 250px;}
    img.small {
    width: 100px;
    height: 100px;}
    ```

* aligning images using CSS : you can use float property to align image wither right or float. but you need to align image in center of its container you should turn the `display` property to `block` and then  use one of the following two ways.
   1. use `text-align:center;` in the containing element.
   2. or you can set margin of right and left to auto. `margin: 0px auto;`

* bachground image : you can set a background image for any element using the property `background-image` 
  
    ```css
    body {
    background-image: url("images/pattern.gif");
    }
    ```

* repeating  image : the default is to repeate the image horizentally or vertically unless you don't set the property `background-repeat` . the `background-repeat` have four values 
   1. repeat-x : repeate an image horizentally.
   2. repeat-y : repeate an image vertically.
   3. no-repeat : repeat image in both directions horizentally and vertically.
   4. no-repeat : showing the image once.

* `background-attachment` has one of two values :
   1. `fixed`  which makes the image in fixed position when the user scroll up or down .
   2. `scroll` when the user scroll up or down it stay in its own position and id dose not scroll with the user.
   
* `background-position` if the image is not repeating you can use the `background-position` to set position image horizentally and vertically . it has pair of values the first points to horizental direction and the second is points to the vertical direction .
  
    ```css
    background-position:left top;
    background-position:left center;
    background-position:left bottom;
    background-position:center top;
    background-position:center center;
    background-position:center bottom;
    background-position:right top;
    background-position:right center;
    background-position:right bottom
    ```

# Chapter 19 - Practical Information  (476-492)

* SEO (Search Engine Optimization) : it is important for you to make your website appearing in the first results when a user search on a search engine like Google .
* in your page there are seven places where you should put your keywords :
  1. Page Title in the `head` tag
  2. url 
  3. heading 
  4. text
  5. link text
  6. image alt text
  7. description in the `meta` tag inside `head` tag


* there are some tools help you to analysis your visitors behaviours such as the number of visitors and what the do when they were in the website (Google Analytics)

* to put your website on the internet you should  purchase a domain name and hosting storage.


# Video and Audio APIs

* HTML5 provides media elements such as `<video> and <audio>` 
  
    ```html
    <video controls>
    <source src="rabbit320.mp4" type="video/mp4">
    <source src="rabbit320.webm" type="video/webm">
    <p>Your browser doesn't support HTML5 video. Here is a <a href="rabbit320.mp4">link to the video</a> instead.</p>
    </video>
    ```

the attribute `controls` is used to show controls and effect of this attribute may differ from  one browser to another so the best practice is to remove it and build your own controls using css.

* if you build your own controls you should then implement your own javascripts event listener to your custom css controls.


* References [Video & Audio HTML5](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Video_and_audio_APIs)

