---
title: "Hemang Chawla - Scholarly Works and Inventions"
layout: gridlay
excerpt: "Hemang Chawla -- Scholarly Works and Inventions."
sitemap: false
permalink: /scientific-portfolio/
---
# Scholarly Works and Inventions

{% assign num_items = site.data.publist.size | minus: 1 %}
<div markdown="0" id="carousel" class="carousel slide" data-ride="carousel" data-interval="5000" data-pause="hover" >
    <!-- Menu -->
    <ol class="carousel-indicators">
      {% for i in (0..num_items) %}
        {% if i == 0 %}
          <li data-target="#carousel" data-slide-to="{{i}}" class="active"></li>
        {% else %}
          <li data-target="#carousel" data-slide-to="{{i}}"></li>
        {% endif %}
      {% endfor %}
    </ol>
    <!-- Items -->
    <div class="carousel-inner" markdown="0">
      {% for i in (0..num_items) %}
        {% assign publi = site.data.publist[i] %} 
        {% if i == 0 %}
        <div class="item active">
          <div class="well">
          <pubtit style="text-align: justify">{{ publi.title }}</pubtit>
          <p><em>{{ publi.authors }}</em></p>
          <p>
          {%- if publi.conf.website -%}
          <a href="{{ publi.conf.website }}">{{publi.conf.name}}, {{publi.conf.year}} </a> 
          {% else %}
          {{publi.conf.name}}, {{publi.conf.year}}
          {% endif %}
          </p>
          <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="50%" style="float: left" />
          {% assign max_words = 81 %}
          <p style="text-align: justify">{{publi.description}} <a href="{{publi.link.url}}">(read more)</a></p>
          <p>
          <!--{%- if publi.link -%}<strong>[<a href="{{ publi.link.url }}">{{ publi.link.display }}</a>]</strong> {%- endif -%}-->
          {%- if publi.linksupp -%}<strong>[<a href="{{ publi.linksupp.url }}">{{ publi.linksupp.display }}</a>]</strong> {%- endif -%}
          {%- if publi.linkvideo -%}<strong>[<a href="{{ publi.linkvideo.url }}">{{ publi.linkvideo.display }}</a>]</strong> {%- endif -%}
          {%- if publi.linkopen -%}<strong>[<a href="{{ publi.linkopen.url }}">{{ publi.linkopen.display }}</a>]</strong> {%- endif -%} 
          {%- if publi.linkcode -%}<strong>[<a href="{{ publi.linkcode.url }}">{{ publi.linkcode.display }}</a>]</strong> {%- endif -%} 
          {%- if publi.linkpres -%}<strong>[<a href="{{ publi.linkpres.url }}">{{ publi.linkpres.display }}</a>]</strong>{%- endif -%}
          </p>
          <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
          <p> {{ publi.news2 }}</p>
          </div>
        </div>
        {% else %}
        <div class="item">
          <div class="well">
          <pubtit style="text-align: justify">{{ publi.title }}</pubtit>
          <p><em>{{ publi.authors }}</em></p>
          <p>
          {%- if publi.conf.website -%}
          <a href="{{ publi.conf.website }}">{{publi.conf.name}}, {{publi.conf.year}} </a> 
          {% else %}
          {{publi.conf.name}}, {{publi.conf.year}}
          {% endif %}
          </p>
          <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="50%" style="float: left" />
          {% assign max_words = 81 %}
          <p style="text-align: justify">{{publi.description}} <a href="{{publi.link.url}}">(read more)</a></p>
          <p>
          <!--{%- if publi.link -%}<strong>[<a href="{{ publi.link.url }}">{{ publi.link.display }}</a>]</strong> {%- endif -%}-->
          {%- if publi.linksupp -%}<strong>[<a href="{{ publi.linksupp.url }}">{{ publi.linksupp.display }}</a>]</strong> {%- endif -%}
          {%- if publi.linkvideo -%}<strong>[<a href="{{ publi.linkvideo.url }}">{{ publi.linkvideo.display }}</a>]</strong> {%- endif -%}
          {%- if publi.linkopen -%}<strong>[<a href="{{ publi.linkopen.url }}">{{ publi.linkopen.display }}</a>]</strong> {%- endif -%} 
          {%- if publi.linkcode -%}<strong>[<a href="{{ publi.linkcode.url }}">{{ publi.linkcode.display }}</a>]</strong> {%- endif -%} 
          {%- if publi.linkpres -%}<strong>[<a href="{{ publi.linkpres.url }}">{{ publi.linkpres.display }}</a>]</strong>{%- endif -%}
          </p>
          <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
          <p> {{ publi.news2 }}</p>
          </div>
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

# Research Papers

{% for publi in site.data.publist %}

  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br /><a href="{{ publi.link.url }}">{{ publi.link.display }}</a>

{% endfor %}

# Patents




----
See more at [Google Scholar](https://scholar.google.ch/citations?user=_58RpMgAAAAJ), [Semantic Scholar](https://www.semanticscholar.org/author/Hemang-Chawla/102373287), and [ResearchGate](https://www.researchgate.net/profile/Hemang-Chawla-2/research)
