---
layout: page
title: Projects
icon: fas fa-laptop-code
order: 2
---

{% comment %}
Below, we filter `site.posts` for those whose categories include "projects".
We then display each project in a card-like layout.
{% endcomment %}

{% assign project_posts = site.posts | where_exp: "post", "post.categories contains 'projects'" %}

<div class="project-list">
  {% for post in project_posts %}
  <div class="project-card">
    <a href="{{ post.url | relative_url }}" class="project-link"></a>
    {% if post.image %}
    <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" class="project-img">
    {% endif %}
    <h2>{{ post.title }}</h2>
  </div>
  {% endfor %}
</div>
