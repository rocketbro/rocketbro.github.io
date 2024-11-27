---
layout: default
title: Projects
---

<div style="font-size: 2rem;"><h1>Projects</h1></div>

Here you'll find a list of projects I've worked on/am currently working on. I keep these pages updated pretty regularly. If you're interested in any of these or in collaborating, please reach out.

<div class="project-grid">
  {% for project in site.projects %}
    {% if project.order == 1 %}
      <div class="project-card">
        <h3><a href="{{ project.url }}">{{ project.project_title }}</a></h3>
        <p>{{ project.type }} • {{ project.description }}</p>
      </div>
    {% endif %}
  {% endfor %}
</div>