---
layout: page
title: "Semi-Technical Reads"
permalink: /tech/
---

<div class="reading-container">
{% for book in site.data.tech %}
{% include booklist.html %}
{% endfor %}
</div>