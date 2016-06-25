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
  {% include booklist.html %}
  {% endfor %}
</div>
