---
layout: page
title: "Semi-Technical Reads"
permalink: /reading/tech
---

<div class="reading-container">
{% for book in site.data.tech %}
<div class="reading">
    <div class="reading-img">
        <img class="book-cover" src="{{ site.url }}{{ book.image }}" alt="{{ book.title }}"/>
    </div>
    <a href="{{ book.link }}"><b>{{ book.title }}</b></a>
    {% if book.author %}<br>{{ book.author }}{% endif %}
    <br>{{ book.status }}
    {% if book.description %}<br><br>{{ book.description }}{% endif %}
</div>
{% endfor %}
</div>