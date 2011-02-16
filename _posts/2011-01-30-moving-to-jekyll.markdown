---
title: Moving to Jekyll and GitHub Pages
layout: post
---

Swedish Pixels, the very website you're reading right now, has once again grown stale. Weeds are growing in the corners, dust has settled on the furniture, the once fresh exterior has become damp and moldy. I believe there might even be an old dead raccoon, rotting and bloating under the kitchen sink, with pieces of fur falling off by the handful.

The few hours I had for writing were used for working on a fiction novel instead of this website. Everyday life consumed me. Well, it still does. However, now I feel an itch to bring this site back to life once again. Like the bird Phoenix it will rise from the ashes, bright orange and red, with a high-pitched *squeeky* cry. At least that's how it looks in my head.

I'm trying to trick myself into doing this by using one of my older methods of self-manipulation: learn a new tool, which inevitably makes me want to *use* it to actually produce something of substance.

I was time to find a new publishing system anyway. Even though I found Wordpress a very nice solution the sheer size of it made my temples hurt. I really don't need all those features. Does anyone? Really? Perhaps. Not me, though. I need (well, *want*, actually) a simple, focused and *elegant* solution. I need (want) a robust solution, that I don't have to upgrade every month.

I've also grown very fond of keeping my other writing versioned with Git. Why not do that with Swedish Pixels too, I said to myself this past Tuesday. I didn't really know *what* this solution might look like, though, so I did what I usually do when I'm lost. I watched what the smart kids---the kids I really admire---do. Right now they all seem to move away from database-driven dynamic publishing platforms to static web pages.

I tried this route once before, with [Webby][2], and rather enjoyed it. The lack of commenting drove me back to a regular CMS. The lack of commenting and my desire for tinkering, that is. I considered returning to Webby, since I had my old setup filed away in my digital archive, but alas Webby seems to be dying. Instead I turned my attention to [Jekyll][4], or rather Jekyll together with [GitHub pages][5].

Jekyll is a program written in Ruby and installing it requires some interaction with the Unix underpinnings of Mac OS X, using Terminal.app. I'm told installation usually is very straight-forward, but I did run into a few problems, before I had *Rubygems* properly updated to a more recent version.[^1] Jekyll has a few utilities for importing blog posts from a wide variety of platforms, but I never got it to work. It appears you need to have MySQL installed on your Mac, a beast almost half a gigabyte in size. I opted for a manual conversion, which was manageable, since I already had most of my older posts converted to single text files from my Webby days.

So far this solution has proven to be very nice. I write my posts in TextMate, while waiting for [Kod][3] to mature, and publish them by pushing them to a GitHub repository. Jekyll features a nice server run locally, which means it's really easy to view your changes in a browser, before you go live. Since I'm no longer dependent on PHP and MySQL the construction process went like a dream.

The only downside I've found is that GitHub Pages offer no support for a .htaccess file, which means I can't do my usual redirects and URL-rewriting. It also means I can no longer use [Mint][1] for statistics.

Anyway, a new infrastructure means a new atom-feed, which probably means you suddenly see a lot of my older posts surfacing in your RSS-readers of choice. I do apologize for that. Also, if you read this in your RSS-reader, chances are you're subscribing to my old feed at *http://swedishpixels.com/masterfeed.xml*. I would really appreciate if you took the time to re-subscribe to my new feed at [http://feeds.feedburner.com/swedishpixels/masterfeed](http://feeds.feedburner.com/swedishpixels/masterfeed).

[1]: http://haveamint.com
[2]: http://webby.rubyforge.org/
[3]: http://kodapp.com
[4]: http://jekyllrb.com/
[5]: http://pages.github.com/


[^1]: For those of you who are as lost as I am: download the latest Rubygems from [here](http://rubygems.org/pages/download) and follow the installation instructions on the same page. I recommend the manual approach (download package, unpack, go into the unpacked folder in Terminal.app and install with `ruby setup.rb`). Also, you need to have Xcode installed when you run `sudo gem install jekyll`.
