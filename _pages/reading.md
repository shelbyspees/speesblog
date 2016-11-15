---
layout: page
title: reading
permalink: /reading/
---

Books I've enjoyed in the past year or so, plus a few I'm hoping to crack open soon. In no particular order.

Check out the <a href="{{ site.baseurl }}/best_practices/2015/04/10/best-of/">Best Of</a> post I wrote listing articles I've enjoyed.

## Lists

Lists expand and collapse.

<div class="panel-group" id="accordion" role="tablist" aria-multiselectable="true">
  <div class="panel panel-default">
    <div class="panel-heading" role="tab" id="software">
      <h4 class="panel-title">
        <a role="button" data-toggle="collapse" data-parent="#accordion" href="#software-list" aria-expanded="true" aria-controls="software-list">
          Working in Software
        </a>
      </h4>
    </div>
    <div id="software-list" class="panel-collapse collapse in" role="tabpanel" aria-labelledby="software">
      <div class="panel-body">
        <div class="reading-container">
          {% for book in site.data.software %}
          {% include booklist.html %}
          {% endfor %}
        </div>
      </div>
    </div>
  </div>
  <div class="panel panel-default">
    <div class="panel-heading" role="tab" id="psych">
      <h4 class="panel-title">
        <a class="collapsed" role="button" data-toggle="collapse" data-parent="#accordion" href="#psych-list" aria-expanded="false" aria-controls="psych-list">
          Brains and People
        </a>
      </h4>
    </div>
    <div id="psych-list" class="panel-collapse collapse" role="tabpanel" aria-labelledby="psych">
      <div class="panel-body">
        <div class="reading-container">
          {% for book in site.data.psych %}
          {% include booklist.html %}
          {% endfor %}
        </div>
      </div>
    </div>
  </div>
  <div class="panel panel-default">
    <div class="panel-heading" role="tab" id="writing">
      <h4 class="panel-title">
        <a class="collapsed" role="button" data-toggle="collapse" data-parent="#accordion" href="#writing-list" aria-expanded="false" aria-controls="writing-list">
          Books on Writing
        </a>
      </h4>
    </div>
    <div id="writing-list" class="panel-collapse collapse" role="tabpanel" aria-labelledby="writing">
      <div class="panel-body">
        <p class="text-muted">
          <small>
            (Shout out to the <a href="http://www.writingexcuses.com/season001/"><i>Writing Excuses</i> podcast</a>!)
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
      </div>
    </div>
  </div>

</div>