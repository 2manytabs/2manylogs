---
layout: default
title: Projects
has_children: true
nav_order: 2
toc: false
---

# 🔧 Projects

{% assign projects = site.pages | where_exp: "p", "p.path contains 'projects/'" %}
{% assign projects = projects | where_exp: "p", "p.name != 'index.md'" %}

{% assign in_progress = projects | where: "status", "in-progress" %}
{% assign done = projects | where: "status", "done" %}

## 🚧 In Progress

{% for p in in_progress %}
- {{ p.title }} — started {{ p.start_date | date: "%Y-%m-%d" }}
{% endfor %}

## ✅ Completed

{% for p in done %}
- {{ p.title }} — finished {{ p.end_date | date: "%Y-%m-%d" }}
{% endfor %}

---
## DEBUG

{% for p in site.pages %}
- {{ p.path }} | url: {{ p.url }} | date: {{ p.date }}
{% endfor %}
