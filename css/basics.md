# CSS Basics
Although the history of CSS is less long and far less dramatic, these are still auspicious times for designers, developers, and end-users in the visual interfaces we build and use.

Cascading Stylesheets, or CSS, gives us the power to style nearly every aspect of our HTML. Where are HTML may be the bones of our web site, CSS is the skin; the outward visual experience. And now CSS3 allows for a level of interactivity that was previously only achievable with JavaScript, greatly reducing the the complication of building polished, reactive sites and interfaces.

CSS is relatively simple in its structure:

	.box {
		font-size: 14px;
		color: gray;
		width: 200px
		height: 400px;
	}
	
	a {
		color: red;
	}
	
	a:hover {
		color: orange;
	}
	
Here, we've specified that any element where the class attribute containes "box" will be given the styles between the next set of curly braces; namely, a font size of 14 pixels, a font color of "gray", a width of 200 pixels and a height of 400 pixels.

Next, any `<a>` tag in the document will be given a text color of red. That color will change to orange when hovered over.


### Selectors
CSS selectors are straight-forward. The selector is the text before the curly braces. A dot before a string indicates a class, e.g. `.container` refers to any element with the class "container". A hash mark indicates an element with that id attribute, e.g. `#main` would refer to an element whose id equals "main". I strongly recommend against styling ids, as id styles can take higher precedence over styles applied to the same element via classes. It's best not to style ids at all.

The absence of a dot or hash means that string refers to the tag name itself, as seen above.

CSS selectors will match and affect all elements that meet the criteria. It's possible, but not generally necessary to specify an element and class or id, e.g. `div.box` would only match a div with the class "box", but not a span with the same class.

### Nesting
Just as HTML elements can be nested, so too can CSS selectors:

	.box a {
		font-size: 20px;
	}

This would only affect `<a>` tags nested inside of elements who had the class "box". While extremely useful, nested selectors can get quite complicated, especially on big projects. General styles that can be broadly applied are preferred when possible.

### Specificity
CSS specificity can be rather confusing, but Chris Coyier does a fantastic job[^1] explaining the details. Make sure to read the entire thing!

### Properties
There are many, many CSS properties, and far more than we can cover in this short manual. However, there are a few in particular that you'll use constantly. Make sure you know what each of these do:

* display
* position
* width
* height
* margin
* padding
* color
* background
* float
* box-sizing
* z-index
* font-size
* line-height
* font-weight
* border-radius
* box-shadow
* text-shadow


### Layout
Doing complicated (or even simple!) layouts is by far the most difficult problem in CSS. Sometime floats work better, other times `display: inline-block`, other times box-sizing makes the most since, and sometimes none of the above. A great resource for learning the latest CSS3 layout techniques is http://learnlayout.com. Again, make sure you red the entire thing[^2].

## Resources
- [MDN Getting Started with CSS](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started) - A great primer on modern CSS.
- [LearnLayout](http://learnlayout.com) - A fantastic site for understanding CSS layouts.
- [MDN CSS Developer Guide](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS) - A collection of resources on CSS. Lots of good stuff!

[^1]: Chris Coyier on [CSS specifity](http://css-tricks.com/specifics-on-css-specificity/)
[^2]: [LearnLayout](http://learnlayout.com)