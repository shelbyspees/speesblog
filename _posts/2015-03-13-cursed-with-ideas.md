---
layout: post
title: Cursed With Ideas
category: musings
date: 2015-03-13 23:00:00 -0800
---

Of course I can't get anything done sitting in a hospital waiting room with daytime television blaring in the background. But as soon as I get in bed in my dark, quiet room the ideas start flowing.

In the dark of the night, I'm doomed to be attacked by my thoughts.

<iframe width="420" height="315" src="https://www.youtube.com/embed/Ocm8QdNR_d8" frameborder="0" allowfullscreen></iframe>

(Yeah I've been listening to the *Anastasia* soundtrack on my commute. I had forgotten how great/cheesy the music is.)

Things to do:

####<i class="fa fa-square-o"></i> Fix Reading page so that each book has the cover image on the left and the information on the right, like this:

![TCP/IP For Dummies]({{ site.url }}/assets/comp/reading.png)

This is going to involve a lot of steps I think, unless I want to rewrite the entire page in pure HTML:

- Create a [YAML object](http://en.wikipedia.org/wiki/YAML#Examples) for each book with the following attributes:
	- cover_image
	- title
	- link_url
	- author
	- status [<i class="fa fa-check-square-o"></i> **Completed**, <i class="fa fa-refresh"></i> In Progress, <i class="fa fa-ellipsis-h"></i> *Not Started*]
	- description
- Use [Liquid](http://docs.shopify.com/themes/liquid-documentation/basics) to populate the data for each book into the HTML
	- I'm simultaneously terrified at the idea of finally automating web things for the first time and relieved that at least I get `if` statements and `for` loops. Someday I'll look back on this and shake my head
- Get a PhD in [CSS](http://i.imgur.com/Q3cUg29.gif) in order to figure out how to arrange things horizontally

It's 1:42am. I have my data structures final in ~32 hours. Two huge assignments due in 46 hours. Ugh tomorrow is going to suck.

####<i class="fa fa-square-o"></i> Super neat DS&A tutorial web app project

This is way over my head at this point, but I like the idea and I'll learn a lot of cool stuff in the process.