---
layout: post
title: "Event Delegation"
excerpt: "Attach event listener to parent element, fire on all child elements that match selector"
tags: [javascript]
comments: true
---

Lets say you have a list of items and you want to find out which item was clicked when selected. You could attach an event listener to each list item, then output something when clicked.

{% highlight html %}
<ul id="parent">
    <li id="item-1">Item 1</li>
    <li id="item-2">Item 2</li>
    <li id="item-3">Item 3</li>
    <li id="item-4">Item 4</li>
    <li id="item-5">Item 5</li>
</ul>
{% endhighlight %}

Using the markup above:

**[Example #1 - Attach event listener to each list item](https://output.jsbin.com/rujofo)**

<script src="https://gist.github.com/greggnakamura/5828ede31d52c4d5b5b9.js?file=jquery-child-event-delegation.js"></script>

**Open your console**, then click any of the existing items and you will see a log output of that clicked item. However, if you add any new items using the fancy '*Add item*' button and then attempt to click that new item, you won't see anything get logged.

![screenshot of Event Delegation]({{ site.url }}/images/event-delegation.jpg)

The reason why this happens is because we have binded our click events to our existing `<li>` elements. Any new items we add will not be binded.

---

**So, how do we handle binding of existing items and any items added in the future?**

### Event Delegation

Event Delegation allows us to attach an event listener to a single parent element. Once we have established this binding to the parent, we can instruct it to fire on any matching child elements.

**[Example #2 - Attach event listerner to parent element](https://output.jsbin.com/kezota)**

<script src="https://gist.github.com/greggnakamura/5828ede31d52c4d5b5b9.js?file=jquery-parent-event-delegation.js"></script>

Following the same steps for Example #1, you can now add as many new items as you like, and each time an existing or new item is clicked, that elements information will be logged to the console.

The key part here is the second `on()` parameter, '*li*'. This is where we instruct the listener to fire when a child of `#parent` is clicked. Any match will cause our anonymous function to execute.

**What allows us to use Event Delegation is event propagation or event bubbling. You can find out more about bubbling [here](http://learn.jquery.com/events/event-delegation/#event-propagation).**
