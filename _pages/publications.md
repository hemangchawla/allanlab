---
title: "Hemang Chawla - Publications"
layout: gridlay
excerpt: "Hemang Chawla -- Publications."
sitemap: false
permalink: /publications/
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
  <p><em>{{ publi.authors }}</em></p>
---
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="50%" style="float: left" />
    {% if publi.description contains '<!--more-->' %}
        <div>
        <p style="text-align: justify">{{ publi.description | split:'<!--more-->' | first }}</p>
        </div>
        <input type="checkbox" class="read-more-state" id="{{ publi.url }}"/>
        <div class="read-more">
        <p style="text-align: justify">{{ publi.description | split:'<!--more-->' | last  }}</p>
        </div>
        <label for="{{ publi.url }}" class="read-more-trigger"></label>
    {% else %}
        <p style="text-align: justify">{{ publi.description }}</p>
    {% endif %}  

[//]: # (    <p style="text-align: justify">{{ publi.description }}</p>)

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


/* Read More */

.read-more {
    opacity: 0;
    max-height: 0;
    font-size: 0;
    transition: .25s ease;
    display: none;
}

.read-more-state {
  display: none;
}

.read-more-state:checked ~ .read-more {
  opacity: 1;
  font-size: inherit;
  max-height: 999em;
  display: inherit;
}

.read-more-state ~ .read-more-trigger:before {
  content: 'Continue reading...';
}

.read-more-state:checked ~ .read-more-trigger:before {
  content: 'Show less...';
}

.read-more-trigger {
  cursor: pointer;
  padding: 1em .5em;
  color: #0085bd;
  font-size: .9em;
  line-height: 2;
  border: 1px solid #0085bd;
  border-radius: .25em;
  font-weight: 500;
  display: grid;
  text-align: center;
}
