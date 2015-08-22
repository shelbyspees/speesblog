---
layout: post
title: Makefile Project
category: technologies
---

Nearly six months later, I finally figured out how to compile and run my homework in Eclipse.

I'm talking about [this whole mess]({{ site.url }}{% post_url 2015-02-22-iterate-faster %}) where I thought it was an issue with my version of GCC or clang or something.

I hate this configuration stuff.

<img class="wide" src="{{ site.url }}/assets/comp/eclipse-project.png"/>

What I was doing was making a ***New C Project***, but I should have been doing ***New Makefile Project with Existing Code***. Cause I had existing code with a makefile. That's what my professor gives us every week to fill in with our implementation code.

This is like a rite of passage. Or hazing. Same thing, really.