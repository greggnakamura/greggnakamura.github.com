---
layout: post
title: jQuery Equal Heights not Equal Heightening
tags: jQuery
---

I've used [Matt Bank's jQuery Equal Heights](https://github.com/mattbanks/jQuery.equalHeights) plugin enough to know that it just works and as it's summary states, it is a "*Simple jQuery plugin to equalize heights of multiple elements on a page.*", which is absolutely true. It's simple to use!

So I was a bit shocked when it didn't work on a recent implementation. I wasn't doing anything fancy. One container, and two children, of which the Equal Heights plugin would be applied.

My markup:

	<div class="column-container">
	    <div class="content"></div>
	    <div class="aside"></div>
	</div>
Since the plugin has always 'just worked', I assumed the issue(s) were on my end...and it was, but it wasn't what I expected. JS issues, nope. CSS padding, margins, or borders maybe? Nope.

The issue turned out to be with my inclusion of Google Fonts. As the [ReadMe file (Caveats)](https://github.com/mattbanks/jQuery.equalHeights#caveats) states:

'*If using @font-face or Google Web Fonts, you may need to wrap the function call in a setTimeout for 100ms-200ms (jQuery.height() needs to fire after the font is rendered to properly calculate the height).*'

So that's what I did:

Before:

	$('.column-container').equalHeights(true);
After:

	setTimeout(function(){
    	$('.column-container').equalHeights(true);
	}, 100);
Success!!