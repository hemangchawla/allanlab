---
title: "Hemang Chawla - Publications"
layout: gridlay
excerpt: "Hemang Chawla -- Publications."
sitemap: false
permalink: /publications_short_highlights/
---


# Publications

For a full list with citations, go to [Google Scholar](https://scholar.google.ch/citations?user=_58RpMgAAAAJ)

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="well">
  <pubtit style="text-align: justify">{{ publi.title }}</pubtit>
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="50%" style="float: left" />
  
  {% assign max_words = 27 %}
  {% capture content_words %}
    {{ publi.description | number_of_words }}
  {% endcapture %}
  {% capture excerpt_words %}
    {{ publi.description | truncatewords: max_words}}
  {% endcapture %}

  {% assign splitting = false %}

  {% if content_words > excerpt_words  %}
    {% capture to_show %} {{publi.description | truncatewords: max_words, "" }} {% endcapture %}
    {% assign to_show = to_show | strip %}
    {% capture to_hide %} {{publi.description | split: to_show | last }} {% endcapture %}
    {% assign splitting = true %}
  {% endif %}

{% if splitting %}
  <div>
  <p style="text-align: justify"> 
  {{to_show}} ...
  </p>
  </div>
  <input type="checkbox" class="read-more-state" id="more"/>
  <div class="read-more">
  {{ to_hide }}
  </div>  
  <label for="more" class="read-more-trigger"></label>
{% else %}
  <p style="text-align: justify"> 
  {{publi.description}}
  </p>
{% endif %}

  <p><em>{{ publi.authors }}</em></p>
  <p>
  {%- if publi.link -%}<strong><a href="{{ publi.link.url }}">{{ publi.link.display }}</a></strong><br/> {%- endif -%}
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

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<p> &nbsp; </p>
