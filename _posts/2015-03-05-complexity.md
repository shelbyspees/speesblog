---
layout: post
title: Complexity
category: best_practices
---

This is an excerpt from a book called [<i class="fa fa-book"></i> *Facts and Fallacies of Software Engineering*](http://www.amazon.com/Facts-Fallacies-Software-Engineering-Robert-ebook/dp/B001TKD4RG/ref=tmm_kin_title_0?_encoding=UTF8&sr=8-2&qid=1424666218) by Robert L. Glass. This section really stood out, and it does a good job of combining a lot of the points in the book.

I can't believe this book was published in the 90s. I guess hardware and software change, but people don't change at all.

---

>**Fact 21:** For every 25 percent increase in problem complexity, there is a 100 percent increase in complexity of the software solution. That's not a condition to try to change (even though reducing complexity is always a desirable thing to do); that's just the way it is.

####Discussion

This is one of my favorite facts. It is a favorite because it is so little known, so compellingly important, and so clear in its explanation. We've already learned that software is very difficult to produce and maintain. This fact explains why that is so.

It explains a lot of the other facts in this book, as well.

* Why are people so important?
	- Because it takes considerable intelligence and skill to overcome complexity.
* Why is estimation so difficult?
	- Because our solutions are so much more complicated than our problems appear to be.
* Why is reuse-in-the-large unsuccessful?
	- Because complexity magnifies diversity.
* Why is there a requirements explosion (as we move from requirements to design, explicit
requirements explode into the hugely more numerous implicit requirements necessary to produce a workable design)?
	- Because we are moving from the 25 percent part of the world to the 100 percent part.
* Why are there so many different correct approaches to designing the solution to a problem?
	- Because the solution space is so complex.
* Why do the best designers use iterative, heuristic approaches?
	- Because there are seldom any simple and obvious design solutions.
* Why is design seldom optimized?
	- Because optimization is nearly impossible in the face of significant complexity.
* Why is 100 percent test coverage rarely possible and, in any case, insufficient?
	- Because of the enormous number of paths in most programs and because software complexity leads to errors that coverage cannot trap.
* Why are inspections the most effective and efficient error removal approach?
	- Because it takes a human to filter through all that complexity to spot errors.
* Why is software maintenance such a time consumer?
	- Because it is seldom possible to determine at the outset all the ramifications of a problem solution.
* Why is "understanding the existing product" the most dominant and difficult task of software maintenance?
	- Because there are so many possible correct solution approaches to solving any one problem.
* Why does software have so many errors?
	- Because it is so difficult to get it right the first time.
* Why do software researchers resort to advocacy?
	- Perhaps because, in the world of complex software, it is too difficult to perform the desperately needed evaluative research that ought to precede advocacy.

Wow! It wasn't until I began constructing this list that I really realized how important this one fact is. If you remember nothing else from reading this book, remember this: 

**For every 25 percent increase in problem complexity, there is a 100 percent increase in the complexity of the software solution.**

And remember, also, that there are no silver bullets for overcoming this problem. Software solutions are complex because that's the nature of this particular beast.