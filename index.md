---
layout: default
title: Home
---

# 👋 2manylogs

## 🔧 Latest Project

{% assign projects = site.pages | where_exp: "p", "p.path contains 'projects/'" %}
{% assign projects = projects | where_exp: "p", "p.name != 'index.md'" %}
{% assign projects = projects | sort: "start_date" | reverse %}

{% assign latest_project = projects | first %}

{% if latest_project %}
- [{{ latest_project.title }}]({{ latest_project.url }})  
  → started {{ latest_project.start_date }}
{% else %}
_No projects yet_
{% endif %}

---

## 📝 Latest Log

{% assign logs = site.pages | where_exp: "p", "p.path contains 'log/'" %}
{% assign logs = logs | sort: "date" | reverse %}

{% assign latest_log = logs | first %}

{% if latest_log %}
- [{{ latest_log.title }}]({{ latest_log.url }})
{% else %}
_No logs yet_
{% endif %}
