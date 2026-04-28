---
layout: default
title: Projects
---

# 🔧 Projects

{% assign projects = site.pages | where_exp: "p", "p.dir == '/projects/' and p.name != 'index.md'" %}

{% for p in projects %}
- {{ p.title }}
{% endfor %}
