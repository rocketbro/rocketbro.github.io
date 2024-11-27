---
layout: default
title: Blog
---

<div style="font-size: 2rem;"><h1 style="margin-top: 0.25em">Blog</h1></div>

My posts are sporatic but this is probably the best blog on the entire internet. I mainly write about current projects, but also post thoughts about music, movies, and whatever else is going on in my brain. I also post recipes *with no ads at all* and even better, *no Jump To Recipe button* because the only thing in the post *is* the recipe. Look for CWC (Cooking With Claude) posts - the way online cooking should be.

<ul class="post-list">
  {% for post in site.posts %}
    <li>
      <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      <div class="post-meta">{{ post.date | date: "%B %d, %Y" }}</div>
    </li>
  {% endfor %}
</ul>
