---
layout: default
title: Projects
---

<h1>Projects</h1>

<div class="project-grid">
  {% for project in site.projects %}
    {% if project.order == 1 %}
      <div class="project-card">
        <h3><a href="{{ project.url }}">{{ project.title }}</a></h3>
        <p>{{ project.type }} • {{ project.description }}</p>
      </div>
    {% endif %}
  {% endfor %}
</div>