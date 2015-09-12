---
layout: page
title: "Working in Software"
permalink: /software/
---

<div class="reading-container">
{% for book in site.data.software %}
{% include booklist.html %}
{% endfor %}
</div>