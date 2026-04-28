---
layout: default
title: Home
nav_order: 1
---

# 👋 2manylogs
## 🔧 Projects

{% assign projects = site.pages
  | where_exp: "p", "p.url contains '/projects/'"
  | sort: "start_date"
  | reverse %}

{% if projects.size > 0 %}
{% for p in projects %}
  {% if p.url != '/projects/' %}
- {% if p.status == "done" %}🟢{% else %}🟡{% endif %} {{ p.start_date | date: "%Y-%m-%d" }}{% if p.end_date %} → {{ p.end_date | date: "%Y-%m-%d" }}{% endif %} - [{{ p.title }}]({{ p.url }}) — {{ p.tags | join: " · " }}
  {% endif %}
{% endfor %}
{% else %}
no projects yet
{% endif %}


---

## 📝 Logs

{% assign logs = site.pages
  | where_exp: "p", "p.date"
  | sort: "date"
  | reverse %}

{% if logs.size > 0 %}
{% for l in logs %}
- {{ l.date | date: "%Y-%m-%d" }} - [{{ l.title }}]({{ l.url }}) — {{ l.tags | join: " · " }}
{% endfor %}
{% else %}
no logs yet
{% endif %}

