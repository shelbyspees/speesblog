---
layout: post
title: YAML Resume
category: career
---

Finally got around to *parameterizing* the [resume page](http://shelbyspees.com/resume/) on my portfolio site.

[Jekyll](http://jekyllrb.com/), the tempting engine I use for my blog, can use <a href="https://en.wikipedia.org/wiki/YAML" data-toggle="tooltip" title="YAML Ain't Markup Language">YAML</a> to store data that can then be accessed from [Liquid](https://github.com/shopify/liquid/wiki/liquid-for-designers) templates in HTML files. I used this capability once before to fill out my [reading page](http://speesblog.com/technologies/2015/04/08/yaml-and-liquid/).

I wanted to do this with my resume for a lot of reasons. YAML is my preferred markup language over JSON or XML for its readability. You could print a YAML file directly on paper and it passes as a plain-text resume.

Of course I also wanted to simplify modifying the styling on my resume page, similar to what I did for my reading page. I hate boilerplate.

Here's the data for my Education section:


<pre># education.yml

- title: 'Bachelor of Science, Computer Science'
  graduation: 'in progress'
  school: 'Oregon State University'
  gpa: 'GPA: 3.80'

- title: 'Bachelor of Arts, Linguistics (Japanese Emphasis)'
  graduation: 'June 2012'
  school: 'University of California, Santa Barbara'
  minor: 'Educational Studies minor'
  gpa: 'GPA: 3.48'
</pre>

---

*In progress.*