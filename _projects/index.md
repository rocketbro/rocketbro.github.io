---
layout: default
title: Projects
permalink: /
---

# Projects

{% for project in site.pages %}
  {% if project.url contains '/projects/' and project.url != '/projects/' %}
  - [{{ project.title }}]({{ project.url }})
  {% endif %}
{% endfor %}