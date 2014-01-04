# HTML Basics
HTML has been around for a while. Its history is full of political intrigue, betrayal and scandal. We won't go into that history here, but Jeremy Keith gives a great review of the sometimes foggy origins of the Hyper Text Markup Language in his book *HTML5 for Web Designers*[^1]

As the essential building block of any website or web application, mastery of HTML is crucial. Fortunately, the HTML5 Spec makes it much more powerful and flexible than its predecessors. HTML5 is backwards compatible (to an extent), and has a number of elegant fallbacks for older browsers.

In it's most basic form, HTML is a series of tags that "mark up" a document, delineating conceptual sections. For instance you might have a heading, a sub heading, and paragraph with a link in an area of a web site. That could be written as:

	<h1>Title of Story</h1>
	<h2>Super Exiting Tag Line</h2>
	<p>Lorem ipsum dolor  <a href="http://google.com">sit amet</a>, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
	
Where `<h1></h1>` are to the "Heading 1" tags, `<h2></h2>` are the "Heading 2" tags, `<p></p>` are the "Paragraph" tags, and `<a></a>` are the "Anchor" tags (also known as link tags). Note that tags can be nested to represent heirarchy and containment.

### Attributes
Attributes specify additional information about a tag. The most common attribute by far is `class`, which is used for both styling and JavaScript purposes. Here are a few examples:

	<div class="container"></div>
	<div id="main"></div>
	<a href="http://google.com">Google</a>


### The skeleton
Although no part of this is required (HTML5 Spec even allows for the validity of having no doctype at all[^2]), you'll generally find any HTML document to have at least this basic structure:

	<!doctype html>
	<html>
		<head>
	  		<title></title>
		</head>
	<body>
		<!-- main content goes here-->
	</body>
	</html>
	
The first line is the HTML5 doctype. Although it's valid to exclude the doctype in HTML5, doing so will send older versions on IE into Quirks Mode, so there's not much reason to leave it out.

Next are the `<html>` tags, inside of which all other tags will live. The `<head>` tags house meta information and generally contain links to any stylesheets. It will sometimes contain links to JavaScripts, but best practices[^3] now encourage loading most or all of your scripts just below the close of the `<body>` tag. 

### Divs

One of the most useful, and most-used tags is the `<div>` tags. It stands for "divider", and is a natural choice when building interfaces, and in situations where other tags may start to lose their semantic value. Divs can be thought of as boxes or containers, and will often be nested inside of other divs.

It's important to remember that divs are `display: block` by default, a virtue which we'll discuss further in the intro to CSS.


### The Most Common Tags
There are many HTML tags, each with their own use, meaning, and purpose. When building web apps, however, you'll see a few tags uses over and over again. Knowledge of all modern HTML is, of course, crucial, but make sure you're well aquainted with these ubiquitous tags in particular:

* html
* head
* title
* script
* link
* meta
* body
* h1, h2, h3, h4, h5, h6
* p
* span
* div
* header
* section
* aside
* footer
* a
* ul
* li
* form
* input
* textarea
* button
* canvas
* main
* article

For the full list of the *only* tags that should be used currently (i.e. non-deprecated, non-obsolete), see MDN's HTML5 Element List[^20]


### Semantic HTML and Accessibility
It's important to use *semantic* markup whenever possible. While it's possible to put just about everything in a `<div>`, tags like `<header>`, `<nav>`, `<section`, `<aside>` and their sibliings offer a great deal of clarity to the flow and importance of information when parsed by accessibility tools. Semantic HTML is especially important for users with visual impairments, as screen readers and other assistive devices can offer much more meaningful data when a site is built with accessibility in mind. 

This doesn't mean that divs should be avoided, but it does mean that you should use more sensical tags *when applicable*. The issue become even more complicated when building web apps versus building web sites. Again, Jeremy Keith's *HTML5 for Web Designers* is a good primer on writing accessible, modern HTML.

NOTE: When using new HTML5 tags, you may need to "shiv" older versions of Internet Explorer, which won't support tags it doesn't know about. Remy Sharp's html5shiv[^13] and Modernizr[^14] both solve this problem painlessly.

## Resources
- [MDN Intro to HTML](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Introduction) - Similar in structure to this document, but much more detailed. A great read.
- [MDN HTML5](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5) - A great place to go for a variety of high-quality, highly reliable resources on HTML.
- [MDN HTML5 Element List](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/HTML5_element_list) - The canonical list of HTML attributes suggested for use today.


[^1]: [HTML5 for Web Designers](http://www.abookapart.com/products/html5-for-web-designers)
[^2]: Ibid, 13
[^3]: Steve Souders' [*Evolution of Script Loading*](http://www.stevesouders.com/blog/2010/12/06/evolution-of-script-loading/)
[^13]: [html5shiv](https://code.google.com/p/html5shiv/)
[^14]: [Modernizr](http://modernizr.com/)
[^20]: MDN's [HTML5 Element List](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/HTML5_element_list)