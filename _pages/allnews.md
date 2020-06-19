---
title: "News"
layout: textlay
excerpt: "Hemang Chawla - Robotics | Vision | AI"
sitemap: false
permalink: /allnews.html
---

# News

{% for article in site.data.news %}
<p>{{ article.date }} <br>
<em>{{ article.headline }}</em></p>
{% endfor %}
