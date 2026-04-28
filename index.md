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

<div style="display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); gap: 12px;">

{% for p in projects %}
  {% if p.url != '/projects/' %}
  <a href="{{ p.url }}" style="text-decoration: none; color: inherit;">
    <div style="border: 1px solid #444; border-radius: 10px; padding: 12px; background: #111;">

      <div style="font-weight: bold; margin-bottom: 6px;">

        {% if p.status == "done" %}🟢{% elsif p.status == "in-progress" %}🟡{% else %}⚪{% endif %} 

        {{ p.title }}
      </div>

      <div style="font-size: 0.9em; opacity: 0.8;">
        {{ p.start_date | date: "%Y-%m-%d" }}
        {% if p.end_date %} → {{ p.end_date | date: "%Y-%m-%d" }}{% endif %}
      </div>

      {% if p.tags %}
      <div style="margin-top: 6px; font-size: 0.85em; opacity: 0.7;">
        {{ p.tags | join: " · " }}
      </div>
      {% endif %}

    </div>
  </a>
  {% endif %}
{% endfor %}

</div>



---

## 📝 Logs

{% assign logs = site.pages
  | where_exp: "p", "p.url contains '/log/'"
  | sort: "date"
  | reverse %}

{% for log in logs %}
  {% if log.url != '/log/' and log.date %}

    {% assign proj = site.pages | where: "project_id", log.project | first %}

- {{ log.date | date: "%Y-%m-%d" }} — [{{ log.title }}]({{ log.url }}){% if proj.status == "done" %}🟢{% elsif proj.status == "in-progress" %}🟡{% else %}⚪{% endif %} [{{ proj.title }}]({{ proj.url }}){% endif %}{% if log.tags %} — {{ log.tags | join: " · " }}{% endif %}

  {% endif %}
{% endfor %}
