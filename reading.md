---
layout: page
title: Reading
permalink: /reading/
---

<aside><p>Books I've enjoyed in the past year or so, plus a few I'm hoping to crack open soon. In no particular order.</p><p>Check out the <a href="{{ site.url }}/best_practices/2015/04/10/best-of.html">Best Of</a> post I wrote listing articles I've enjoyed.</p>

<b>Book Categories:</b>
<ul class="aside-list">
    <li><a href="#top">Semi-Technical Reads</a></li>
    <li><a href="#career">Working in Software</a></li>
    <li><a href="#psych">Self-Improvement and Social Psychology</a></li>
    <li><a href="#health">Health and Fitness</a></li>
</ul>
</aside>



<h2 id="technical" class="">Semi-Technical Reads</h2>

{% for book in site.data.tech %}

<div class="reading">
    <div class="reading-img">
        <img src="{{ site.url }}{{ book.image }}" alt="{{ book.title }}"/>
    </div>
    <a href="{{ book.link }}"><b>{{ book.title }}</b></a>
    {% if book.author %}<br>by {{ book.author }}{% endif %}
    <br>{{ book.status }}
    {% if book.description %}<br><br>{{ book.description }}{% endif %}
</div>
{% endfor %}






<h2 id="technical" class="">Semi-Technical Reads</h2>

{% for book in site.data.tech %}
<table>
  <tr>
  	<td class="minimum"><img src="{{ site.url }}{{ book.image }}" alt="{{ book.title }}"/></td>
    <td>
    	<a href="{{ book.link }}">
    		<b>{{ book.title }}</b>
    	</a>
    {% if book.author %}
    	<br>by {{ book.author }}
    {% endif %}
    <br>{{ book.status }}
    {% if book.description %}
    	<br><br>{{ book.description }}
    {% endif %}
    </td>
  </tr>
</table>

<br>
{% endfor %}






<h2 id="career" class="anchor">Working in Software</h2>

<aside>
<b>Book Categories:</b>
<ul class="aside-list">
    <li><a href="#top">Semi-Technical Reads</a></li>
    <li><a href="#career">Working in Software</a></li>
    <li><a href="#psych">Self-Improvement and Social Psychology</a></li>
    <li><a href="#health">Health and Fitness</a></li>
</ul>
</aside>

{% for book in site.data.software %}
<table>
  <tr>
    <td class="minimum"><img src="{{ site.url }}{{ book.image }}" alt="{{ book.title }}"/></td>
    <td>
        <a href="{{ book.link }}">
            <b>{{ book.title }}</b>
        </a>
    {% if book.author %}
        <br>by {{ book.author }}
    {% endif %}
    <br>{{ book.status }}
    {% if book.description %}
        <br><br>{{ book.description }}
    {% endif %}
    </td>
  </tr>
</table>

<br>
{% endfor %}







<h2 id="psych" class="anchor">Self-Improvement and Social Psychology</h2>

<aside>
<b>Book Categories:</b>
<ul class="aside-list">
    <li><a href="#top">Semi-Technical Reads</a></li>
    <li><a href="#career">Working in Software</a></li>
    <li><a href="#psych">Self-Improvement and Social Psychology</a></li>
    <li><a href="#health">Health and Fitness</a></li>
</ul>
</aside>

{% for book in site.data.psych %}
<table>
  <tr>
    <td class="minimum"><img src="{{ site.url }}{{ book.image }}" alt="{{ book.title }}"/></td>
    <td>
        <a href="{{ book.link }}">
            <b>{{ book.title }}</b>
        </a>
    {% if book.author %}
        <br>by {{ book.author }}
    {% endif %}
    <br>{{ book.status }}
    {% if book.description %}
        <br><br>{{ book.description }}
    {% endif %}
    </td>
  </tr>
</table>

<br>
{% endfor %}







<h2 id="health" class="anchor">Health and Fitness</h2>

<aside>
<b>Book Categories:</b>
<ul class="aside-list">
    <li><a href="#top">Semi-Technical Reads</a></li>
    <li><a href="#career">Working in Software</a></li>
    <li><a href="#psych">Self-Improvement and Social Psychology</a></li>
    <li><a href="#health">Health and Fitness</a></li>
</ul>
</aside>

Starting Strength

Ultramarathon Runner

Born to Run

Mindless Eating: Why We Eat More Than We Think