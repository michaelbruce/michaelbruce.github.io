---
layout: default
title: Home
tagline: This is what I live for
---

### Check out these articles

{% for post in site.posts %}
  <a href="{{ post.url }}">{{ post.title }}</a><span> &raquo; {{ post.date | date_to_string }}</span>
{% endfor %}

```
;;;###autoload
(defun evelyn/open-shell-in-ansi-term ()
  "Opens a new shell inside an ansi-terminal."
  (interactive)
    (ansi-term "bash" "localhost"))
```

