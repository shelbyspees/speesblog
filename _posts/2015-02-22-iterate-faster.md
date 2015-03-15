---
layout: post
title: Iterate Faster
category: "tools"
---
I've read two of [Joel](http://www.joelonsoftware.com/AboutMe.html)'s books and two of [Jeff](http://blog.codinghorror.com/about-me/)'s books, plus various posts they've written that haven't been sold for money. And I've read posts from all over the internet about the software industry. I soak it up like a microfiber cloth.

A theme I've been noticing in my life lately is how important it is to be able to iterate quickly. I don't mean for-loops. I mean being able to try something, get it wrong, and try again. Trial and error IS the learning process. This has been mentioned [again](http://blog.codinghorror.com/boyds-law-of-iteration/) and [again](http://blog.codinghorror.com/go-that-way-really-fast/) on Jeff's blog and [elsewhere](http://readwrite.com/2010/09/13/does-speed-trump-quality-for-startup-iteration):

>Boyd's Law of Iteration: speed of iteration beats quality of iteration.

It doesn't matter how many Best Practices books I read, I won't get good at this without doing it a bunch of times.

Luckily I have a very expensive and very fast computer to help me with that. And it does for the most part. But there have been a few situations lately that have slowed me down considerably.

The most frustrating one has got to be my data structures assignments. I can't compile and run them locally on Eclipse. I've tried every kind of configuration. I just keep getting

    Launch failed. Binary not found.

I've gone through like eight different ways to configure the compiler and the project. I think Eclipse just doesn't like being used for C on a Mac. One or the other, but not both.

I'm sure if I gave myself more time to do these assignments I'd have figured out a solution by now. But of course, I'm a student. The whole point of school is to be given arbitrary deadlines to improve how well I perform under pressure at the last minute.

Since most of my assignments are due at midnight Sunday night, this means I'm frantically trying to understand and implement this new data structure as the sun is setting on my weekend. And while Eclipse can helpfully point out dumb errors in my code, like naming errors and missing return statements, it won't help me out by compiling and running the tests that'll tell me whether I actually coded it correctly.

So I get to a point where I feel like my code should pass the tests, and

- connect over SSH to my school server
- send my files to the server on a friendly FTP browser
- wait for the files to load and then `cd` into the directory (because to hell if I'm reorganizing all my files each time I drag them over, and of course I need them all to compile anyway)
- run `make` and wait for errors (sometimes it actually compiles and I get a `segmentation fault: core dump`, or real test data!)
- try to fix those errors back on my local copy in Eclipse.
- Rinse, and repeat.

The compile errors are more annoying than the failed test cases for some reason. Oh yeah, because it's always supposed to compile the first time. Duh.

I know I'm doing something wrong. But I can't bring myself to edit the files directly in vim on the school server. I like my syntax highlighting, and we're supposed to be using an IDE for this class anyway.

But yeah. That whole process is such a huge pain, and it seriously breaks up my train of thought when I'm trying to fix the code. I'm lucky the assignments I'm doing are really tiny. Because it's not like I'd ever encounter impediments like this in the real world, right?

...Right?

---

Update: [I figured it out.]({{ site.url }}{% post_url 2015-03-12-makefile-project %})