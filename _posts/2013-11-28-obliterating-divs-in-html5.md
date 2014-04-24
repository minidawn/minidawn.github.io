---
layout: post
date: 2013-11-28 21:19
title: "Obliterating divs in HTML5"
author: ravin455
---

Earlier today, I was updating an old site of mine to HTML5 and CSS3. Whilst I writing the CSS bit, I noted down something on a notepad. I wrote: _define HTML tags by the importance of it's content_. Another way to put it is use tags instead of divs. Instead of defining a `div` with an `id` or `class`, like `div.header-title`. I would stylize the `h1` tag, so to define it as my header title. Here is an example of what I did:

	<!-- old HTML.. still using divs to define sections --> 
	<div class="header">
		<div class="header-title">Hello!</div> 
	</div>

Replaced by:

	<!-- HTML5, removing the use of divs completely --> 
	<header>
   		<h1>Hello!</h1>
	</header>

This is more readable and more convenient compared to using a `div`. Typically when you define a `div` you have to choose between using `id` or `class`. Classes are for reusability and ids are for single use cases. When you replace all of this by just using a simple HTML tag, it cuts to the chase and is elegant. I wrote the CSS like this:

	header h1 { font-size: 15px; }

This could have been written like this...

	.header.header-title { font-size: 15px; }

[Original Post](http://threpo.tumblr.com/post/68365581293/obliterating-divs-in-html5)