---
title: Post to Jekyll by Email
layout: post
---

[Speaking of baked weblogs](/2011/03/baking-website-with-jekyll/): one thing I do miss a little is the wonderful email publication interface I enjoyed with Tumblr, Posterious and even Wordpress. It should be possible to make a similar solution with some local scripting, though.

Imagine an email rule, which takes a message to a specific address, runs it through a script that extracts a title and url from the email title and body, adds a proper YAML header, saves it as a text file in your Jekyll post directory, commits it to your Git repository and pushes it to your server.

I think it definitely is doable, even though I probably can't code it myself.