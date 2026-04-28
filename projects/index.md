---
layout: default
title: Projects
---

# 🔧 Projects

{% assign projects = site.pages | where_exp: "p", "p.path contains 'projects/'" %}
{% assign projects = projects | where_exp: "p", "p.name != 'index.md'" %}

{% assign in_progress = projects | where: "status", "in-progress" %}
{% assign done = projects | where: "status", "done" %}

## 🚧 In Progress

{% for p in in_progress %}
- [{{ p.title }}]({{ p.url }}) — started {{ p.start_date }}
{% endfor %}

## ✅ Completed

{% for p in done %}
- [{{ p.title }}]({{ p.url }})
{% endfor %}
