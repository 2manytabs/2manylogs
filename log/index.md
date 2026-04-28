---
layout: default
title: Log
---

# 📓 Log

{% raw %}
{% assign logs = site.pages | where_exp: "p", "p.dir == '/log/' and p.name != 'index.md'" %}
{% assign logs = logs | sort: "date" | reverse %}

{% for log in logs %}
- [{{ log.title }}]({{ log.url }}) — {{ log.date | date: "%Y-%m-%d" }}
{% endfor %}
{% endraw %}
