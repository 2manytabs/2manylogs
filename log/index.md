---
layout: default
title: Log
has_children: true
nav_order: 3
---

# Log

{% assign logs = site.pages
  | where_exp: "p", "p.date and p.url contains '/log/'"
  | sort: "date"
  | reverse %}

{% for log in logs %}
- {{ log.date | date: "%Y-%m-%d" }} — [{{ log.title }}]({{ log.url }}) — {{ log.tags | join: " · " }}
{% endfor %}
