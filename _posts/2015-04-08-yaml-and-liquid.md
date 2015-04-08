---
layout: post
title: YAML and Liquid
---

I finally got around to trying to automate the population of my Reading page with the books on my list. 

Before this I had each book with the following attributes:

- image
- title
- link
- author
- status
- description

set up in this Frankenstein's monster of Markdown and HTML table formatting:

<aside>It was finals, ok? It's not like I had anything better to do.</aside>

{% highlight html %}
| <img src="{{ site.url }}/assets/joel_on_software.jpg" alt="Joel on Software"/> | [**Joel on Software**](http://smile.amazon.com/gp/product/B001NRNIMG/ref=kinw_myk_ro_title)<br>by Joel Spolsky<br><i class="fa fa-check-square-o"></i> **Completed** |
{% endhighlight %}

Luckily Sublime wraps my text for me so it's not quite that impossible to read, but the moment I started doing this I knew I'd have to automate it one day.

Thankfully I'm smart enough to use [Jekyll]() to build my blog, which means I have access to [Liquid attributes](https://docs.shopify.com/themes/liquid-documentation/basics), with which I can do things using [YAML](http://jekyllrb.com/docs/variables/) data. 

YAML is like JSON but easier to read. Basically just key-value pairs, or variables with values, or structs/classes with instance variables, or objects with attributes.

Early on I figured out how to organize the YAML metadata for my reading list:

{% highlight yaml %}
- title: 
  author: 
  link: 
  image: 
  description: >
  status: 
{% endhighlight %}

Which was easy enough to fill in with my data:

{% highlight yaml %}
- title: Code
  author: Charles Petzold
  link: "http://smile.amazon.com/Code-Developer-Practices-Charles-Petzold-ebook/dp/B00JDMPOK2/ref=sr_1_1?s=digital-text&ie=UTF8&qid=1423800084&sr=1-1&keywords=code"
  image: /assets/code.jpg
  description: >
  status: <i class="fa fa-refresh"></i> In Progress
{% endhighlight %}

After pouring over the [Jekyll documentation]() for a while I finally put it together that you can create a new folder called `_data` in your Jekyll site directory and put in whatever `.yml` files you want. So I moved my `reading.yml` there, which meant I could now access any of the attributes in my reading objects using `site.data.reading`.

It took me a while to shake out the initial bugs--mostly issues with too many or not enough quotation marks--and for a while my Reading page was stuck like this:

<img class="wide" src="{{ site.url }}/assets/comp/bad-read.png"/>

<aside top="1950px">I'm having so much trouble formatting the code in this post. It's great that Liquid still plugs in variables if I want them formatted like code, but that means it's significantly harder to get my point across here.</aside>

The main issue in that above photograph was that I needed quotes here around the double curly braces for `book.link` as well as around the URL in my YAML file. 

I soon realized that I wouldn't be able to automate the section headers this way, and I didn't really want to at this point (someday I'll actually learn JavaScript, I promise) so I decided to separate out each section on my reading page:

- Semi-Technical Reads
- Working in Software
- Self-Improvement and Social Psychology
- Health and Fitness

That explains why I renamed `reading.yml` to `tech.yml` and why my for-loop below pulls each `book` object from `site.data.tech`. It's like Intro to Computer Science for HTML!

<script src="https://gist.github.com/shelbyspees/5d93a9c75de141e60f10.js"></script>

In the above YAML object example with *Code*, you can see that I left the string for `status` reading `<i class="fa fa-refresh"></i> In Progress`. After filling out a couple sets of these I realized I definitely wanted the HTML for my status icon to be locked away in some nice `in_progress` variable that I can just reference in my `tech.yml` file.

[Jekyll's documentation](http://jekyllrb.com/docs/variables/) says I should be able to just create my own variables using the `site.[CONFIGURATION_DATA]` functionality by creating a new variable in `_config.yml`. So I went into my config file and threw down the following:

{% highlight html %}
completed: <i class="fa fa-check-square-o"></i> <b>Completed</b> 
in_progress: <i class="fa fa-refresh"></i> In Progress
not_started: <i class="fa fa-ellipsis-h"></i> <em>Not Started</em>
owned: <i class="fa fa-ellipsis-h"></i> <em>Owned, Not Started</em>
{% endhighlight %}

And I went back into my `tech.yml` file and changed it to this:

    status: { site.in_progress }

And it didn't work. When I open up my reading page I get this:

<img class="wide" src="{{ site.url }}/assets/comp/nil-read.png"/>

Which is Ruby for "`site.in_progress` is returning `nil`, you dummy. I don't know what the heck you're trying to reference here but I'm pretty sure it doesn't exist."

I mean I know it doesn't make sense for the In Progress icon to be a global variable in `site` but I just wanted to get it working first before organizing it logically, the right way. But it didn't work. Doesn't matter what kinds of quotation marks I use or how many curly braces I try, my .yml file doesn't want to read from my other .yml file.

Ughh.

So I decided to write this post while it was all fresh in my mind. It's 4:00am right now and I wanted to sleep at like 9:00pm and my sleep schedule is totally on its head.

I might just have to manually enter the HTML for each status icon. Maybe I'll ask on Stack Overflow.