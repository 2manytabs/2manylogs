---
layout: default
title: Log
has_children: true
has_toc: false
nav_order: 3
---

# Log

{% assign logs = site.pages
  | where_exp: "p", "p.url contains '/log/'"
  | sort: "date"
  | reverse %}

{% for log in logs %}
  {% if log.url != '/log/' and log.date %}
- {{ log.date | date: "%Y-%m-%d" }} — [{{ log.title }}]({{ log.url }}){% if log.tags %} — {{ log.tags | join: " · " }}{% endif %}
  {% endif %}
{% endfor %}
