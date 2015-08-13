---
layout: post
title: "jQuery Migrate to the Rescue!"
excerpt: "Use jQuery Migrate to APIs and features removed from jQuery core "
tags: [javascript]
comments: true
---

**If you ever find yourself working on an application where you need jQuery 1.9+, but the system you are building the application on requires anything below jQuery 1.9, you may run into system errors such as I did recently. **

`Uncaught TypeError: Cannot read property 'msie' of undefined`

**The error was thrown because of this**: "The `$.browser` method has been removed as of **jQuery 1.9**."

As of jQuery 1.9 many [APIs and features](http://jquery.com/upgrade-guide/1.9/#changes-of-note-in-jquery-1-9) from jQuery core were either removed or deprecated.

<script src="http://code.jquery.com/jquery-migrate-1.2.1.js"></script>

Uncaught TypeError: Cannot read property 'msie' of undefined

http://stackoverflow.com/questions/14923301/uncaught-typeerror-cannot-read-property-msie-of-undefined-jquery-tools
