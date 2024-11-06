---
layout: default
title: Projects
---

# Projects

<div class="project-grid">
  {% for project in site.projects %}
    <div class="project-card">
      <h2>
        <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
      </h2>
      <p>{{ project.description }}</p>
    </div>
  {% endfor %}
</div>