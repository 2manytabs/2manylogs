---
layout: default
title: all_logs
has_children: true
has_toc: false
nav_order: 3
---

# all_logs
{% assign logs = site.pages
  | where_exp: "p", "p.url contains '/log/'"
  | sort: "date"
  | reverse %}

{% for log in logs %}
  {% if log.url != '/log/' and log.date %}

    {% assign proj = site.pages | where: "project_id", log.project | first %}

- {{ log.date | date: "%Y-%m-%d" }} — [{{ log.title }}]({{ log.url }}){% if proj %} — 📦 [{{ proj.title }}]({{ proj.url }}){% endif %}{% if log.tags %} — {{ log.tags | join: " · " }}{% endif %}

  {% endif %}
{% endfor %}
