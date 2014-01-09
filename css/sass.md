#SASS

SASS, or Syntactically Awesome Style Sheets (yes you read that right), is an extension of CSS that provides an added level of power to your basic CSS allowing you to do such things as implement variables, nested rules, mixins, inline imports and much more[^1]. Gone are the days of having to change the same color in multiple places individually among other great assets to improve workflow and efficiency. 

For example, nested selectors! <br>

	
	.nested { 
		display: block;
		float: left;
	
		h1 {
			color: #e7e7e7;
		}
	}

Traditional CSS targeting:

	.not-nested {
		display: block;
		float: left;
	}

	.not-nested h1 {
		color: #e7e7e7;
	} 

There is a lot of great SASS documentation  out there that will teach you everything you would want to know about SASS and all of its great features. The links below are great starting points:
	
#####SASS Website: <http://sass-lang.com> 

#####SASS Documentation: <http://sass-lang.com/documentation/file.SASS_REFERENCE.html>

Also, Dan Cederholm is a major authority when it comes to CSS. He has written some great books on CSS and SASS. This is a great article that is definitely worth the read on why you should consider using SASS: <http://alistapart.com/article/why-sass>

[^1] : [SASS Documentation][id]
[id]: http://sass-lang.com/documentation/file.SASS_REFERENCE.html