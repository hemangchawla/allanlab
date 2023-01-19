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
  
  {% assign max_words = 30 %}
  {% capture content_words %}
    {{ publi.description | number_of_words }}
  {% endcapture %}
  {% capture excerpt_words %}
    {{ publi.description | truncatewords: max_words}}
  {% endcapture %}

  {% if content_words != excerpt_words  %}
    {% assign words = publi.description | split: " " %} 
  {% endif %}

  <p style="text-align: justify"> 
  {% if content_words != excerpt_words  %}

  {% capture to_show %} {{publi.description | truncatewords: max_words, "" }} {% endcapture %}
  {% assign to_show = to_show | strip %}
  {% capture to_hide %} {{publi.description | split: to_show | last }} {% endcapture %}
  {{to_show}}...
  AND
  {{to_hide}}
  {% endif %}
  </p>

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

[//]: # (<script>)

[//]: # (function myFunction&#40;&#41; {)

[//]: # (  var dots = document.getElementById&#40;"dots"&#41;;)

[//]: # (  var moreText = document.getElementById&#40;"more"&#41;;)

[//]: # (  var btnText = document.getElementById&#40;"myBtn"&#41;;)

[//]: # ()
[//]: # (  if &#40;dots.style.display === "none"&#41; {)

[//]: # (    dots.style.display = "inline";)

[//]: # (    btnText.innerHTML = "Read more"; )

[//]: # (    moreText.style.display = "none";)

[//]: # (  } else {)

[//]: # (    dots.style.display = "none";)

[//]: # (    btnText.innerHTML = "Read less"; )

[//]: # (    moreText.style.display = "inline";)

[//]: # (  })

[//]: # (})

[//]: # (</script>)

[//]: # (    {{ publi.description | truncatewords: max_words}})

[//]: # (    wohoo)

[//]: # (    {{ words | join " " }})