---
layout: default
title: Projects
---

<h1>Projects</h1>

<div class="project-grid">
  {% for project in site.projects %}
    <div class="project-card">
      <h3><a href="{{ project.url }}">{{ project.title }}</a></h3>
      <p>{{ project.description }}</p>
    </div>
  {% endfor %}
</div>