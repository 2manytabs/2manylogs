---
layout: default
title: Home
nav_order: 1
---

# 👋 2manylogs

## 🔧 Latest Project

{% assign latest_project = site.pages 
  | where: "parent", "Projects" 
  | sort: "date" 
  | reverse 
  | first %}

{% if latest_project %}
- {{ latest_project.date | date: "%Y-%m-%d" }} - [{{ latest_project.title }}]({{ latest_project.url }})  
  tags: {{ latest_project.tags | join: ", " }}
{% else %}
_no projects yet_
{% endif %}

---

## 📝 Latest Log

{% assign latest_log = site.pages 
  | where: "parent", "Log" 
  | sort: "date" 
  | reverse 
  | first %}

{% if latest_log %}
- {{ latest_log.date | date: "%Y-%m-%d" }} - [{{ latest_log.title }}]({{ latest_log.url }})  
  tags: {{ latest_log.tags | join: ", " }}
{% else %}
_no logs yet_
{% endif %}
