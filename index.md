---
layout: default
title: Home
tagline: These are thoughts flowing through my mind
---

### Check out these articles
<hr>

{% for post in site.posts %}
  <a href="{{ post.url }}">{{ post.title }}</a><span style="float:right;"> {{ post.date | date_to_string }}</span>
{% endfor %}

<hr>
