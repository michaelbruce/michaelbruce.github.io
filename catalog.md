---
layout: default
title: Catalog
tagline: These are thoughts flowing through my mind
---

### Check out these articles

{% for post in site.posts %}
  <a href="{{ post.url }}">{{ post.title }}</a><span> &raquo; {{ post.date | date_to_string }}</span>
{% endfor %}
