---
layout: default
title: test_project
project_id: test_project
parent: Projects
nav_exclude: true

status: in-progress
start_date: 2026-04-28
end_date:
tags: [iot, esp32]
---

[← Back to Projects](/projects/)

## {% if page.status == "done" %}🟢{% else %}🟡{% endif %} {{ page.title }}

**Path:**  
[Home](/) / [Projects](/projects/) / {{ page.title }}

**Meta:**  
**{{ page.start_date | date: "%Y-%m-%d" }}{% if page.end_date %} → {{ page.end_date | date: "%Y-%m-%d" }}{% endif %}**  
{{ page.tags | join: " · " }}

---

## 🧠 Overview
Short description of what this project is and why it exists.

---

## ⚙️ Stack
- ESP32  
- Sensors  
- Arduino IDE  

---

## 📦 Features
- feature 1  
- feature 2  

---

## 📝 Log / Progress
- 2026-04-28 — setup  
- 2026-04-29 — first test  

## 📝 Log / Progress (autolink test)

{% assign logs = site.pages
  | where_exp: "p", "p.project == page.title"
  | sort: "date"
  | reverse %}

{% if logs.size > 0 %}
{% for log in logs %}
- {{ log.date | date: "%Y-%m-%d" }} — [{{ log.title }}]({{ log.url }}){% if log.tags %} — {{ log.tags | join: " · " }}{% endif %}
{% endfor %}
{% else %}
no logs yet
{% endif %}
---

## 🚧 Notes / Problems
- issue 1  
- idea 2  

---

## 📸 Media (optional)
Screenshots, diagrams, links

---

## 🔗 Links
- GitHub repo  
- Docs  
