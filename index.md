---
layout: default
title: Home
nav_order: 1
---

# 👋 2manylogs
## 🔧 Projects

{% assign projects = site.pages
  | where_exp: "p", "p.url contains '/projects/' and p.url != '/projects/'"
  | sort: "date"
  | reverse %}

{% if projects.size > 0 %}
{% for p in projects %}
- {{ p.date | date: "%Y-%m-%d" }} - [{{ p.title }}]({{ p.url }}) — {{ p.tags | join: " · " }}
{% endfor %}
{% else %}
no projects yet
{% endif %}

---

## 📝 Logs

{% assign logs = site.pages
  | where_exp: "p", "p.url contains '/log/' and p.url != '/log/'"
  | sort: "date"
  | reverse %}

{% if logs.size > 0 %}
{% for l in logs %}
- {{ l.date | date: "%Y-%m-%d" }} - [{{ l.title }}]({{ l.url }}) — {{ l.tags | join: " · " }}
{% endfor %}
{% else %}
no logs yet
{% endif %}
