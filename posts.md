---
layout: page
title: posts
permalink: /posts/
---

<ul style="margin-left: 0; list-style: none;">
	{% for post in site.posts %}
	<li>
		{{ post.date | date: "%b %d" }} <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
	</li>
	{% endfor %}
</ul>