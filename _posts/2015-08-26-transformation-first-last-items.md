---
layout: post
title: "Kentico: Handling First and Last items in Transformations"
excerpt: "Transformations are great for rendering content. If you need to handle the first or last item, use `DataItemIndex`"
tags: [kentico]
comments: true
---

Kentico's [transformations](https://docs.kentico.com/display/K8/Writing+transformations) are an extremely useful way of rending content using templates for DocTypes or Custom Table items.

In cases where you need to handle the first or last items in the collection, you can either use a [Hierarchical Transformations](https://docs.kentico.com/display/K8/Using+hierarchical+transformations) or `DataItemIndex`. For more complex situations I would recommend using the Hierarchical as it handles many more different types of Transformations (*first, last, header, footer, to name a few*).

For much simpler implementations, I recommend using `DataItemIndex` conditionals:

**Handle first row:**
{% highlight html %}
/* transformation: check if first record */
<%# DataItemIndex == 0 ? "First record" : "Not first record" %>

/* example: add `first` class to first item */
<%# DataItemIndex == 0 ? "<li class=\"first\">" + Eval("DocumentName") + "</li>" : "<li>" + Eval("DocumentName") + "</li>" %>

{% endhighlight %}

**Handle last row:**
{% highlight html %}
/* transformation: check if last record */
<%# DataItemIndex == DataRowView.DataView.Count - 1 ? "Last record" : "Not last record" %>

/* example: remove comma on last item for comma separated lists */
<%# DataItemIndex == DataRowView.DataView.Count - 1 ? Eval("DocumentName") : Eval("DocumentName") + ", " %>
{% endhighlight %}
