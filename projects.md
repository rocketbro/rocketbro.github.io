---
layout: default
title: Projects
---

<div style="font-size: 2rem;"><h1 style="margin-top: 0.25em">Projects</h1></div>

Here you'll find a list of projects I've worked on/am currently working on. This page is still being fleshed out - [check out my GitHub page](https://github.com/rocketbro) to see the very latest updates. If you're interested in any of these or in collaborating, please reach out.

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