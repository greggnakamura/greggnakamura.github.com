---
layout: post
title: "Error: `libsass` bindings not found"
excerpt: "Try reinstalling `node-sass`? Warning: Task 'sass:server' failed. Use --force to continue."
tags: [javascript, node, yeoman]
comments: true
---

Ran into this error when firing up a Yeoman App and attempting my first `grunt serve`.

{% highlight powershell %}
Warning: Loading "sass.js" tasks...ERROR
Error: `libsass` bindings not found in C:path\to\node_modules\grunt-sass\node_modules\node-sass\vendor\win32-x64-11\binding.node. Try reinstalling `node-sass`?
Warning: Task "sass:server" failed. Use --force to continue.
Aborted due to warnings. Use --force to continue.
{% endhighlight %}

Initially, I removed my entire `node_modules` directory, then ran `npm update`...to no avail ([reference](http://stackoverflow.com/questions/28409100/try-reinstalling-node-sass-on-node-0-12#answer-28974608)).

<hr>
> **Note**, if you are on a Windows machine, you may run into a `path too long to be deleted` error when attempting to delete your `node-modules` directory. If you do, one solution you may want to try is to create a **subst** directory ([reference](http://superuser.com/questions/755298/how-to-delete-a-file-with-a-path-too-long-to-be-deleted#answer-755301)).
<hr>

After [further review](http://stackoverflow.com/questions/29461831/libsass-bindings-not-found-when-using-node-sass-in-nodejs#answer-29624362), I ran `npm rebuild node-sass`, which did end up resolving my `libsass` binding error.

I'm not 100% sure why running `rebuild` worked so if anyone is willing to provide a thorough explanation, I would appreciate it. `rebuild` is used to recompile addons, but I'm still a little fuzzy on why this is actually was needed.




