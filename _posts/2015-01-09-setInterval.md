---
layout: post
title: "Using `setInterval`"
excerpt: "`setInterval` is a handy window timer used to run some code repeatedly and uses a time delay to call a certain function. It also returns a unique ID that can be passed to `clearInterval()` to stop processing."
tags: [javascript]
comments: true
---

`setInterval` is a handy window timer used to run some code repeatedly and uses a time delay to call a certain function. It also returns a unique ID that can be passed to `clearInterval()` to stop processing.

Before I knew or realized there was a `setInterval` function, I used `setTimeout` exclusively. It was usually fine since I was using it process one thing at a time.

A while back, I was tasked with calling a function every 1/2 second, then returning its value. Without the realization of using `setInterval` here is what I initially came up with:

<script src="https://gist.github.com/greggnakamura/6a8b35d2294afaeb49d1.js?file=setTimeout.js"></script>

Immediately you can see how ugly this is. I thought to myself, *"there has to be another, cleaner way to accomplish this"*.

In talking with a colleague of mine, it was pointed out that I could, or rather should use `setInterval` in this case:

<script src="https://gist.github.com/greggnakamura/6a8b35d2294afaeb49d1.js?file=setInterval.js"></script>

Here, I'm letting `setInterval` call my `doSomething` function every 1/2 second. Then, when the count is greater than what I need, I simply call `clearInterval`, passing in the unique ID (`timer`), which stops `setInterval` from any further processing.

...and performance wise? Well, it's pretty easy to [see which is more ideal](http://jsperf.com/greggs-settimeout-vs-setinterval).

![settimeout-setinterval]({{ site.url }}/images/settimeout-setinterval.jpg)
