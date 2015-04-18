---
layout: page
title: Topics
group: navigation
permalink: /topics/
---
{% include JB/setup %}

{% for category in site.categories %} 
  <h2 id="{{ category[0] }}-ref">{{ category[0] | join: "/" | replace: '_', ' ' }}</h2>
  <ul class="list-by-topic">
    {% assign pages_list = category[1] %}
    {% include JB/pages_list %}
  </ul>
{% endfor %}

