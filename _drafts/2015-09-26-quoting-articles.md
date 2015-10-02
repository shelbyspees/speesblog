---
layout: post
title: Quoting Articles
---

So lately there have been a lot of articles that I want to quote. Things about company culture, management practices, how to succeed or fail on projects. There are a few common themes that I keep coming across and I'd like to round up the quotes and sort of synthesize them into a couple different posts.

Okay.

## People # TODO

One thing that I've encountered is that no technology, no methodology, nothing can substitute or supplement good people. You need quality people to create quality products, especially in software where it's all knowledge work. It's all thinking. Sure, you can automate things. But the only way to tell if you're going in the right direction is by trusting in those good people.

In Reginald Braithwaite's book [*What I've Learned from Failure*](https://leanpub.com/shippingsoftware/read), Braithwaite tells the story of 

## Features

Minimal iterations. Testing--unit tests, integration tests, user acceptance tests--for every iteration.

Braithwaite writes about the difference between increments and iterations:

>Increments are components of the finished software that do not provide value in and of themselves

They're easy to measure, but those metrics have little meaning or value:

>Are you going in the right direction? Who knows, but you know you how fast you are going, and that is worth something, isn’t it? I can tell you exactly what it is worth. At some meeting later on, when the project has been judged an expensive failure, you can prove it was a well-managed failure under your watch. Congratulations.

That really spoke to me. **It doesn't matter how well-managed your project is if you're building the wrong product.**

How do you know you're building the right product? Ask your customer. This is a lot easier when your product is a teeny tiny piece of value you can implement and test to see if it's even necessary. This is where iterations come in:

>An iteration is a piece of software with business value. People can touch it, try it, use it, and judge how well it does or doesn’t help the business execute. This is different in every way from an increment. I call iterations “products.” If something cannot be called a product, it probably isn’t really delivering any value.

So the most effective way to organize your project into milestones is to break it up into tiny baby projects where each one creates a viable product on its own. At the very least, showing your customer a viable product at each of these milestones gives you an excuse to pick their brains--because we all know that you're never going to get the whole story of what they need easily. The more time you spend asking customers questions the better you'll be able to deliver solutions to their needs.

Maybe you completely misunderstood the customer's needs and you're going in a completely wrong direction. Wouldn't you rather have that information after a month of development rather than after nine months of requirements gathering, scheduling, meetings, presentations, etc.?

Braithwaite also posits that the real scare resource in these situations isn't development capacity, it's management capacity. Decisions need to be made about features, and asking management to make such decisions and provide feedback on multiple features at once. Break the project into digestible chunks, for everyone's sake. 

Bonus side-effect: By developing a complete product each step of the way you'll have tons of experience making the different technologies work together, or at least you'll find out right away when they don't. 

## Goals

How do you define a successful project? Here's a possible answer:

>A project is successful when it meets all of the requirements laid out at the beginning.

Now, here I'm going to make a distinction that I've seen made elsewhere. Requirements are technical. Requirements define what software is supposed to do. That's useful and important.
  
What requirements don't tell us is how much value the customer is getting from the project.

At the beginning of a project and every step along the way, your job isn't to nail down requirements. Your job is to find out the customer's goals in having this project.

Requirements are static. Once you say that you need to use Bootstrap 3 so that your app is compatible with mobile devices up front, you know you're using Bootstrap 3. It's been chosen, it works, there's no need to reconsider that.

Goals are dynamic. Goals change. At first your customer might think they need a mobile-compatible web app to allow their traveling sales people to read product updates on their phones. But then you learn that the sales people don't read product updates on their phones because the updates are too long and detailed. They'd actually rather have them sent to their Kindles so they can read the updates without eye strain. Since traditional e-readers don't really play nice with web applications your responsive css classes aren't going to be of any use. You really ought to be sending the updates out in plain text so the sales people can upload them directly to their Kindles.
  
[Wow I came up with a decent example. Pat on the back right there.]

If you never learned this, your customer would have a mobile-responsive web app with all their product updates and their sales people still wouldn't be reading them.