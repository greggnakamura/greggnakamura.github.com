---
layout: post
title: "Why can't I add my .dlls to the repo!?"
excerpt: "The other day I spent the better part of an hour or so trying to figure out why the .dll files in my project were not being detected...GLOBAL GITIGNORE!!"
tags: [git]
comments: true
---

The other day I spent the better part of an hour or so trying to figure out why the .dll files in my project were not being detected.

I did have two .gitignore files in my project, but neither had rules for `[Bb]in/` or `*.dll`. I won't bore you with all of my debugging steps, but...

(╯°□°)╯︵ ┻━┻

Turns out, I had a [global gitignore](http://stackoverflow.com/questions/15515729/git-repository-ignoring-all-dlls) file in my home directory and in this file was:

    `*.dll`

I removed this rule, ran a `git status` and all the .dlls for my project were now being detected.

You can find out more about this global gitignore file in [Github Help](https://help.github.com/articles/ignoring-files/#create-a-global-gitignore).
