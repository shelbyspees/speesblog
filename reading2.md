---
layout: page
title: Reading2
permalink: /reading2/
---

* [Semi-Technical Reads](#technical)
* [Working in Software](#career)
* [Self-Improvement and Social Psychology](#psych)
* [Health and Fitness](#health)

<aside><p>Books I've enjoyed in the past year or so, plus a few I'm hoping to crack open soon. In no particular order.</p></aside>

<h2 id="technical" class="anchor">Semi-Technical Reads</h2>

{% for book in site.data.reading %}
<table class="minimum">
  <tr>
  	<td><img src="{{ site.url }}{{ book.image }}" alt="{{ book.title }}"/></td>
    <td>
    	<a href="{{ book.link }}">
    		<b>{{ book.title }}</b>
    	</a>
    {% if book.author %}<br>by {{ book.author }}{% endif %}
    <br>{{ book.status }}
    {% if book.description %}<br><br>{{ book.description }}{% endif %}
    </td>
  </tr>
</table>
{% endfor %}