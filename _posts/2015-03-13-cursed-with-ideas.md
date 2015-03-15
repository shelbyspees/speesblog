---
layout: post
title: Cursed with Ideas
category: musings
date: 2015-03-13 23:00:00
---

Of course I can't get anything done sitting in a hospital waiting room with daytime television blaring in the background. But as soon as I get in bed in my dark, quiet room the ideas start flowing.

In the dark of the night, I'm doomed to be attacked by my thoughts.

<iframe width="420" height="315" src="https://www.youtube.com/embed/Ocm8QdNR_d8" frameborder="0" allowfullscreen></iframe>

(Yeah I've been listening to the *Anastasia* soundtrack on my commute. I had forgotten how great/cheesy the music is.)

Things to do:






<h3 class="anchor" id="reading-page"><i class="fa fa-check-square-o"></i> Fix Reading page</h3>

--> Update: I ended up doing it the cheap Markdown way using tables and a bit of CSS to adjust the cell width site-wide. Eventually I'll do it the proper automated way.

Fix Reading page so that each book has the cover image on the left and the information on the right, like this:

<img class="wide" src="{{ site.url }}/assets/comp/reading.png"/>

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





<h3 class="anchor" id="d-s-and-a"><i class="fa fa-square-o"></i> Super neat DS&A tutorial web app project</h3>

This is way over my head at this point, but I like the idea and I'll learn a lot of cool stuff in the process.

Features:

- Interactive UI (think [Duolingo](https://www.duolingo.com/) or [RegExr](http://www.regexr.com/))
- Straightforward explanations of benefits and applications of each data structure/algorithm aimed at first-year CS students or self-taught programmers
- Replace walls of text with visualizations and tooltips
- IDE experience with debugger-like walkthrough of each function with parallel animation
- 
- Animated visualizations to demonstrate logic
	- E.g. Using color gradients to visually represent numerical values. An array should look like a [paint chip](http://sugarluxeblog.com/wp-content/uploads/2009/01/paint-chips.jpg) after it's been sorted, with the numerical values there to verify correct sorting
	- Step-by-step animations. Imagine having arrows there to show adding or removing a value from a linked list, or percolating up and down a heap. Basically like the Blue's Clues of CS.
- (Eventually?) user accounts to save progress, like codecademy, etc.

Things I'll have to learn:

- Building a web app from the ground up
- How to make a web-based IDE. Ouch
- Animated visualizations (probably using a tool like [this](https://animatron.com/))
- How to make the animation and IDE features responsive
- Data structures
- Algorithms
- C implementation of DS&A
- C++ implementation of DS&A
- Java implementation of DS&A

I'm also thinking of adding grammar lessons in the languages I know. Once a teacher, always a teacher, amirite?










<h3 class="anchor" id="job-hunting"><i class="fa fa-square-o"></i> Posts on job hunting</h3>

I've read, saved, retweeted, analyzed dozens of articles on the job application process, from writing your LinkedIn header to deciding on what to wear the day of the interview. I don't want all that knowledge to go to waste. Plus what better way to procrastinate than to summarize the articles I methodically collected while--you guessed it--procrastinating.

- Job application advice posts
	- Cover letter
	- Resume
	- [Interview prep]({{ site.url }}{% post_url 2015-03-14-interview-prep %})
	- Career fair prep
- musings: Employment is a relationship
- Respond to common interview questions
	- [Part I]({{ site.url }}{% post_url 2015-03-14-interview-questions-part-one %})