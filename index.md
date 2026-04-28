---
layout: default
title: Home
nav_order: 1
---

# 👋 2manylogs
## 🔧 Latest Project

{% assign latest_project = site.pages
  | where_exp: "p", "p.url contains '/projects/'"
  | sort: "date"
  | reverse
  | first %}

{% if latest_project %}
- {{ latest_project.date | date: "%Y-%m-%d" }} - [{{ latest_project.title }}]({{ latest_project.url }})  
  tags: {{ latest_project.tags | join: ", " }}
{% else %}
no projects yet
{% endif %}

---

## 📝 Latest Log

{% assign latest_log = site.pages
  | where_exp: "p", "p.url contains '/log/'"
  | sort: "date"
  | reverse
  | first %}

{% if latest_log %}
- {{ latest_log.date | date: "%Y-%m-%d" }} - [{{ latest_log.title }}]({{ latest_log.url }})  
  tags: {{ latest_log.tags | join: ", " }}
{% else %}
no logs yet
{% endif %}
