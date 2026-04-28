---
layout: default
title: Log
nav_order: 3
---

# Log

{% assign logs = site.pages | where_exp: "p", "p.path contains 'log/'" %}
{% assign logs = logs | where_exp: "p", "p.name != 'index.md'" %}
{% assign logs = logs | sort: "date" | reverse %}

{% for log in logs %}
- {{ log.date | date: "%Y-%m-%d" }} — [{{ log.title }}]({{ log.url }})
{% endfor %}
