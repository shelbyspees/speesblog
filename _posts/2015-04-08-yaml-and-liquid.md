---
layout: post
title: Yaml and Liquid
---

I finally got around to trying to automate the population of my Reading page with the books on my list. 

Before this I had each book with the following attributes:

- image
- title
- link
- author
- status
- description

Set up in this ugly Frankenstein's monster of Markdown and HTML table formatting:

{% highlight html %}
| <img src="{{ site.url }}/assets/joel_on_software.jpg" alt="Joel on Software"/> | [**Joel on Software**](http://smile.amazon.com/gp/product/B001NRNIMG/ref=kinw_myk_ro_title)<br>by Joel Spolsky<br><i class="fa fa-check-square-o"></i> **Completed** |
{% endhighlight %}

<aside top="250px">It was finals, ok? It's not like I had anything better to do.</aside>

Luckily Sublime wraps my text for me so it's not quite that impossible to read, but the moment I started doing this I knew I'd have to automate it one day.

Thankfully I'm smart enough to use [Jekyll]() to build my blog, which means I have access to [Liquid attributes](https://docs.shopify.com/themes/liquid-documentation/basics), with which I can do things using [YAML](http://jekyllrb.com/docs/variables/) data. 

YAML is like JSON but easier to read.

Early on I figured out how to organize the metadata for my reading list.

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
