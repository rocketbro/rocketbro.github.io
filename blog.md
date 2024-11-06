---
layout: default
title: Blog
---


<h1>Blog Posts</h1>

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <div class="post-meta">{{ post.date | date: "%B %d, %Y" }}</div>
      <!-- <div class="post-excerpt">{{ post.excerpt }}</div> -->
    </li>
  {% endfor %}
</ul>
