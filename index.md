---
layout: default
title: Home
nav_order: 1
---

# 👋 2manylogs
## 🔧 Projects

{% assign projects = site.pages
  | where_exp: "p", "p.url contains '/projects/'"
  | sort: "date"
  | reverse %}

{% if projects.size > 0 %}
{% for p in projects %}
  {% if p.url != '/projects/' %}
- {{ p.date | date: "%Y-%m-%d" }} - [{{ p.title }}]({{ p.url }}) — {{ p.tags | join: " · " }}
  {% endif %}
{% endfor %}
{% else %}
no projects yet
{% endif %}

---

## 📝 Logs

{% assign logs = site.pages
  | where_exp: "p", "p.url contains '/log/'"
  | sort: "date"
  | reverse %}

{% if logs.size > 0 %}
{% for l in logs %}
  {% if l.url != '/log/' %}
- {{ l.date | date: "%Y-%m-%d" }} - [{{ l.title }}]({{ l.url }}) — {{ l.tags | join: " · " }}
  {% endif %}
{% endfor %}
{% else %}
no logs yet
{% endif %}
