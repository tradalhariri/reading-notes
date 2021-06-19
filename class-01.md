# Introduction to HTMl

## How Websites Are Created

To create small and simple websites you just need to learn html ,css and maybe javascript but for the  complex websites you maybe need to learn extra knowledge like backend technologies and databases.

## How the Web Works

when you type any url in your browser say it is [www.google.com](www.google.com) the following scenario is what happens:

* First your browser will send a message to ISP ( Internet Service Provider like zain company ) that it needs to reach google.com.
* ISP then sends that request to DNS server ( whick works like phone book each website name is corresponded to a number called IP address).
* once the IP address of google.com has been obtained by ISP then the ISP sends that IP to the browser.
* then the browser can now talk with the server that hosts the google.com.
* Finally the server that hosts the google.com will send the html and css and other files to that browser.

all of that scenario happens in seconds.


# HTML Chapter 1 - Structure:

* **HTML Uses Elements to Describe the Structure of Pages**
The browser can understand what to show on it through html tags. html tag tell the browser how to display the content inside of it.

for example :

`<p>paragraph 1</p>` the browser knows that p means paragraph and so on.

most of html tags consists of opening tag ,closing tag and the content between opening and closing tag.

* anything inside opening `<html>` and closing `</html>`  is html code.
* anything inside opening `<body>` and closing `</body>`  is what to appear on the browser window.
* anything inside opening `<title>` and closing `</title>`  appears on the browser tap.
* anything inside opening `<h1>` and closing `</h1>`  appears as a main heading.
* head tag contains information about the page.

example:

```<html>
<head>
<title>This is the Title of the Page</title>
</head>
<body>
<h1>This is the Body of the Page</h1>
<p>Anything within the body of a web page is
displayed in the main browser window.</p>
</body>
</html>
```

In the opening tags we may iclude attributes.The attribute give the browser more information about the tag.

example:
`<p lang="en-us">Paragraph in English</p>` the `lang=en-us` attribute inside `p` tag indicate that the language for this paragraph is English.



# HTML Chapter 8 - Extra Markup:

* There are more than one version from html but we will use fifth version  of html. 

`<!DOCTYPE html>`  this line of code tells the browser that we are using html 5 version.

* To comment anything inside html code document just put it inside of `<!-- here we can add any comment -->` so that comment will not appear on the browser window.

* Every element has the `id` attribute but the value of each element must be different from other elements. in other words the id is the identifier of html tag.

* class attribute is used to group the elements that sharing in one thing. we can assign the element more than one class but not more than one id value.

* Block elements : they block every thing from being beside them and take the whole width of screen.

some examples of block elements are `p , h1 , div, ul, ol`.

* Inline elements : they stacked beside eath other and take the width as much as its content. 

some examples of block elements are `a, img`.


* iframe tag: it stands for inline frame and used to embed a page inside another. It can be useful when displaying the google map.
the i farme tag has some attribute like:
  1. src : the source of the page that we need to embed inside another page.
  2. height : height of iframe.
  3. width : width of iframe.
  4. scrolling : not supported in html 5. it is important when the embeded page is larger than the height of iframe.

  
* Information About Your Pages

`<meta>` element is an empty tag or self closed tag that it dose not need a closing tag.
it used inside head tag and used to provide information about the website to the SE (Search Engine).
So ranking of the website can improve.

* Escape characters 

we can use escape characters to display some characters inside the webpage like `<>, ©`.


# HTML Chapter 17 - HTML5 Layout

in the traditional layout the developers need  to divide the page using `div` tag and use id or class for each section of the page.
HTML 5 introduced new elments that do the same thing but with the semantic of their names.

Some of new html layout elements :

`<header> and <footer>` they  can be used to represent header and footer for the main page or for specific section of the page.
`<nav>`is used to group main navigation links of the website.
`<aside>` has two purposes whether it is inside `<article>` or not. if it is outside the article tag it acts as a container to display contents related to the entire page like search box or links to other pages.
`<section>` it is used to group content together.
`<hgroup>` it is used to group the heading elements such as h1, h2, h3 .... and considered as one heading.


* Helping Older Browsers Understand

older browsers will tackle the new html 5 elements as an inline elements so we need to add the following rule css.
```header, section, footer, aside, nav, article, figure
{
display: block;
}
```

IE9 can style these elements using css but the older versions of it cannot so we need to add the following javascript known as html5 shiv.

```<!--[if lt IE 9]>
<script src="http://html5shiv.googlecode.com/svn/
trunk/html5.js"></script>
<![endif]-->
```

# HTML Chapter 18 - Process & Design


# Introduction

# JS Chapter 1 - The ABC of Programming











