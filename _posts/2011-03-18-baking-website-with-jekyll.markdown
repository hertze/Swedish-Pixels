---
title: Baking your web site with Jekyll
layout: post
---

Brent Simmons [recently made a case][1] for "baking" your web site, by what he meant using static pages instead of dynamically generated ones. He argues web servers won't get faster soon enough to cope with the ever rising tide of traffic. Even tough this site is in no immediate danger of getting Fireballed, I agree with him. His thoughts aren't new of course, as thoughts seldom are, but they're becoming increasingly relevant. Since the idea of returning to simpler ways of publishing content aligns very well with the increasingly popular minimalism trend, I believe we're going to see more and more of this in the coming years. Dynamic publishing took of because it made it simple for *anyone* to write on the web. The pendulum is swinging the other way and now *the nerds* will lead us back to simpler times.

I've tried a lot of different publishing platforms: handcoded HTML, my own database driven system, [Textpattern][2], [Webby][3], [Movable Type][4] and [WordPress][5]. I like tinkering and learning new stuff and it has been fun. Computers and the Internet allows for joys of discovery and amazement seldom available elsewhere to a regular guy like me. I also think I've been moving around between systems because they never felt right for me. There's always been that nagging discomfort, like a pebble in your shoe. Authoring my own system was educating, but the efforts involved to keep up with security aspects of a dynamic site were too overwhelming. I really liked Textpattern---it's an awesome system---but I found myself holding my breath every time I had to upgrade the system. Movable Type and WordPress are enormous monstrosities. For me they were like firing canon balls to kill mosquitoes.

<img src="http://swedishpixels.com/bilder/filesystem.jpg" style="float:right; margin: 0 0 10px 10px;">

For the last month and a half I've been running Jekyll and for the first time in years I feel content. With my web publishing, that is.

The feeling of writing everything as text files on either of my computers, committing it to a Git repository and pushing it to [GitHub pages][6] for publications is best described as *satisfaction*. It feels incredibly robust, almost incorruptible. There are no upgrades you *have* to do. No database backups, which I always forgot anyway. No plugins to manage, no theme park of a web interface you have to sift through to make the tiniest change. I say good riddance to all of that.

I've also gotten the chance to acquaint myself better with Git, which really is a most extraordinary version control system. I now use if for all my writing, fact and fiction, for the web and for paper. I've tried most of the graphical interfaces, but keep coming back to [Gity][8].

I haven't really seen much of the theoretical down sides of static site generation. I never did publish texts from my iPhone or iPad anyway. Comments, as well as a lot of social media sharing, can be added by using javascript snipplets, provided by Disqus, Twitter, Facebook and more.

Most of my minor quibbles have had to do with Liquid, the template language used with Jekyll. If you're used to script your site with PHP or Ruby, Liquid *is* a bit limited. I also found that some Liquid code that worked great on my local Jekyll install didn't work when I sent the pages to GitHub, which was annoying to say the least.

Also, I really loathe [Maruku][7], the Markdown parser Jekyll ships with. I hope someone writes a Ruby wrapper around Fletcher Penney's MultiMarkdown 3 and adds it in the near future.


[1]: http://inessential.com/2011/03/16/a_plea_for_baked_weblogs
[2]: http://textpattern.com
[3]: http://webby.rubyforge.org/
[4]: http://www.movabletype.com/
[5]: http://wordpress.org
[6]: https://github.com/hertze/hertze.github.com
[7]: http://maruku.rubyforge.org/maruku.html
[8]: http://gityapp.com/