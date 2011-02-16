---
title: The MultiMarkdown Gospel
layout: post
---

When it comes to writing tools there are those that are nice to have and those I can't imagine ever doing without. [Fletcher Penney][1]'s [MultiMarkdown][2] (MMD) is one of the latter. I would even go so far as to divide my computing life into *before* and *after* MMD.

I rarely use a word processor these days. Everything I write---notes, fiction and academical prose---is written as plain text files in MultiMarkdown syntax and transformed into beautifully typeset PDFs, with LaTeX as an intermediary step. The exact same document can be output as XHTML for the web, as an PDF or as an RTF-file for further formatting elsewhere. It's truly content separated from form.

Right now Fletcher seems to be busy [beta testing MMD 3][3], which is a complete rewrite in C. MMD 2 is a Perl program, and as such a bit slower. I never had any problems with the this, though. I have always been able to afford waiting a few seconds for a 60.000 word manuscript to parse. As I understand it Fletcher is doing the new version for the future---a future with iOS in mind. Perl has no place on our iDevices.

I must confess I haven't tried the MMD 3 betas yet. The new version in C does things a bit differently when it comes to modifying the output and right now I've tweaked the XSLT-files of the ageing MMD 2 to suit my needs just perfectly. One of these days I'll have to make the transition, but once I start I know the fidgeting monster-nerd in me will eat my life until I have it all figured out. I can't afford that right now. Not when I'm trying to write an academic paper.

From his work I know Fletcher to be a really smart guy. I'm sure MMD 3 will be even greater than it's predecessors. I too hope to see MMD on my iPad in the not-to-distant future---in one form or the other. I also hope for MMD 3 to be the default Markdown parser in [Jekyll][4][^1], since I don't care much for [Maruku][5] or [RDiscount][6].

[1]: http://fletcherpenney.net/
[2]: http://fletcherpenney.net/multimarkdown/
[3]: http://groups.google.com/group/multimarkdown/browse_thread/thread/26e70675588de41e
[4]: http://jekyllrb.com/
[5]: https://github.com/nex3/maruku
[6]: https://github.com/rtomayko/rdiscount

[^1]: Someone would need to write a Ruby wrapper around MMD, the same way that RDiscount is a wrapper around Discount. Are you that someone?