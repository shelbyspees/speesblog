---
layout: page
title: "Books on Writing"
permalink: /reading/writing/
---

<p class="text-muted">
  <small>
    (Shout out to the <a href="http://www.writingexcuses.com/season001/"><i>Writing Excuses</i> podcast</a> with Brandon Sanderson, Dan Wells, and Howard Taylor. I'm only on season 2 but I already love these guys.)
  </small>
</p>

<div class="reading-container">
  {% for book in site.data.writing %}
    <div class="reading">
      <div class="reading-img">
        <img class="book-cover" src="{{ book.image }}" alt="{{ book.title }}"/>
      </div>
      <a href="{{ book.link }}"><b>{{ book.title }}</b></a>
      {% if book.author %}<br>{{ book.author }}{% endif %}
      <br>{{ book.status }}
    </div>
  {% endfor %}
</div>
