---
layout: post
title: "Tooltips using pseudo-element 'after'"
excerpt: "CSS only tooltips using the pseudo-element 'after' and data attributes."
tags: [css]
comments: true
---

Tooltip functionality is a good way of providing instant feedback to users as they are traversing your content. In the past, for most implementations, we had to use javascript of some sort to assist with this functionality. Today, however, that's a different story.

Advances in CSS, when combined with data attributes, have made this a lot simpler. Data attributes allow us to associate data to a particular element. Once we have established these attributes we can use CSS to provide feedback to the user, in this case, with some tooltips.

Below is a sample of this in action. When you hover over any of the salmon colored text, you will see a tooltip appear, along with its associated content.

<p data-height="440" data-theme-id="0" data-slug-hash="HubdE" data-default-tab="result" data-user="greggnakamura" class='codepen'>See the Pen <a href='http://codepen.io/greggnakamura/pen/HubdE/'>::after tooltip</a> by Gregg Nakamura (<a href='http://codepen.io/greggnakamura'>@greggnakamura</a>) on <a href='http://codepen.io'>CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>
