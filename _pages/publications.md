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
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="50%" style="float: left" />
  <p style="text-align: justify">{{ publi.description }}</p>
  <p><em>{{ publi.authors }}</em></p>
  <!--<p><strong><a href="{{ publi.link.url }}">{{ publi.link.display }}</a></strong></p>-->
  {% for link in publi.link %}
   test
  <br><strong><a href="{{ link.url }}">{{ link.display }}</a></strong>
  {% endfor %}
  <!--<strong><a href="{{ publi.linksupp.url }}">{{ publi.linksupp.display }}</a></strong><br>
  <strong><a href="{{ publi.linkvideo.url }}">{{ publi.linkvideo.display }}</a></strong><br>
  <strong><a href="{{ publi.linkopen.url }}">{{ publi.linkopen.display }}</a></strong><br> 
  <strong><a href="{{ publi.linkcode.url }}">{{ publi.linkcode.display }}</a></strong><br> 
  <strong><a href="{{ publi.linkpres.url }}">{{ publi.linkpres.display }}</a></strong></p>-->
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
