---
title: "News"
layout: textlay
excerpt: "Hemang Chawla -- News"
sitemap: false
permalink: /news.html
---

# News

{% for article in site.data.news %}
<p>{{ article.date }} <br>
<em>{{ article.headline }}</em></p>
{% endfor %}
