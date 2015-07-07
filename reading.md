---
layout: page
title: reading
permalink: /reading/
---

<aside><p>Books I've enjoyed in the past year or so, plus a few I'm hoping to crack open soon. In no particular order.</p><p>Check out the <a href="{{ site.url }}/best_practices/2015/04/10/best-of.html">Best Of</a> post I wrote listing articles I've enjoyed.</p>

<b>Book Categories:</b>
<ul class="aside-list">
    <li><a href="#top">Semi-Technical Reads</a></li>
    <li><a href="#career">Working in Software</a></li>
        <li><a href="#psych">Brains and People</a></li>
    <li><a href="#health">Health and Fitness</a></li>
</ul>
</aside>



<div class="reading-container">
    <h2 id="technical" class="">Semi-Technical Reads</h2>

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





<div class="reading-container">
    <h2 id="career" class="anchor">Working in Software</h2>

    <aside>
    <b>Book Categories:</b>
    <ul class="aside-list">
        <li><a href="#top">Semi-Technical Reads</a></li>
        <li><a href="#career">Working in Software</a></li>
        <li><a href="#psych">Brains and People</a></li>
        <li><a href="#health">Health and Fitness</a></li>
    </ul>
    </aside>

    {% for book in site.data.software %}
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





<div class="reading-container">
    <h2 id="psych" class="anchor">Brains and People</h2>

    <aside>
    <b>Book Categories:</b>
    <ul class="aside-list">
        <li><a href="#top">Semi-Technical Reads</a></li>
        <li><a href="#career">Working in Software</a></li>
        <li><a href="#psych">Brains and People</a></li>
        <li><a href="#health">Health and Fitness</a></li>
    </ul>
    </aside>

    {% for book in site.data.psych %}
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




<div class="reading-container">
    <h2 id="health" class="anchor">Health and Fitness</h2>

    <aside>
    <b>Book Categories:</b>
    <ul class="aside-list">
        <li><a href="#top">Semi-Technical Reads</a></li>
        <li><a href="#career">Working in Software</a></li>
        <li><a href="#psych">Brains and People</a></li>
        <li><a href="#health">Health and Fitness</a></li>
    </ul>
    </aside>

    <p>Starting Strength</p>
    <p>Ultramarathon Runner</p>
    <p>Born to Run</p>
    <p>Mindless Eating: Why We Eat More Than We Think</p>
</div>