---
title: "Hemang Chawla - Research and Inventions"
layout: gridlay
excerpt: "Hemang Chawla -- Research and Inventions."
sitemap: false
permalink: /research-inventions/
---
# Research and Inventions

{% assign num_items = site.data.publist.size | minus: 1 %}
{% assign highlights = site.data.publist | where_exp: "publi", "publi.highlight == 1" %}
{% assign num_highlights = highlights.size | minus: 1 %}

<div markdown="0" id="carousel" class="carousel slide" data-ride="carousel" data-interval="3000" data-pause="" >
    <!-- Menu -->
    <ol class="carousel-indicators">
      {% for i in (0..num_highlights) %}
        {% assign publi = highlights[i] %}
        {% if i == 0 %}
          <li data-target="#carousel" data-slide-to="{{i}}" class="active"></li>
        {% else %}
          <li data-target="#carousel" data-slide-to="{{i}}"></li>
        {% endif %}
      {% endfor %}
    </ol>
    <!-- Items -->
    <div class="carousel-inner" markdown="0">
      {% for i in (0..num_highlights) %}
        {% assign publi = highlights[i] %}
        {% if i == 0 %}
        <div class="item active">
          <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic_same_size/{{ publi.image }}" height= "50%" alt= "{{publi.title}}, {{publi.link.display}}" class="img-responsive" style="float: center;" />
        </div>
        {% else %}
        <div class="item">
          <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic_same_size/{{ publi.image }}" height= "50%" alt= "{{publi.title}}, {{publi.link.display}}" class="img-responsive" style="float: center;" />
        </div>
        {% endif %}
      {% endfor %}
    </div>
  <a class="left carousel-control" href="#carousel" role="button" data-slide="prev">
    <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="right carousel-control" href="#carousel" role="button" data-slide="next">
    <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>

## Papers

{% for publi in site.data.publist %}

  <b>{{ publi.title }}</b> <br />
  {%- if publi.conf -%}<a href="{{ publi.conf.website}}">{{ publi.conf.name }}</a> {%- endif -%} <br />
  <em>{{ publi.authors }} </em> <br />
  {%- if publi.link.url -%}[<a href="{{ publi.link.url }}">Camera Ready</a>] {%- endif -%}
  {%- if publi.linksupp -%}[<a href="{{ publi.linksupp.url }}">{{ publi.linksupp.display }}</a>] {%- endif -%}
  {%- if publi.linkvideo -%}[<a href="{{ publi.linkvideo.url }}">{{ publi.linkvideo.display }}</a>] {%- endif -%}
  {%- if publi.linkopen -%}[<a href="{{ publi.linkopen.url }}">{{ publi.linkopen.display }}</a>] {%- endif -%} 
  {%- if publi.linkcode -%}[<a href="{{ publi.linkcode.url }}">{{ publi.linkcode.display }}</a>] {%- endif -%} 
  {%- if publi.linkpres -%}[<a href="{{ publi.linkpres.url }}">{{ publi.linkpres.display }}</a>]{%- endif -%}

{% endfor %}

## Patents

{% for patent in site.data.patentlist %}
  <b>{{patent.title}}</b> <br />
  <em>{{ patent.inventors }} </em> <br />
  {% if patent.pending != 1 %}  
  {%- if patent.published -%} Published: {{patent.published}} <br /> {%- endif -%}
  {%- if patent.granted -%} Granted: {{patent.granted}} <br /> {%- endif -%}
  {%- else -%}
  Pending
  {% endif %}
{% endfor %}


----
See more at [Google Scholar](https://scholar.google.ch/citations?user=_58RpMgAAAAJ), 
and [Google Patents](https://patents.google.com/?inventor=Hemang+Chawla)